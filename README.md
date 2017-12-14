# offerup

The unofficial OfferUp API client.

> Note: OfferUp doesn't provide an API. So this lib should only be used for personal fun.

## Install

```bash
npm install offerup
```
## Usage

```js
var offerup = require('offerup');

// Set your Google Map Api
offerup.setGoogleMapApi('Your_Api_Key');

// Get your list by Query
offerup.getFullListByQuery({
    location: 'Chicago', // required
    search: 'iphone', // required
    radius: 50,
    limit: 100,
    price_min: 100,
    price_max: 1000
    }).then(function success(response){

        /*
        Output
            "status": {
                "status": "ok",
                "message": "success",
                "code": "200",
                "server_time": "2017-12-10T04:54:43Z"
            },
            "data": {
                "feed_items": [
                    {
                        "type": "item",
                        "item": {
                            "post_date": "2017-12-10T04:49:07.464Z",
                            "owner": {
                                    ...
                                },
                            "id": 391663263,
                            "title": "Looking to buy iPod 6 or any iPhone",
                            "post_date_ago": "13 minutes",
                            "location_name": "Joliet, IL"
                        }
                    }
                ],

            }
        */

    }, function error(response){
        console.log(response);
    });
```

* See the [full getFullListByQuery() docs](docs/getFullListByQuery.md) for the list of all possible modules and the data they return.

## Methods

### setGoogleMapApi()

>https://developers.google.com/maps/

```js
offerup.setGoogleMapApi('Your_Api_Key');
```

### setDefaults()

This data will be used if the query parameter is empty

```js
offerup.setDefaults({
    location: 'New York',
    radius: 30,
    limit: 1000,
    price_min: 100,
    price_max: 1000
});
```