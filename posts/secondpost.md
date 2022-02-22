---
title: Using The Javascript Fetch API To Get Data.
description: This is a post on using js fetch api.
date: 2018-07-04
tags:
  - js
  - API
  - ip
layout: layouts/post.njk
---

Today, I'm going to walk you through how to wire up some data up to a Wikipedia-query tag so that when your IP address changes, your location will change, and so will the Wikipedia article.

## Getting Started

For this lab we utilize [GeoIP](https://freegeoip.app/) to retrieve our `lat`, `long`, `city`, and `state`. Here's how our constructor looks.

```js
  constructor() {
    super();
    this.locationEndpoint = 'https://freegeoip.app/json/';
    this.long = null;
    this.lat = null;
    this.city = null;
    this.state = null;
  }
```

Next, we set the properties that we later use to populate our data. Here we return our lat and long as integers and our city and state as strings.

```js
  static get properties() {
  return {
    long: { type: Number },
    lat: { type: Number },
    city: { type: String },
    state: { type: String },
  };
}
```

## Fetching API

Before fetching the data from our API, let's talk about what fetch is. Fetch API is an interface that allows you to make HTTP requests to servers from web browsers. We utilize the fetch to retrieve our location based on our IP address in this lab. See how we utilize fetch in our lab.

```js
 async getGEOIPData() {
  const IPClass = new UserIP();
  const userIPData = await IPClass.updateUserIP();
  return fetch(this.locationEndpoint + userIPData.ip)
    .then(resp => {
      if (resp.ok) {
        return resp.json();
      }
      return false;
    })
    .then(data => {
      // console.log(data);
      this.long = data.longitude;
      this.lat = data.latitude;
      this.city = data.city;
      this.state = data.region_name;

      return data;
    });
}
```

In this code block, using the URL we set to locationEndpoint we were able to fetch our location based on our IP address. We used fetch to make an HTTP request to the server holding the API, then if the response was "ok," we will return the API call as a [JSON](https://www.json.org/json-en.html). Here's what the API response should look like.

```js
{
"ip": "102.16.28.100",
"country_code": "US",
"country_name": "United States",
"region_code": "PA",
"region_name": "Pennsylvania",
"city": "State College",
"zip_code": "16802",
"time_zone": "America/New_York",
"latitude": 40,
"longitude": -77,
"metro_code": 574
}
```

We then set our properties `lat`, `long`, `city`, and `state` to the variables the API returns to access the data. In this case, we only need the latitude, longitude, city, and region_name, which means the state you are in.

## Render()

```js
render() {
    // this function runs every time a properties() declared variable changes
    // this means you can make new variables and then bind them this way if you like
    const url = `https://maps.google.com/maps?q=${this.lat},${this.long}&t=&z=15&ie=UTF8&iwloc=&output=embed`;
    return html`<iframe title="Where you are" src="${url}"></iframe>
      <br />
      <link href="https://www.google.com/maps/@${this.lat},${this.long},14z" />
      <wikipedia-query search="${this.city}, ${this.state}"></wikipedia-query>
      <wikipedia-query search="${this.city}"></wikipedia-query>
      <wikipedia-query search="${this.state}"></wikipedia-query> `;
  }
```

This method is invoked on each update to perform rendering tasks. This method returns any value renderable by lit-HTML's elements. We pass the `lat` and `long` properties to get the Iframe working. Whenever these properties are changed, lit render the information and updates.

## Wiring The Wikipedia Tags

1. Create an HTML link that sits below the iframe that links to the location on google maps.

2. Pass the `lat`, and `long` properties.

3. Next run npm `install @lrnwebcomponents/wikipedia-query`

4. In order to use the we must import the tag at the top of your file to use it import '@lrnwebcomponents/wikipedia-query/wikipedia-query.js;'

5. Next, in our render function add in the wikipedia tags. [Wikipedia's API is documented](https://en.wikipedia.org/w/api.php)

6. The search property takes `${this.city}`, `${this.state}` and the comma then a space to ensure the tags work properly.

Based on your location the Wikipedia tag will display information of your state and city.

Now you have successfully fetch an API to wire Wikipedia tags. Way to go!

To view the complete project [click here](https://github.com/reyes-edwin/ip-project/blob/master/src/LocationFromIP.js).

# Resources
1. [wikipedia-query](https://www.npmjs.com/package/@lrnwebcomponents/wikipedia-query)
2. [GeoIP](https://freegeoip.app/)
3. [Fecth API](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch)


