---
title: API Reference | Mashvisor

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - javascript
  - php
  - go

toc_footers:
  - <a href='https://www.mashvisor.com'>Mashvisor Inc.</a>
  - <a class="btn-orange" href="https://www.mashvisor.com/signup?source=api">Get a free API key</a>


includes:
  - errors

search: true
---

# Introduction

> Live Main API Endpoint:

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2",
  "method": "GET",
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2');
$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));
$request->setMethod(HTTP_METH_GET);

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2?_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, payload)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> Test Main API Endpoint:

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2?_t=meowmeowmeow",
  "method": "GET",
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2');
$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));
$request->setMethod(HTTP_METH_GET);

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2?_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, payload)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
Welcome to the Mashvisor API reference! You can use our API to access Mashvisor API endpoints needed by developers to build there applications on top of Mashvisor Inc, which can get real estate information, deep analysis, solid and up to date calculatuins on various cities, zip codes, and neighborhoods in our database acrross the United States.

You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

The Mashvisor API is organized around REST. Our API has predictable, resource-oriented URLs, and uses [HTTP](https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) response codes to indicate API errors. We use built-in HTTP features, like HTTP authentication and [HTTP verbs](http://www.restapitutorial.com/lessons/httpmethods.html), which are understood by off-the-shelf HTTP clients. [JSON](http://www.json.org/) is returned by all API responses, including errors.

To make the API as explorable as possible, endpoints have test mode and live mode. You just need to change the main API endpoint between modes.

**The requests in the right sidebar are designed to work as is. The sample requests are performed using a test mode**.

Please if you find any wrong documents contact *ahmadh@mashvisor.com* mentioning the file link.

# Authentication

> To authorize, use this code:

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/octet-stream");
RequestBody body = RequestBody.create(mediaType, null);
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2?_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2');
$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2?_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> Make sure to replace `meowmeowmeow` with your API key.

> JWT Token Payload example:

```json
{
  "exp": 1568793046,
  "iss": "Mashvisor.com",
  "user": {
    "role": "agent_crm_manager,Agent",
    "created_at": 1447594446000,
    "last_name": "Hashlamon",
    "locale": "en",
    "subscription_plan": "MASHVISOR_TOP_AGENT",
    "provider": "MASHVISOR",
    "subscription_end_at": null,
    "name": "Ahmed Hashlamon",
    "id": 579,
    "plan_interval": "ANNUAL",
    "mobile_number": "+16692226396",
    "first_name": "Ahmed",
    "email": "ahmadh@mashvisor.com"
  }
}
```

Mashvisor uses API keys to allow access to the API. You can ask for an API key via subscribing [here](https://www.mashvisor.com/signup?source=api). <br>

Mashvisor expects for the API key to be included in all API requests to the server. <br>

Moreover, Mashvisor allows you to authenticate your account when using the API by including your secret authorization header in the request which is basically a [JWT](https://en.wikipedia.org/wiki/JSON_Web_Token) token. Such authentication to the API is performed via [HTTP Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication).  <br>

All API requests requires the JWT authentication must be made over [HTTPS](https://en.wikipedia.org/wiki/HTTP_Secure). Calls made over plain HTTP will fail.

<aside class="notice">
You must replace <code>{JWT_TOKEN}</code> with your personal API key.
</aside>

# CORE RESOURCES
# Search
## List Cities

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/city/list?state=FL")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/city/list?state=FL",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/city/list');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'FL'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/city/list?state=FL"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "count": 692,
    "list": [
        "Anthony",
        "BABSON PARK",
        "BAGDAD",
        "Bal Harbour",
        "BALDWIN",
        "Belle Glade",
        "Belleview",
        "BOCA GRANDE",
        "BRADENTON BEACH",
        "CALLAHAN"
    ]
}
```

This endpoint retrieves the cities has the biggest occupancy in a specific state. 

### HTTP Request

`GET http://api.mashvisor.com/v.1/city/list` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV. If ignored, it will fetch all available cities.
page | Integer | 1 | The page to return the content for. Valid values:1, ... etc.
items | Integer | 10 | The items to return the content for. Valid values: 10, ... etc.

## List Neighborhoods

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/city/neighborhoods/CA/Los Angeles?_t=meowmeowmeow&state=GA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/city/neighborhoods/CA/Los Angeles?_t=meowmeowmeow&state=GA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/city/neighborhoods/CA/Los Angeles?_t=meowmeowmeow&state=GA');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/city/neighborhoods/CA/Los Angeles?_t=meowmeowmeow&state=GA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "count": 96,
        "results": [
            {
                "id": 7877,
                "city": "Los Angeles",
                "latitude": 33.952138,
                "longitude": -118.404407,
                "name": "Westchester",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 13017,
                "city": "Los Angeles",
                "latitude": 34.238792,
                "longitude": -118.477272,
                "name": "North Hills",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 13176,
                "city": "Los Angeles",
                "latitude": 34.228894,
                "longitude": -118.444025,
                "name": "Panorama City",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 13327,
                "city": "Los Angeles",
                "latitude": 33.974969,
                "longitude": -118.420888,
                "name": "Playa Vista",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 19810,
                "city": "Los Angeles",
                "latitude": 34.078243,
                "longitude": -118.546495,
                "name": "Pacific Palisades",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 21056,
                "city": "Los Angeles",
                "latitude": 33.986305,
                "longitude": -118.462922,
                "name": "Venice",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 25449,
                "city": "Los Angeles",
                "latitude": 34.231196,
                "longitude": -118.317322,
                "name": "La Tuna Canyon",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            {
                "id": 27080,
                "city": "Los Angeles",
                "latitude": 34.173907,
                "longitude": -118.461303,
                "name": "Sherman Oaks",
                "state": "CA",
                "county": "Los Angeles",
                "is_village": 0
            },
            ...
        ]
    },
    "message": "City neighborhoods list fetched successfully"
}
```

This endpoint lsits all city avialable neighborhoods. 

### HTTP Request

`GET https://api-build.mashvisor.com/v2/city/neighborhoods/C/{state}/{city}` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | State name, ex: NV.
city | String | | City Name, Ex: Los Angeles

## List Top Markets

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/city/top-markets?_t=meowmeowmeow&state=GA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/city/top-markets?_t=meowmeowmeow&state=GA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/trends/neighborhoods');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'GA'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/city/top-markets?_t=meowmeowmeow&state=GA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": [
        {
            "city": "Atlanta",
            "state": "GA",
            "smart_location": "Atlanta, GA",
            "homes_for_sale": 6019
        },
        {
            "city": "Marietta",
            "state": "GA",
            "smart_location": "Marietta, GA",
            "homes_for_sale": 1183
        },
        {
            "city": "Savannah",
            "state": "GA",
            "smart_location": "Savannah, GA",
            "homes_for_sale": 1110
        },
        {
            "city": "Decatur",
            "state": "GA",
            "smart_location": "Decatur, GA",
            "homes_for_sale": 1029
        },
        {
            "city": "Lawrenceville",
            "state": "GA",
            "smart_location": "Lawrenceville, GA",
            "homes_for_sale": 873
        }
    ],
    "message": "Top markets list fetched successfully"
}
```

This endpoint retrieves the top housing cities with their active homes for sale count in a specific state. 

### HTTP Request

`GET https://api-build.mashvisor.com/v2/city/top-markets` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
items | Integer | 5 | The items to return the content for. Valid values: 10, ... etc.

## Get City Invesmtent Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/city/investment/CA/Los Angeles?_t=meowmeowmeow&state=GA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/city/investment/CA/Los Angeles?_t=meowmeowmeow&state=GA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/city/investment/CA/Los Angeles?_t=meowmeowmeow&state=GA');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/city/investment/CA/Los Angeles?_t=meowmeowmeow&state=GA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "median_price": 998378.0407,
        "sqft": 1842.1734,
        "investment_properties": 4448,
        "airbnb_properties": 7084,
        "traditional_properties": 14354,
        "occupancy": 68.6682,
        "traditional_coc": 1.6432380442643497,
        "airbnb_coc": 1.6819542874835247,
        "traditional_rental": 3777.875777894207,
        "airbnb_rental": 4093.917001833255,
        "airbnb_rental_rates": {
            "oneBedRoomHomeValue": 2336.444943967073,
            "twoBedRoomsHomeValue": 3083.203274119984,
            "threeBedRoomsHomeValue": 4045.138149354516,
            "fourBedRoomsHomeValue": 5573.433687482561
        },
        "traditional_rental_rates": {
            "oneBedRoomHomeValue": 1763.9154224395752,
            "twoBedRoomsHomeValue": 2686.9422912597656,
            "threeBedRoomsHomeValue": 3942.8028729756675,
            "fourBedRoomsHomeValue": 4796.2156499226885
        }
    },
    "message": "City Overview fetched successfully"
}
```

This endpoint retrieves the city investment performance. 

### HTTP Request

`GET https://api-build.mashvisor.com/v2/city/investment/{state}/{city}` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | State name, ex: NV.
city | String | | City Name, Ex: Los Angeles


## Get City Top Properties

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/city/properties/CA/Los Angeles?_t=meowmeowmeow&state=GA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/city/properties/CA/Los Angeles?_t=meowmeowmeow&state=GA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/city/properties/CA/Los Angeles?_t=meowmeowmeow&state=GA');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/city/properties/CA/Los Angeles?_t=meowmeowmeow&state=GA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "properties": [
            {
                "id": 642325,
                "neighborhood": "Westlake",
                "neighborhood_id": 276023,
                "address": "308 N Mountain View Avenue",
                "zip_code": 90026,
                "zip": 90026,
                "city": "Los Angeles",
                "county": "LOS ANGELES",
                "state": "CA",
                "type": "Single Family Residential",
                "image_url": "http://photos.listhub.net/SOCALMLS/RS16117046/1?lm=20160601T225422",
                "list_price": 275000,
                "baths": 1,
                "beds": 2,
                "sqft": 1247,
                "days_on_market": 1203,
                "next_open_house_date": null,
                "next_open_house_start_time": null,
                "next_open_house_end_time": null,
                "last_sale_date": "2017-02-15 00:00:00",
                "last_sale_price": 415000,
                "listing_id": "RS16117046",
                "has_pool": null,
                "is_water_front": null,
                "num_of_units": null,
                "latitude": 34.0691,
                "longitude": -118.267,
                "traditional_ROI": 5.10278,
                "airbnb_ROI": 9.7587,
                "traditional_rental": 2406.54,
                "airbnb_rental": 4217.37,
                "traditional_cap": 5.10278,
                "airbnb_cap": 9.7587,
                "list_price_formatted": "$275,000",
                "price_per_sqft": 221,
                "country": "United States",
                "COC": {
                    "airbnb": 9.7587,
                    "traditional": 5.10278
                },
                "rental_income": {
                    "airbnb": 4217.37,
                    "traditional": 2406.54
                },
                "cap_rate": {
                    "airbnb": 9.7587,
                    "traditional": 5.10278
                },
                "image": "http://photos.listhub.net/SOCALMLS/RS16117046/1?lm=20160601T225422"
            },
            {
                "id": 1046266,
                "neighborhood": "Sun Valley",
                "neighborhood_id": 41131,
                "address": "11854 Roscoe Boulevard",
                "zip_code": 91352,
                "zip": 91352,
                "city": "Los Angeles",
                "county": "LOS ANGELES",
                "state": "CA",
                "type": "Single Family Residential",
                "image_url": "http://photos.listhub.net/BCSREGTX/18006654/1?lm=20180329T181647",
                "list_price": 255000,
                "baths": 2,
                "beds": 3,
                "sqft": 1048,
                "days_on_market": 449,
                "next_open_house_date": null,
                "next_open_house_start_time": null,
                "next_open_house_end_time": null,
                "last_sale_date": null,
                "last_sale_price": null,
                "listing_id": "18006654",
                "has_pool": null,
                "is_water_front": null,
                "num_of_units": null,
                "latitude": 34.2213,
                "longitude": -118.392,
                "traditional_ROI": 6.54324,
                "airbnb_ROI": 9.51711,
                "traditional_rental": 2672.32,
                "airbnb_rental": 3857.34,
                "traditional_cap": 6.54324,
                "airbnb_cap": 9.51711,
                "list_price_formatted": "$255,000",
                "price_per_sqft": 243,
                "country": "United States",
                "COC": {
                    "airbnb": 9.51711,
                    "traditional": 6.54324
                },
                "rental_income": {
                    "airbnb": 3857.34,
                    "traditional": 2672.32
                },
                "cap_rate": {
                    "airbnb": 9.51711,
                    "traditional": 6.54324
                },
                "image": "http://photos.listhub.net/BCSREGTX/18006654/1?lm=20180329T181647"
            },
            {
                "id": 2104921,
                "neighborhood": "Boyle Heights",
                "neighborhood_id": 113886,
                "address": "1222 S Herbert Avenue",
                "zip_code": 90023,
                "zip": 90023,
                "city": "Los Angeles",
                "county": "Los Angeles",
                "state": "CA",
                "type": "Single Family Residential",
                "image_url": "http://media.crmls.org/medias/a2901c46-5520-4750-8546-d5fa6ad66164.jpg",
                "list_price": 340000,
                "baths": 2,
                "beds": 4,
                "sqft": 1600,
                "days_on_market": 7,
                "next_open_house_date": null,
                "next_open_house_start_time": null,
                "next_open_house_end_time": null,
                "last_sale_date": "2017-03-14 00:00:00",
                "last_sale_price": 280000,
                "listing_id": "MB19181287",
                "has_pool": null,
                "is_water_front": null,
                "num_of_units": null,
                "latitude": 34.0182,
                "longitude": -118.183,
                "traditional_ROI": 3.39692,
                "airbnb_ROI": 9.04391,
                "traditional_rental": 2455.65,
                "airbnb_rental": 4994.44,
                "traditional_cap": 3.39692,
                "airbnb_cap": 9.04391,
                "list_price_formatted": "$340,000",
                "price_per_sqft": 213,
                "country": "United States",
                "COC": {
                    "airbnb": 9.04391,
                    "traditional": 3.39692
                },
                "rental_income": {
                    "airbnb": 4994.44,
                    "traditional": 2455.65
                },
                "cap_rate": {
                    "airbnb": 9.04391,
                    "traditional": 3.39692
                },
                "image": "http://media.crmls.org/medias/a2901c46-5520-4750-8546-d5fa6ad66164.jpg"
            },
            {
                "id": 1953384,
                "neighborhood": "Harbor City",
                "neighborhood_id": 38888,
                "address": "24815 Normandie Avenue #66",
                "zip_code": 90710,
                "zip": 90710,
                "city": "Los Angeles",
                "county": "LOS ANGELES",
                "state": "CA",
                "type": "Other",
                "image_url": "http://photos.listhub.net/MRMLSCA/SB19148313/1?lm=20190624T132410",
                "list_price": 65000,
                "baths": 1,
                "beds": 1,
                "sqft": 654,
                "days_on_market": 86,
                "next_open_house_date": null,
                "next_open_house_start_time": null,
                "next_open_house_end_time": null,
                "last_sale_date": null,
                "last_sale_price": null,
                "listing_id": "SB19148313",
                "has_pool": null,
                "is_water_front": null,
                "num_of_units": null,
                "latitude": 33.8002,
                "longitude": -118.298,
                "traditional_ROI": 9.94736,
                "airbnb_ROI": 8.81465,
                "traditional_rental": 1179.68,
                "airbnb_rental": 1552.57,
                "traditional_cap": 9.94736,
                "airbnb_cap": 8.81465,
                "list_price_formatted": "$65,000",
                "price_per_sqft": 99,
                "country": "United States",
                "COC": {
                    "airbnb": 8.81465,
                    "traditional": 9.94736
                },
                "rental_income": {
                    "airbnb": 1552.57,
                    "traditional": 1179.68
                },
                "cap_rate": {
                    "airbnb": 8.81465,
                    "traditional": 9.94736
                },
                "image": "http://photos.listhub.net/MRMLSCA/SB19148313/1?lm=20190624T132410"
            }
        ]
    },
    "message": "City Properties fetched successfully"
}
```

This endpoint retrieves the city's top invesmtent properties performance. 

### HTTP Request

`GET https://api-build.mashvisor.com/v2/city/properties/{state}/{city}` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | State name, ex: NV.
city | String | | City Name, Ex: Los Angeles

## Get Top Neighborhoods

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/trends/neighborhoods?state=IL&city=Chicago&items=3")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/trends/neighborhoods?state=IL&city=Chicago&items=3",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/trends/neighborhoods');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'IL',
  'city' => 'Chicago',
  'items' => '3'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/trends/neighborhoods?state=IL&city=Chicago&items=3"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "total_results": 3,
        "current_page": 1,
        "state": "IL",
        "city": "Chicago",
        "neighborhoods": [
            {
                "id": 269585,
                "name": "Humboldt Park",
                "city": "Chicago",
                "state": "IL",
                "occupancy": "55.40430000",
                "total_listing": 47,
                "description": null,
                "single_home_value": 520000,
                "single_home_value_formatted": "$520,000",
                "investment_rentals": {
                    "airbnb_rental": {
                        "roi": 2.206806357417788,
                        "cap_rate": 4.275257478632692,
                        "rental_income": 1852.6115740741664
                    },
                    "traditional_rental": {
                        "roi": 0.2465075217187405,
                        "cap_rate": 3.185552884615385,
                        "rental_income": 1380.40625
                    }
                },
                "mashMeter": 57.7665
            },
            {
                "id": 269592,
                "name": "Logan Square",
                "city": "Chicago",
                "state": "IL",
                "occupancy": "55.10080000",
                "total_listing": 119,
                "description": null,
                "single_home_value": 350000,
                "single_home_value_formatted": "$350,000",
                "investment_rentals": {
                    "airbnb_rental": {
                        "roi": 3.7590651363134384,
                        "cap_rate": 6.757881386799999,
                        "rental_income": 1971.0487378166665
                    },
                    "traditional_rental": {
                        "roi": 1.5805461276322603,
                        "cap_rate": 5.608165714285714,
                        "rental_income": 1635.715
                    }
                },
                "mashMeter": 58.353
            },
            {
                "id": 403312,
                "name": "Ukrainian Village",
                "city": "Chicago",
                "state": "IL",
                "occupancy": "54.73170000",
                "total_listing": 41,
                "description": null,
                "single_home_value": 464500,
                "single_home_value_formatted": "$464,500",
                "investment_rentals": {
                    "airbnb_rental": {
                        "roi": 2.949021758402095,
                        "cap_rate": 6.284044771359168,
                        "rental_income": 2432.448996913611
                    },
                    "traditional_rental": {
                        "roi": 0.749465583878405,
                        "cap_rate": 4.492094725511302,
                        "rental_income": 1738.815
                    }
                },
                "mashMeter": 62.044
            }
        ]
    },
    "message": "City Overview fetched successfully"
}
```

This endpoint retrieves the neighborhoods has the biggest occupancy in a specific city and state. 

### HTTP Request

`GET http://api.mashvisor.com/v.1/trends/neighborhoods` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
city | String* | | city name, ex: Las Vegas.
page | Integer | 1 | The page to return the content for. Valid values:1, ... etc.
items | Integer | 5 | The items to return the content for. Valid values: 10, ... etc.
desc | Boolean | false | If it's true, it'll fetch the neighborhood description and single home values in the request response.

## Get Neighborhood Overview

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/neighborhood/268201/bar?_t=meowmeowmeow&state=CA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/neighborhood/268201/bar?_t=meowmeowmeow&state=CA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/neighborhood/268201/bar');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  '_t' => 'meowmeowmeow',
  'state' => 'CA'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/neighborhood/268201/bar?_t=meowmeowmeow&state=CA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "id": "268201",
        "name": "Haight Ashbury",
        "city": "San Francisco",
        "county": "San Francisco",
        "state": "CA",
        "is_village": 0,
        "description": "Years ago, the Haight-Ashbury of San Francisco scene had a long-gone '60s and ‘70s hippie culture.  However, over time the Haight has changed.  But save for a few hippie memorabilia, today the Haight has a whole new vibe.  Although there are some fragments of flower-power, incense-burning, acid-dropping, peace-and-love-vibing era that can be purchased at smoke shops along the neighborhood, today the neighborhood is different. With exclusive boutiques, high-end vintage-clothing shops, second-hand stores, Internet cafés and hip restaurants having all settled in, this reinvented area stands out as one of San Francisco's commercial centers.  \r\n\r\nWhat makes the Haight unique is its just-rolled-out-of-bed vibe during the day, which provides a perfect opportunity for lazing around in cafés and bookstores.  Weekends can get quite crowded with shoppers and brunch seekers during the day and club-goers at night. Neo-punks, club kids, fashionistas, tourists and neighborhood locals also fit in here, whether they have come to get a new piercing, grab a burrito or just enjoy some fun people-watching from a café.  But there are two distinct areas of the Haight: The Upper Haight, which stretches from Stanyan to Masonic, which is known as the shopping zone, though it deteriorates a bit where it stretches toward Golden Gate Park. While, the Lower Haight, roughly Divisidero to Webster is a more diverse neighborhood with a stony feel. While it has been an alternate nightlife hub for years, the Lower Haight has become a main attraction for DJs and ravers with an attraction to dance-music and clubs.",
        "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
        "latitude": 37.768094,
        "longitude": -122.448285,
        "walkscore": 96,
        "num_of_properties": 3,
        "num_of_airbnb_properties": 161,
        "num_of_traditional_properties": 21,
        "median_price": 699000,
        "price_per_sqft": 908.19,
        "mashMeter": 84.86,
        "avg_occupancy": 82.7578,
        "strategy": "airbnb",
        "airbnb_rental": {
            "roi": 3.7042534351348877,
            "cap_rate": 10.878766820904865,
            "rental_income": 6336.881673177083
        },
        "traditional_rental": {
            "roi": 2.3523680369059243,
            "cap_rate": 7.266060085836912,
            "rental_income": 4232.4800000000005
        }
    },
    "message": "Neighborhood bar fetched successfully"
}
```

This endpoint retrieves a neighborhood investment analysis and overview. 

### HTTP Request

`GET https://api-build.mashvisor.com/v2/neighborhood/{id}/bar` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Integer | | Neighborhood id

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | Neighborhood's state

# Property Info
## The Property Objects

> The Property Object:

```json
{
  "status": "success",
  "content": {
    "stateInterest": {
      "state": "GA",
      "thirtyYearFixed": 4.41,
      "thirtyYearFixedCount": 0,
      "fifteenYearFixed": 3.83,
      "fifteenYearFixedCount": 0,
      "fiveOneARM": 3.95,
      "fiveOneARMCount": 0
    },
    "isShortSale": null,
    "source": "Property Services of Atlanta,  Inc.",
    "yearBuilt": 2005,
    "nextOpenHouseEndTime": null,
    "sqft": 1566,
    "lastSaleDate": "2017-03-23 00:00:00",
    "id": 2214791,
    "state": "GA",
    "county": "DeKalb",
    "longitude": -84.51863861083984,
    "zip": 30331,
    "image": {
      "image": "http://photos.listhub.net/GAMLS/8655658/1?lm=20190908T182354",
      "url": "http://photos.listhub.net/GAMLS/8655658/1?lm=20190908T182354",
      "width": 100,
      "height": 100
    },
    "extra_images": [
      "http://photos.listhub.net/GAMLS/8655658/1?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/2?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/3?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/4?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/5?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/6?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/7?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/8?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/9?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/10?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/11?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/12?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/13?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/14?lm=20190908T182354"
    ],
    "videos": [],
    "virtual_tours": [],
    "tax": 1765,
    "mls_id": "8655658",
    "daysOnMarket": 3,
    "neighborhood": {
      "country": "United States",
      "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
      "city": "Atlanta",
      "singleHomeValue": 140000,
      "mashMeter": 67.49,
      "latitude": 33.692139,
      "description": null,
      "singleHomeValue_formatted": "$140,000",
      "is_village": false,
      "mashMeter_formatted": 67.49,
      "name": "Fairburn",
      "id": 403452,
      "state": "GA",
      "longitude": -84.522495,
      "walkscore": 14,
      "airbnb_properties_count": 6,
      "traditional_properties_count": 0
    },
    "homeType": "Single Family Residential",
    "property_type": "Residential",
    "property_sub_type": "Single Family Detached",
    "beds": 4,
    "num_of_units": null,
    "favorite": null,
    "status": "Active",
    "city": "Atlanta",
    "saleType": "MLS Listing",
    "latitude": 33.69144821166992,
    "description": "Home has covered front porch, spare bedroom and full bath with shower only on main.  Open kitchen with dining area and access to the back of the home.  Upper level has laundry closet, two spare bedrooms, full hall bath, master bedroom and master bath.   Great home for a first-time buyer or investor.   Home is all electric.   Investor owned and is being sold 'as-is' with no disclosures.  No HOA.   Tenants will be out shortly.   No showings until home is vacant.",
    "nextOpenHouseDate": null,
    "recentReductionDate": null,
    "title": "Single Family Detached, Traditional - Atlanta, GA",
    "rent_appreciation_rate": null,
    "originalListPrice": null,
    "parkingSpots": 1,
    "parkingType": "Attached",
    "address": "2333 Daniel",
    "nextOpenHouseStartTime": null,
    "lotSize": 5663,
    "broker_name": "Property Services of Atlanta,  Inc.",
    "broker_number": "(678) 384-6220",
    "broker_url": "http://www.psatlanta.com/atlanta-homes-for-sale",
    "agents": [
      {
        "id": 39995,
        "office_id": 8461
      }
    ],
    "url": "https://listings.listhub.net/pages/GAMLS/8655658/?channel=mashv",
    "baths": 3,
    "address_revealing": true,
    "location": "Fairburn",
    "interested": null,
    "listPrice": 125000,
    "price_per_sqft": 79.82120051085569,
    "lastSalePrice": 145000,
    "is_foreclosure": 0,
    "foreclosure_status": null,
    "occupancy_status": null,
    "owner_occupied": false,
    "listing_date": "2019-09-06T00:00:00.000Z",
    "heating_system": "Fireplace",
    "cooling_system": "Ceiling Fan(s)",
    "mls_name": "Georgia Multiple Listing Service",
    "hoa_dues": null,
    "view_type": null,
    "parcel_number": "14F-0032-0005-068-9",
    "architecture_style": "New Traditional",
    "has_pool": null,
    "is_water_front": null,
    "needs_repair": 0,
    "tenant_occupied": 0,
    "is_market_place": 0,
    "schools": [
      {
        "category": "Elementary",
        "name": "Deerwood Academy",
        "district": null
      },
      {
        "category": "High",
        "name": "Therrell",
        "district": null
      },
      {
        "category": "JuniorHigh",
        "name": null,
        "district": null
      },
      {
        "category": "Middle",
        "name": "Bunche",
        "district": null
      }
    ],
    "modification_timestamp": "2019-09-08T18:40:39.000Z",
    "created_at": "2019-09-09T05:23:45.000Z",
    "updated_at": "2019-09-09T05:23:45.000Z"
  }
}
```

Mashvisor has agreements with multiple MLS' providers and we're currently finalizing agreements with multiple others.
We currently have 6M+ MLS listings in total in our databases (active and inactive). ~850K Active MLS listings from them nationwide. Covering 600+ MLSs out of 820.

### Property Data Dictionary

| Attribute | Definition | Possible Returns |
|-------------|-------------------------------------------------------|---------------------------|
| id          | Mashvisor Property ID                                 | Integer                   |
| title       | A short title for the property                        | String                    |
| description | Longer description of the property                    | String                    |
| home_type   | The property sub type as provided by the MLS provider | String <br>Possible values: <br>1. Single Family Residential <br>2.Townhouse <br>3.Condo/Coop <br>4.Multi Family <br>5. Other|
| property_main_type | The property main type as provided by the MLS provider| String <br>Possible values: <br>* Residential <br>* Commercial <br>* Common Interest <br>* Farm And Agriculture <br>* Lots And Land <br>* MultiFamily <br>* Other <br>* Rental <br>* Residential           |
| property_category  | The main property listing category                                       | String <br>Possible values:  <br>* Purchase <br>* Lease <br>* Rent                  |
| address            | The full street address of the property, ex:<br> 36981 Newark Blvd #B | String                |
| city               | The city where the property is located                                | String                |
| state              | The state where the property is located                               | String                |
| county             | County where a property is located                                    | String                |
| zip                | Postal code where a property is located                               | Integer               |
| location           | The neighborhood where the property is located                        | String                |
| beds               | Property full bedrooms count                                          | Integer               |
| baths              | Property full bathrooms count                                         | Integer               |
| num_of_units       | Number of units in the property, only exists with multifamily properties | Integer               |
| sqft               | Property living area in square feet unit                                 | Integer               |
| lot_size           | The lot size of the property in square feet unit                         | Integer               |
| parcel_number        | The property APN assigned by tax assessor                | String                                |
| listing_id           | The MLS ID of the property                               | String                                |
| year_built           | The year was constructed in                              | Integer                               |
| walkscore            | The walkscore value of the property address              | Integer                               |
| tax                  | The last knows tax amount                                | Integer                               |
| tax_history          | Collection of all the taxes reported for a property      | JSON Array                            |
| list_price           | The listed price for the property                        | Integer                               |
| price_per_sqft       | Price per sqft value                                     | Float                                 |
| days_on_market       | Number of days since the property was on market for sale | Integer                               |
| parking_spots        | Number of parking spots                                  | Integer                               |
| parking_type         | An indicator for the parking type                        | Integer                               |
| last_sale_date       | The last sale date of the property                       | Date                                  |
| last_sale_price      | The last sale price of the property                      | Integer                               |
| is_foreclosure       | An indicator if the property is foreclosure or not       | Boolean <br> Possible values: 0, 1 |
| foreclosure_status   | The foreclosure status as described by the MLS provider  | String  <br> Possible values <br>* Foreclosure - Other <br>* Lis Pendens (Pre-Foreclosure) <br>* Notice of Default (Pre-Foreclosure) <br>* Notice of Foreclosure Sale (Auction) <br>* Notice of Trustee Sale (Auction) <br>* Other <br>* REO - Bank Owned  |
| next_open_house_date | The date of the open house occuring                      | Date                                  |
| next_open_house_start_time | The time of the open house starting                             | Time             |
| next_open_house_end_time   | The time of the open house ending                               | Time             |
| url                        | The URL of the property                                         | String           |
| source                     | The name of the entity authorized the property to be syndicated | String           |
| provider_url               | The URL of the entity authorized the property to be syndicated  | String           |
| mls_name                   | The name of the MLS                                             | String           |
| broker_name                | The broker’s name                                               | String           |
| broker_number              | The broker’s phone number                                       | String           |
| broker_email               | The broker’s email                                              | String           |
| broker_address             | The broker’s full address                                       | String           |
| franchise                  | The franchise of the property                                   | String           |
| latitude                   | Latitude of the property                                        | Float            |
| longitude                  | Longitude of the property                                       | Float            |
| directions                 | The directions for the property                                 | String           |
| heating_system             | The heating system type                                         | String           |
| cooling_system             | The cooling system type                                         | String           |
| neighborhood_id            | The property neighborhood ID                                    | Integer          |
| schools                    | Collection of all the schools nearby a property                 | JSON Array       |
| view_type                  | The property view type                                          | String <br> Possible values: <br>* Airport <br>* Average <br>* Bluff <br>* Bridge <br>* Canyon <br>* City <br>* Desert <br>* Forest <br>* Golf Course <br>* Harbor <br>* Hills <br>* Lake <br>* Marina <br>* Mountain <br>* None <br>* Ocean <br>* Other <br>* Panorama <br>* Park <br>* Ravine <br>* River <br>* Territorial <br>* Unknown <br>* Valley <br>* Vista <br>* Water |
| image_url          | The property main image URL                            | String                                        |
| extra_images       | List of the images associated with a property          | String                                        |
| videos             | Videos associated with a property                      | String                                        |
| virtual_tours      | Virtual tour link for a property                       | String                                        |
| listing_date       | The date when the property was listed for sale         | Date                                          |
| updated_at         | Date it’s updated in the database                      | Date                                          |
| buyer_name         | The property buyer’s name                              | String                                        |
| seller_name        | The property seller’s name                             | String                                        |
| owner_ame          | The property owner’s name                              | String                                        |
| owner_address      | The owner full street address                          | String                                        |
| owner_city         | The owner city                                         | String                                        |
| owner_state        | The owner city                                         | String                                        |
| owner_zip_code     | The owner city                                         | String                                        |
| owner_phone_number | The owner phone number                                 | String                                        |
| owner_image        | The owner headshot                                     | String                                        |
| owner_email        | The owner email                                        | String                                        |
| occupancy_status   | Property occupancy status                              | String <br> Possible values: <br>* Assumed Owner Occupancy <br>* Owner Occupied or Primary Residence <br>* Second Home |
| agent_id           | The property’s agent ID associated to it               | Integer                                       |
| Expense            | Collection of all the expenses reported for a property | JSON Array <br> Possible values: <br>* AC Maintenance Fee <br>* Accounting Fee <br>* Additional Pet Fee <br>* Amenity Fee <br>* Annual Operating Expenses <br>* Application Fee <br>* Beach Fee <br>* Boat Fee <br>* Broadband Fee <br>* Building Insurance <br>* Building Maintenance Fee <br>* Bus Service Fee <br>* Cable Fee <br>* Capital Improvements Fee <br>* Carpet Cleaning Fee <br>* Cleaning Deposit <br>* Cleaning Fee <br>* Closing Cost <br>* Club Fee <br>* Club Membership Fee <br>* Co-Op Fee <br>* Cold Water Fee <br>* Common Area Maintenance Fee <br>* Community Development District Fee <br>* Community/Master Home Owner Fee <br>* Condo Management Fee <br>* Condo/Co-Op Fee <br>* Contingency Fund Fee <br>* Cook Fee <br>* Day Care Fee <br>* Dock Fee <br>* Doorman Fee <br>* Dredging Fee <br>* Electric Fee <br>* ElevatorUseFee<br>* EquestrianFee<br>* ExterminatorFee<br>* FacilitiesFee<br>* FireDepartmentDues<br>* FireInsuranceFee<br>* FirewoodFee<br>* FirstMonthsRent<br>* FirstTwoMonthsRent<br>* FitnessCenterFee<br>* FrontFootFee<br>* GardenerFee<br>* GasFee<br>* GreenFee<br>* GroundMaintenanceFee<br>* GroundRent<br>* GutterCleaningFee<br>* HealthFee<br>* HomeOwnerAssessmentsFee<br>* HomeOwnerTransferFee<br>* HorseCareFee<br>* InitiationFee<br>* KeyDeposit<br>* LandAssessmentFee<br>* LandFee<br>* LastMonthsRent<br>* LawnMaintenanceFee<br>* LegalFee<br>* LifeguardFee<br>* LightBulbs Filters Fuses AlarmCareFee<br>* LightFee<br>* MaidServiceFee<br>* MaintenanceonPool <br>* ManagementFee<br>* MarinaFee<br>* Mello-RoosCommunityFacilitiesDistrictFee<br>* MHParkFees<br>* MoveinFee<br>* MoveoutFee<br>* OilFee<br>* OnsiteParkingFee<br>* OriginationFee<br>* Other<br>* OwnerPays<br>* ParkFee<br>* ParkingFee<br>* PetAddendumFee<br>* PetApplicationFee<br>* PetDeposit<br>* PhoneFee<br>* Pier/DockMaintenanceFee<br>* PlannedAreaDevelopmentFee<br>* POAFee<br>* Pool/SpaFee<br>* ProcessingFee<br>* RanchFee<br>* Re-KeyFee<br>* RecaptureFee<br>* RecreationFee<br>* RecyclingFee<br>* RegimeFee<br>* RepairDeductible<br>* ReservationFee<br>* ResortFee<br>* RoofMaintenanceFee<br>* RoofRepairFee<br>* RoofReplacementFee<br>* RVFee<br>* RVParkingFee<br>* SecurityDeposit<br>* SecurityLightFee<br>* SecurityMonitoringFee<br>* SecurityServiceFee<br>* SecurityStaffFee<br>* SecuritySystemFee<br>* SepticInspectionFee<br>* SewerFee<br>* SewerTapFee<br>* SnowRemovalFee<br>* SocialFee<br>* SpecialAssessmentFee<br>* StormWaterFee<br>* StreetLightingFee<br>* StreetMaintenanceFee<br>* StreetParkingFee<br>* StructuralMaintenanceFee<br>* TenantPays<br>* TennisFee<br>* TrashFee<br>* TripleNetFee<br>* UtilitiesFee<br>* WalkingTrailFee<br>* WaterFee<br>* WaterHeaterFee<br>* WaterIrrigationFee<br>* WaterPipeFee<br>* WaterRightsFee<br>* WaterTapFee<br>* WaterTreatmentFee<br>* WaterUseFee<br>* Water/SewerHookupFee<br>* WaterfrontFee<br>* WindowCleaningFee<br>* YardCareFee
| builder_name    | The builder name of a property                                                                        | String                                 |
| builder_email   | The builder email of a property                                                                       | String                                 |
| builder_number  | The builder phone number of a property                                                                | String                                 |
| builder_address | The builder full address of a property                                                                | String                                 |
| disclaimer      | String serves as a negation or limitation of the rights under a warranty given by a seller to a buyer | String                                 |
| appliances      | A description of the appliance as provided                                                            | JSON Array <br> Possible values:<br>* BarbequeorGrill <br>* CoffeeSystem <br>* CoffeeSystem-Roughin <br>* Cooktop <br>* Cooktop-Electric <br>* Cooktop-Electric2burner <br>* Cooktop-Electric6burner <br>* Cooktop-Gas <br>* Cooktop-Gas2burner <br>* Cooktop-Gas5burner <br>* Cooktop-Gas6burner <br>* Cooktop-GasCustom <br>* Cooktop-Induction <br>* Cooktop-Induction2burner <br>* Cooktop-Induction6burner <br>* Dishwasher <br>* Dishwasher-Drawer <br>* Dishwasher-Twoormore <br>* Dryer <br>* Dryer-Dualfuel <br>* Dryer-Electric110V <br>* Dryer-Electric220V <br>* Dryer-Gas <br>* Dryer-Gasroughin <br>* Freezer <br>* Freezer-Compact <br>* Freezer-Upright <br>* GarbageDisposer <br>* IceMaker <br>* Microwave <br>* None <br>* Other <br>* Oven <br>* Oven-Convection <br>* Oven-Double <br>* Oven-DoubleElectric <br>* Oven-DoubleGas <br>* Oven-Gas <br>* Oven-Gas3wide <br>* Oven-Self-Cleaning <br>* Oven-Steam <br>* Oven-Twin <br>* Oven-TwinElectric <br>* Oven-TwinGas <br>* Oven-TwinGas3wide <br>* Oven-TwinMixed <br>* Range <br>* Range-BuiltIn <br>* Range-Dual <br>* Range-Dual10burner <br>* Range-Dual6burner <br>* Range-Dual8burner <br>* Range-Electric <br>* Range-Gas <br>* Range-Gas10burner <br>* Range-Gas6burner <br>* Range-Gas8burner <br>* Range-Induction <br>* Range-Other <br>* Rangetop-Electric <br>* Rangetop-Electric2burner <br>* Rangetop-Electric6burner <br>* Rangetop-Gas <br>* Rangetop-Gas10burner <br>* Rangetop-Gas2burner <br>* Rangetop-Gas4burnercompact <br>* Rangetop-Gas6burner <br>* Rangetop-Gas8burner <br>* Rangetop-GasCustom <br>* Rangetop-Induction <br>* Rangetop-Induction2burner <br>* Rangetop-Induction6burner <br>* Refrigerator <br>* Refrigerator-Bar <br>* Refrigerator-Built-in <br>* Refrigerator-Built-inWithPlumbing <br>* Refrigerator-Drawer <br>* Refrigerator-SidebySide <br>* Refrigerator-Undercounter <br>* Refrigerator-WineStorage <br>* Refrigerator-WithPlumbing <br>* TrashCompactor <br>* VacuumSystem <br>* VacuumSystem-Roughin <br>* VentHood <br>* VentHood10burner <br>* VentHood6burner <br>* VentHood8burner <br>* WarmingDrawer <br>* Washer <br>* Washer-Frontload <br>* Washer-Steamer <br>* Washer-Topload <br>* Washer/DryerCombo <br>* Washer/DryerStack <br>* Water-Filter <br>* Water-InstantHot <br>* Water-Purifier <br>* Water-Softener|
| detailed_characteristics | Detailed characteristics                          | JSON Array |
| room_count               | Total rooms count                                 | Integer    |
| year_updated             | Indicates the year the property received updates  | Integer    |
| half_baths               | Indicates the half bathrooms value for a property | Integer    |

<aside class="success">
Remember — a happy request is an authenticated one!
</aside>


## Get Property

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/property?id=2214791&state=GA&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/property?id=2214791&state=GA&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/property');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  'state' => 'GA',
  'id' => 2214791,
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/property?id=2214791&state=GA&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "stateInterest": {
      "state": "GA",
      "thirtyYearFixed": 4.41,
      "thirtyYearFixedCount": 0,
      "fifteenYearFixed": 3.83,
      "fifteenYearFixedCount": 0,
      "fiveOneARM": 3.95,
      "fiveOneARMCount": 0
    },
    "isShortSale": null,
    "source": "Property Services of Atlanta,  Inc.",
    "yearBuilt": 2005,
    "nextOpenHouseEndTime": null,
    "sqft": 1566,
    "lastSaleDate": "2017-03-23 00:00:00",
    "id": 2214791,
    "state": "GA",
    "county": "DeKalb",
    "longitude": -84.51863861083984,
    "zip": 30331,
    "image": {
      "image": "http://photos.listhub.net/GAMLS/8655658/1?lm=20190908T182354",
      "url": "http://photos.listhub.net/GAMLS/8655658/1?lm=20190908T182354",
      "width": 100,
      "height": 100
    },
    "extra_images": [
      "http://photos.listhub.net/GAMLS/8655658/1?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/2?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/3?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/4?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/5?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/6?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/7?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/8?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/9?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/10?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/11?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/12?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/13?lm=20190908T182354",
      "http://photos.listhub.net/GAMLS/8655658/14?lm=20190908T182354"
    ],
    "videos": [],
    "virtual_tours": [],
    "tax": 1765,
    "mls_id": "8655658",
    "daysOnMarket": 3,
    "neighborhood": {
      "country": "United States",
      "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
      "city": "Atlanta",
      "singleHomeValue": 140000,
      "mashMeter": 67.49,
      "latitude": 33.692139,
      "description": null,
      "singleHomeValue_formatted": "$140,000",
      "is_village": false,
      "mashMeter_formatted": 67.49,
      "name": "Fairburn",
      "id": 403452,
      "state": "GA",
      "longitude": -84.522495,
      "walkscore": 14,
      "airbnb_properties_count": 6,
      "traditional_properties_count": 0
    },
    "homeType": "Single Family Residential",
    "property_type": "Residential",
    "property_sub_type": "Single Family Detached",
    "beds": 4,
    "num_of_units": null,
    "favorite": null,
    "status": "Active",
    "city": "Atlanta",
    "saleType": "MLS Listing",
    "latitude": 33.69144821166992,
    "description": "Home has covered front porch, spare bedroom and full bath with shower only on main.  Open kitchen with dining area and access to the back of the home.  Upper level has laundry closet, two spare bedrooms, full hall bath, master bedroom and master bath.   Great home for a first-time buyer or investor.   Home is all electric.   Investor owned and is being sold 'as-is' with no disclosures.  No HOA.   Tenants will be out shortly.   No showings until home is vacant.",
    "nextOpenHouseDate": null,
    "recentReductionDate": null,
    "title": "Single Family Detached, Traditional - Atlanta, GA",
    "rent_appreciation_rate": null,
    "originalListPrice": null,
    "parkingSpots": 1,
    "parkingType": "Attached",
    "address": "2333 Daniel",
    "nextOpenHouseStartTime": null,
    "lotSize": 5663,
    "broker_name": "Property Services of Atlanta,  Inc.",
    "broker_number": "(678) 384-6220",
    "broker_url": "http://www.psatlanta.com/atlanta-homes-for-sale",
    "agents": [
      {
        "id": 39995,
        "office_id": 8461
      }
    ],
    "url": "https://listings.listhub.net/pages/GAMLS/8655658/?channel=mashv",
    "baths": 3,
    "address_revealing": true,
    "location": "Fairburn",
    "interested": null,
    "listPrice": 125000,
    "price_per_sqft": 79.82120051085569,
    "lastSalePrice": 145000,
    "is_foreclosure": 0,
    "foreclosure_status": null,
    "occupancy_status": null,
    "owner_occupied": false,
    "listing_date": "2019-09-06T00:00:00.000Z",
    "heating_system": "Fireplace",
    "cooling_system": "Ceiling Fan(s)",
    "mls_name": "Georgia Multiple Listing Service",
    "hoa_dues": null,
    "view_type": null,
    "parcel_number": "14F-0032-0005-068-9",
    "architecture_style": "New Traditional",
    "has_pool": null,
    "is_water_front": null,
    "needs_repair": 0,
    "tenant_occupied": 0,
    "is_market_place": 0,
    "schools": [
      {
        "category": "Elementary",
        "name": "Deerwood Academy",
        "district": null
      },
      {
        "category": "High",
        "name": "Therrell",
        "district": null
      },
      {
        "category": "JuniorHigh",
        "name": null,
        "district": null
      },
      {
        "category": "Middle",
        "name": "Bunche",
        "district": null
      }
    ],
    "modification_timestamp": "2019-09-08T18:40:39.000Z",
    "created_at": "2019-09-09T05:23:45.000Z",
    "updated_at": "2019-09-09T05:23:45.000Z"
  }
}
```

This endpoint retrieves the property's detailed data set stored in Mashvisor database. 

### HTTP Request

`GET https://api.mashvisor.com/v2/property`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The property Id from the Mashvisor database.
state | String | | The state of the property should be provided to the api or api will throw error 404.
parcel_number | String | | Property parcel or APN
mls_id | String | | Property MLS id
address | String | | Property street address
city | String | | Property city
zip_code | String | | Property zip code

## Get Taxing

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/property/2214791/taxing?state=GA&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/property/2214791/taxing?state=GA&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/property/2214791/taxing');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  'state' => 'GA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/property/2214791/taxing?state=GA&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "tax_history": [
      {
        "year": "2007",
        "property_tax": 2427.07,
        "assessment": 57160
      },
      {
        "year": "2009",
        "property_tax": 2411.98,
        "assessment": 54200
      },
      {
        "year": "2010",
        "property_tax": 1201.29,
        "assessment": 27200
      },
      {
        "year": "2012",
        "property_tax": 810.42,
        "assessment": 18240
      },
      {
        "year": "2013",
        "property_tax": 661.82,
        "assessment": 15000
      },
      {
        "year": "2014",
        "property_tax": 843.34,
        "assessment": 18600
      },
      {
        "year": "2015",
        "property_tax": 1275.61,
        "assessment": 18600
      },
      {
        "year": "2016",
        "property_tax": 1685.51,
        "assessment": 28000
      },
      {
        "year": "2017",
        "property_tax": 1764.56,
        "assessment": 28000
      },
      {
        "year": "2018",
        "property_tax": 1764.56,
        "assessment": 31120
      }
    ]
  }
}
```

This endpoint retrieves the property's detailed data set stored in Mashvisor database. 

### HTTP Request

`GET https://api.mashvisor.com/v2/property/{id}/taxing` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The property Id from the Mashvisor database.

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.

## Get Agent

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/agents/profile/detail?id=51266&state=LA&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/agents/profile/detail?id=51266&state=LA&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/agents/profile/detail');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'id' => '51266',
  'state' => 'LA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/agents/profile/detail?id=51266&state=LA&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": 200,
    "content": {
        "agentData": {
            "id": 51266,
            "first_name": "Mary",
            "last_name": "Danna",
            "email": "mary@salepending.com",
            "primary_phone": "(504) 517-6533",
            "phone_number": "(504) 455-0100",
            "role": "Listing",
            "office_id": 6067,
            "website": "http://www.salepending.com",
            "address": "3197 RICHLAND AVENUE",
            "city": "New Orleans",
            "state": "LA",
            "county": "Jefferson",
            "zip_code": "70002",
            "company": "Keller Williams Realty 455-0100",
            "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
            "real_estate_licence": "0995689808",
            "years_of_experience": 1388534400,
            "areas_served": "[\"Covington, LA, USA\",\"Metairie, LA, USA\",\"New Orleans, LA, USA\",\"Mandeville, LA, USA\",\"Harahan, LA, USA\",\"Kenner, LA, USA\",\"Jefferson, LA, USA\",\"Gretna, LA, USA\",\"River Ridge, LA, USA\",\"Elmwood, LA, USA\"]",
            "agent_specialities": "Investment,Multifamily,Short Term Rentals,Second Homes,Luxury Homes,Single Family Residential",
            "agent_experience": ",Multifamily,Condos,Commercial,Single Family Residential,Renovations,Flips,Renovation loans,403k,Luxury,Short Term Rentals",
            "summary": "\n",
            "title": "Investment Real Estate Agent",
            "mls_id": null,
            "price_range": null,
            "sold_properties": null,
            "active_properties": null,
            "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
            "source": "Listhub",
            "created_at": "2017-02-11T09:20:00.000Z",
            "updated_at": "2019-09-09T00:36:18.000Z",
            "listhub_id": "3yd-NOMARLA-dannmary",
            "agent_id": 51266,
            "cities_serving_in": [
                {
                    "city": "Metairie",
                    "state": "LA"
                },
                {
                    "city": "New Orleans",
                    "state": "LA"
                },
                {
                    "city": "Kenner",
                    "state": "LA"
                },
                {
                    "city": "Coushatta",
                    "state": "LA"
                },
                {
                    "city": "River Ridge",
                    "state": "LA"
                }
            ],
            "office_agents": [
                {
                    "id": 43843,
                    "first_name": "TANGIE",
                    "last_name": "P STEPHENS",
                    "email": "soldbytangie@gmail.com",
                    "primary_phone": "(504) 239-1288",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2017-01-09T22:36:34.000Z",
                    "updated_at": "2019-08-01T00:42:11.000Z",
                    "listhub_id": "3yd-NOMARLA-steptang",
                    "properties_count": 249
                },
                {
                    "id": 56608,
                    "first_name": "BRITTANY",
                    "last_name": "E PICOLO-RAMOS",
                    "email": "picoloramosinfo@gmail.com",
                    "primary_phone": "(504) 251-7920",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2017-03-22T09:47:22.000Z",
                    "updated_at": "2019-03-28T12:43:35.000Z",
                    "listhub_id": "3yd-NOMARLA-picobrit",
                    "properties_count": 148
                },
                {
                    "id": 62537,
                    "first_name": "LOUIS",
                    "last_name": "R WILLIAMS",
                    "email": "louis@thewilliamsteam.com",
                    "primary_phone": "(504) 233-3374",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "St. Tammany",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2017-06-23T00:31:51.000Z",
                    "updated_at": "2019-08-20T10:01:12.000Z",
                    "listhub_id": "3yd-NOMARLA-willloui",
                    "properties_count": 126
                },
                {
                    "id": 28499,
                    "first_name": "JUDY",
                    "last_name": "B WALKER",
                    "email": "judybwalker@gmail.com",
                    "primary_phone": "(504) 251-4142",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2016-12-15T14:53:52.000Z",
                    "updated_at": "2019-03-28T12:43:35.000Z",
                    "listhub_id": "3yd-NOMARLA-walkjudy",
                    "properties_count": 109
                },
                {
                    "id": 28501,
                    "first_name": "JENNIFER",
                    "last_name": "BLANCHARD",
                    "email": "jennifer@Blanchardsells.com",
                    "primary_phone": "(504) 345-1000",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2016-12-15T14:53:58.000Z",
                    "updated_at": "2019-03-28T12:43:35.000Z",
                    "listhub_id": "3yd-NOMARLA-dazejenn",
                    "properties_count": 69
                },
                {
                    "id": 29085,
                    "first_name": "SANDY",
                    "last_name": "W DUPLESSIS",
                    "email": "sduplessis@kw.com",
                    "primary_phone": "(504) 756-7136",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2016-12-15T15:09:34.000Z",
                    "updated_at": "2019-03-28T12:43:35.000Z",
                    "listhub_id": "3yd-NOMARLA-wacksand",
                    "properties_count": 60
                },
                {
                    "id": 56757,
                    "first_name": "JOHN",
                    "last_name": "H SIBLEY",
                    "email": "john@sibleyrealestate.com",
                    "primary_phone": "(504) 457-8111",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2017-03-22T17:08:14.000Z",
                    "updated_at": "2019-03-28T12:43:35.000Z",
                    "listhub_id": "3yd-NOMARLA-sibljohn",
                    "properties_count": 57
                },
                {
                    "id": 28581,
                    "first_name": "TIFFANY",
                    "last_name": "L RIDDLE",
                    "email": "t.riddle@cox.net",
                    "primary_phone": "(504) 289-4696",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2016-12-15T14:56:26.000Z",
                    "updated_at": "2019-09-05T00:34:40.000Z",
                    "listhub_id": "3yd-NOMARLA-riddtiff",
                    "properties_count": 55
                },
                {
                    "id": 56587,
                    "first_name": "JENNIFER",
                    "last_name": "BLANCHARD",
                    "email": "Listings@blanchardsells.com",
                    "primary_phone": "(504) 345-1000",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2017-03-22T08:47:03.000Z",
                    "updated_at": "2019-05-06T00:56:23.000Z",
                    "listhub_id": "3yd-NOMARLA-dazejenn",
                    "properties_count": 51
                },
                {
                    "id": 56756,
                    "first_name": "LAURIE",
                    "last_name": "M LIONNET",
                    "email": "LaurieLionnet@kw.com",
                    "primary_phone": "(504) 462-9376",
                    "phone_number": "(504) 455-0100",
                    "role": "Listing",
                    "office_id": 6067,
                    "website": "https://kwmetairie.com",
                    "address": "3197 RICHLAND AVENUE",
                    "city": "METAIRIE",
                    "state": "LA",
                    "county": "Jefferson",
                    "zip_code": "70002",
                    "company": "KELLER WILLIAMS REALTY 455-0100",
                    "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
                    "real_estate_licence": null,
                    "years_of_experience": null,
                    "areas_served": null,
                    "agent_specialities": null,
                    "agent_experience": null,
                    "summary": null,
                    "title": null,
                    "mls_id": null,
                    "price_range": null,
                    "sold_properties": null,
                    "active_properties": null,
                    "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
                    "source": "Listhub",
                    "created_at": "2017-03-22T17:07:48.000Z",
                    "updated_at": "2019-03-28T12:43:35.000Z",
                    "listhub_id": "3yd-NOMARLA-lionlaur",
                    "properties_count": 46
                }
            ]
        },
        "agentDataConnection": "6",
        "supportedIDX": null,
        "approvedClaims": 0,
        "canEdit": false,
        "claimStatus": "NO-CLAIM"
    },
    "message": ""
}
```

This endpoint retrieves a random agent for given non-agent user.

### HTTP Request

`GET https://api-build.mashvisor.com/v2/agents/profile/detail` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.
id | Long | | The agent Id from the Mashvisor database.
name | string | | The agent full name from the Mashvisor database.
city | string | | The agent city from the Mashvisor database.

## Get Office

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/office/details?id=6067&state=LA&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/office/details?id=6067&state=LA&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/office/details');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'id' => '6067',
  'state' => 'LA',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/office/details?id=6067&state=LA&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "id": 6067,
    "phone_number": "(504) 455-0100",
    "name": "KELLER WILLIAMS REALTY 455-0100",
    "email": "lucy@kw.com",
    "website": "https://kwmetairie.com",
    "mls_id": null,
    "address": "3197 RICHLAND AVENUE",
    "city": "METAIRIE",
    "state": "LA",
    "zip_code": "70002",
    "source": "Listhub",
    "created_at": "2016-12-15T14:53:40.000Z",
    "updated_at": "2019-09-10T02:58:01.000Z",
    "agents": [
      {
        "id": 28494,
        "first_name": "SIMONE",
        "last_name": "S SOIGNET",
        "email": "simonesoignet@aol.com",
        "primary_phone": "(504) 650-6650",
        "phone_number": "(504) 455-0100",
        "role": "Listing",
        "office_id": 6067,
        "website": "https://kwmetairie.com",
        "address": "3197 RICHLAND AVENUE",
        "city": "METAIRIE",
        "state": "LA",
        "county": "Jefferson",
        "zip_code": "70002",
        "company": "KELLER WILLIAMS REALTY 455-0100",
        "image": "http://brokerlogos.listhub.net/NOMARLA/fe465471bc0111e695bc0242ac110009/20170329225736882.png",
        "real_estate_licence": null,
        "years_of_experience": null,
        "areas_served": null,
        "agent_specialities": null,
        "agent_experience": null,
        "summary": null,
        "title": null,
        "mls_id": null,
        "price_range": null,
        "sold_properties": null,
        "active_properties": null,
        "mailchimp_transfer_date": "2019-03-28T12:43:35.000Z",
        "source": "Listhub",
        "created_at": "2016-12-15T14:53:41.000Z",
        "updated_at": "2019-03-28T12:43:35.000Z",
        "listhub_id": "3yd-NOMARLA-soignets",
        "active_listings": 1
      }
    ],
    "agents_count": 353,
    "active_listings": [
      {
        "id": 717559,
        "address": "6931 MEMPHIS Street",
        "city": "New Orleans",
        "state": "LA",
        "zip": 70124,
        "county": "ORLEANS",
        "status": "Active",
        "listing_id": "2157451",
        "location": "Lake Shore-Lake Vista",
        "neighborhood_id": 276411,
        "list_price": 615000,
        "beds": 4,
        "baths": 3,
        "home_type": "Single Family Residential",
        "image_url": "http://photos.listhub.net/NOMARLA/2157451/1?lm=20190716T215155",
        "last_sale_price": null,
        "last_sale_date": null,
        "year_built": 2014
      }
    ],
    "active_listings_count": 276,
    "sold_listings": [
      {
        "id": 92573,
        "address": "1041 TCHOUPITOULAS St",
        "city": "New orleans",
        "state": "LA",
        "zip": 70130,
        "county": null,
        "status": "inactive",
        "listing_id": "2017044",
        "location": "Lower Garden District",
        "neighborhood_id": 152428,
        "list_price": 685000,
        "beds": 2,
        "baths": 3,
        "home_type": "Townhouse",
        "image_url": "http://photos.listhub.net/KW/7375144/1?lm=20170102T181554",
        "last_sale_price": 540000,
        "last_sale_date": "2012-11-14 00:00:00",
        "year_built": null
      }
    ],
    "sold_listings_count": 2651,
    "service_areas": [
      {
        "city": "New Orleans",
        "state": "LA"
      },
      {
        "city": "Kenner",
        "state": "LA"
      }
    ]
  }
}
```

This endpoint retrieves a random agent for given non-agent user.

### HTTP Request

`GET https://api.mashvisor.com/v2/property/office/details` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.
id | Long | | The office Id from the Mashvisor database.



## Get Price Estimates

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/property/estimates/664367?state=GA&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .addHeader("User-Agent", "PostmanRuntime/7.15.2")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/property/estimates/664367?state=GA&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/property/estimates/664367');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));
$request->setQueryData(array(
  'state' => 'GA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/property/estimates/664367?state=GA&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "zestimate": 129193,
        "zrental_estimate": 1350,
        "redfin_estimate": 129193
    }
}
```

This endpoint retrieves list and rental price estimation of given property. 

### HTTP Request

`GET https://api.mashvisor.com/v2/property/estimates/{pid}` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
pid | String* | | The property Id from the Mashvisor database.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | The state of the property should be provided to the api or api will throw error 404.


# Property Ownership
## The Ownership Objects

> The Contact Object:

```json
{
  "status": "success",
  "content": {
    "id": 3432,
    "first_name": "Ahmed",
    "last_name": "Hashlamon",
    "email_address": "ahmadh@mashvisor.com",
    "phone_number": "(669) 222-6396",
    "line_type": null,
    "address": null,
    "city": "Campbell",
    "state": "CA",
    "zip_code": "95008",
    "created_at": "2016-12-15T14:53:40.000Z",
    "updated_at": "2019-09-10T02:58:01.000Z"
  }
}
```

> The Demographics Object:

```json
{
  "status": "success",
  "content": {
    "dob": "24081992",
    "age_range": "25-29",
    "ethnicity": "Catholic",
    "single_parent": "Yes",
    "senior_adult_household": "Yes",
    "young_adult_household": null,
    "business_owner": "Accountant",
    "language": "English",
    "religion": "Christian",
    "number_of_children": "3",
    "presence_of_children": "Yes",
    "education": null,
    "occupation": null,
    "gender": "Male",
    "marital_status": "Married",
    "owner_renter": "Owner",
    "social_presence_indicator": "Yes"
  }
}
```

> The Lifestyle and Interests Object:

```json
{
  "status": "success",
  "content": {
    "magazines": "Yes",
    "technology": "Yes",
    "dieting_and_wellness": "Yes",
    "exercise": "Yes",
    "diy_home_improvement": "Yes",
    "jewelry": null,
    "mail_order_buyer": "Yes",
    "membership_clubs": "Yes",
    "online_education": "Yes",
    "spectator_sports": "Yes",
    "outdoor_sports": "Yes",
    "investing": null,
    "books": null,
    "political_donor": "Yes",
    "hobbies_and_crafts": "Yes",
    "cosmetics": "Yes",
    "travel": "Yes",
    "charitable_donations": "Yes",
    "arts_and_antiques": "Yes",
    "pet_owner": "Yes",
    "cooking": null,
    "diy_auto_work": "Yes",
    "health_and_beauty": "Yes",
    "parenting": null,
    "music": null,
    "film_and_movies": "Yes",
    "self_improvement": "Yes",
    "womens_apparel": "Yes"
  }
}
```

> The Financials, Household incomes, wealth score, and autos Object:

```json
{
  "status": "success",
  "content": {
    "est_household_income": "$80,000 - 100,000",
    "length_of_residence": "10 years",
    "home_purchase_date": "201770",
    "est_home_purchase_price": "$950,000-1,100,999",
    "dwelling_type": "Single Family",
    "auto_year": null,
    "number_of_credit_lines": "2",
    "auto_make": null,
    "credit_card_holder": "Yes",
    "auto_model": null,
    "est_home_value": null,
    "auto_edition": null,
    "est_net_worth": "$500,000-749,999",
    "gas_credit_card_holder": null,
    "upscale_card_holder": "Yes",
    "wealth_score": 98
  }
}
```

Mashvisor database could let find properties owners information, contact info, demographics, lifestyle, interests, finantionals and household income through data gathered sicne few years ago based on the proeprty address, parcels, or MLS ids.

### Owner Data Dictionary

| Attribute | Definition | Possible Returns |
|-------------|-------------------------------------------------------|---------------------------|
| First Name                | Owner First name                                                         | String  |
| Last Name                 | Owner Last name                                                          | String  |
| Phone Number              | Phone number, including area code                                        | Integer |
| Line Type                 | Landline or Mobile                                                       | String  |
| Email Address             | Owner email address                                                      | String  |
| Address                   | Street address                                                           | String  |
| City                      | City name                                                                | String  |
| State                     | State abbreviation                                                       | String  |
| Zip Code                  | Zip code                                                                 | Integer |
| DOB                       | A month and year of person’s born                                        | String  |
| Age Range                 | Age range of the person                                                  | String  |
| Ethnicity                 | Ethnicity of the person                                                  | String  |
| Single Parent             | Is single parent presence in household                                   | String  |
| Senior Adult Household    | Yes or null                                                              | String  |
| Young Adult Household     | Yes or null                                                              | String  |
| Business Owner            | Business owner; Accountant, Builder, Director, ..                        | String  |
| Language                  | Primary Language                                                         | String  |
| Religion                  | Person’s religion                                                        | String  |
| Number of Children        | Children within the household                                            | Integer |
| Presence of Children      | Yes or null                                                              | String  |
| Education                 | Highest level of education                                               | String  |
| Occupation                | Industry of occupation                                                   | String  |
| Gender                    | Male or Female                                                           | String  |
| Marital Status            | Single or Married                                                        | String  |
| Own/Rent                  | Own or rent household                                                    | String  |
| Social Presence Indicator | Whether the person has an account on social networks or not, Yes or null | String  |
| Magazines                 | If there’s a match, the title will be listed                             | String  |
| Technology                | If there’s a match, the title will be listed                             | String  |
| Dieting and Wellness      | If there’s a match, the title will be listed                             | String  |
| Exercise                  | If there’s a match, the title will be listed                             | String  |
| DIY Home Improvement      | If there’s a match, the title will be listed                             | String  |
| Jewelry                   | If there’s a match, the title will be listed                             | String  |
| Mail Order Buyer          | If there’s a match, the title will be listed                             | String  |
| Membership Clubs          | If there’s a match, the title will be listed                             | String  |
| Online Education          | If there’s a match, the title will be listed                             | String  |
| Spectator Sports          | If there’s a match, the title will be listed                             | String  |
| Outdoor Sports            | If there’s a match, the title will be listed                             | String  |
| Investing                 | If there’s a match, the title will be listed                             | String  |
| Books                     | If there’s a match, the title will be listed                             | String  |
| Political Donor           | If there’s a match, the title will be listed                             | String  |
| Hobbies and Crafts        | If there’s a match, the title will be listed                             | String  |
| Cosmetics                 | If there’s a match, the title will be listed                             | String  |
| Travel                    | If there’s a match, the title will be listed                             | String  |
| Charitable Donations      | If there’s a match, the title will be listed                             | String  |
| Arts and Antiques         | If there’s a match, the title will be listed                             | String  |
| Pet Owner                 | If there’s a match, the title will be listed                             | String  |
| Cooking                   | If there’s a match, the title will be listed                             | String  |
| DIY Auto work             | If there’s a match, the title will be listed                             | String  |
| Health and Beauty         | If there’s a match, the title will be listed                             | String  |
| Parenting                 | If there’s a match, the title will be listed                             | String  |
| Music                     | If there’s a match, the title will be listed                             | String  |
| Film and Movies           | If there’s a match, the title will be listed                             | String  |
| Self Improvement          | If there’s a match, the title will be listed                             | String  |
| Womens Apparel            | Yes or null                                                              | String  |
| Est. Household Income     | Estimated household income                                               | String  |
| Length of Residence       | Length of residence                                                      | String  |
| Home Purchase Date        | Estimated date of home purchase                                          | Date    |
| Est. Home Purchase Price  | Estimated price of home purchase                                         | String  |
| Dwelling Type             | Single family or multi-family                                            | String  |
| Auto year                 | Year of automobile                                                       | Integer |
| Number of credit lines    | City Number of lines of credit                                           | Integer |
| Auto make                 | Make of automobile                                                       | String  |
| Credit card holder        | Yes or null                                                              | String  |
| Auto model                | Model of automobile                                                      | String  |
| Est. Home Value           | Estimated home value                                                     | String  |
| Auto edition              | Edition of automobile                                                    | String  |
| Est. Net Worth            | Estimated net worth                                                      | String  |
| Gas credit card holder    | Yes or null                                                              | String  |
| Upscale card holder       | Yes or null                                                              | String  |
| Wealth Score              | Measure of wealth, 0 - 100                                               | Integer |

## Get Contact Info

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/owner/contact?mls_id=SF453443465&_t=meowmeowmeow&state=GA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/owner/contact?mls_id=SF453443465&_t=meowmeowmeow&state=GA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/owner/contact');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'mls_id' => 'SF453443465',
  '_t' => 'meowmeowmeow',
  'state' => 'GA'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/owner/contact?mls_id=SF453443465&_t=meowmeowmeow&state=GA"

	req, _ := http.NewRequest("GET", url, nil)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "id": 3432,
    "first_name": "Ahmed",
    "last_name": "Hashlamon",
    "email_address": "ahmadh@mashvisor.com",
    "phone_number": "(669) 222-6396",
    "line_type": null,
    "address": null,
    "city": "Campbell",
    "state": "CA",
    "zip_code": "95008",
    "created_at": "2016-12-15T14:53:40.000Z",
    "updated_at": "2019-09-10T02:58:01.000Z"
  }
}
```

This endpoint retrieves the contact info from Mashvisor for a single property owner.

### HTTP Request

`GET https://api.mashvisor.com/v2/owner/contact`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
parcel_number | String | | Property parcel or APN
mls_id | String | | Property MLS id
address | String | | Property street address
city | String | | Property city
state* | String | | Property state
zip_code | String | | Property zip code

## Get Demographics

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/owner/demographics?phone_number=+16692226396&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/owner/demographics?phone_number=+16692226396&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/owner/demographics');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'phone_number' => '+16692226396',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/owner/demographics?phone_number=+16692226396&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "dob": "24081992",
    "age_range": "25-29",
    "ethnicity": "Catholic",
    "single_parent": "Yes",
    "senior_adult_household": "Yes",
    "young_adult_household": null,
    "business_owner": "Accountant",
    "language": "English",
    "religion": "Christian",
    "number_of_children": "3",
    "presence_of_children": "Yes",
    "education": null,
    "occupation": null,
    "gender": "Male",
    "marital_status": "Married",
    "owner_renter": "Owner",
    "social_presence_indicator": "Yes"
  }
}
```

This endpoint retrieves all owner demographics by his/her full name, phone number, email address, or by a full mailing address

### HTTP Request

`GET https://api.mashvisor.com/v2/owner/demographics`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
first_name | String | | First name
last_name | String | | Last name
phone_number | String | | Person phone number
email_address | String | | Person email address
address | String | | Property street address
zip_code | String | | Property zip code
city | String | | Property city
state | String | | Property state

## Get Lifestyle and Interests

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/owner/lifeint?phone_number=+16692226396&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/owner/lifeint?phone_number=+16692226396&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/owner/lifeint');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'phone_number' => '+16692226396',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/owner/lifeint?phone_number=+16692226396&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "magazines": "Yes",
    "technology": "Yes",
    "dieting_and_wellness": "Yes",
    "exercise": "Yes",
    "diy_home_improvement": "Yes",
    "jewelry": null,
    "mail_order_buyer": "Yes",
    "membership_clubs": "Yes",
    "online_education": "Yes",
    "spectator_sports": "Yes",
    "outdoor_sports": "Yes",
    "investing": null,
    "books": null,
    "political_donor": "Yes",
    "hobbies_and_crafts": "Yes",
    "cosmetics": "Yes",
    "travel": "Yes",
    "charitable_donations": "Yes",
    "arts_and_antiques": "Yes",
    "pet_owner": "Yes",
    "cooking": null,
    "diy_auto_work": "Yes",
    "health_and_beauty": "Yes",
    "parenting": null,
    "music": null,
    "film_and_movies": "Yes",
    "self_improvement": "Yes",
    "womens_apparel": "Yes"
  }
}
```

This endpoint retrieves all owner lifestyle and interests by his/her full name, phone number, email address, or by a full mailing address.

### HTTP Request

`GET https://api.mashvisor.com/v2/owner/lifeint`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
first_name | String | | First name
last_name | String | | Last name
phone_number | String | | Person phone number
email_address | String | | Person email address
address | String | | Property street address
zip_code | String | | Property zip code
city | String | | Property city
state | String | | Property state

## Get Financials, Household Incomes

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/owner/finhouse?phone_number=+16692226396&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/owner/finhouse?phone_number=+16692226396&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/owner/finhouse');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'phone_number' => '+16692226396',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/owner/finhouse?phone_number=+16692226396&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "est_household_income": "$80,000 - 100,000",
    "length_of_residence": "10 years",
    "home_purchase_date": "201770",
    "est_home_purchase_price": "$950,000-1,100,999",
    "dwelling_type": "Single Family",
    "auto_year": null,
    "number_of_credit_lines": "2",
    "auto_make": null,
    "credit_card_holder": "Yes",
    "auto_model": null,
    "est_home_value": null,
    "auto_edition": null,
    "est_net_worth": "$500,000-749,999",
    "gas_credit_card_holder": null,
    "upscale_card_holder": "Yes",
    "wealth_score": 98
  }
}
```

This endpoint retrieves all owner financials, household incomes, and wealth score by his/her full name, phone number, email address, or by a full mailing address.

### HTTP Request

`GET https://api.mashvisor.com/v2/owner/finhouse`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
first_name | String | | First name
last_name | String | | Last name
phone_number | String | | Person phone number
email_address | String | | Person email address
address | String | | Property street address
zip_code | String | | Property zip code
city | String | | Property city
state | String | | Property state

# Investment Analysis
## The Investment Performance Object

> The Investment Performance Object:

```json
{
  "principle_with_interest": null,
  "traditional": {
      "occupancy": 93.9,
      "cash_flow": 698.3238000000001,
      "roi": 103.4553777777778,
      "cap_rate": 9.53343071672355,
      "rental_income": 1450.755,
      "maintenance_cost": 73.25,
      "traditional_utilities": 170,
      "management_cost": 145.0755,
      "traditional_property_tax": 70,
      "traditional_home_owner_insurance": 91,
      "cleaningFees": 0,
      "traditional_rental_income_tax": 203.10570000000004,
      "total_expenses": 752.4312,
      "traditional_other": 0,
      "hoa_dues": 0,
      "expenses_details": {
          "utilities": {
              "expenses": {
                  "trash": null,
                  "water": null,
                  "cable": null,
                  "electricity": null,
                  "fuel": null
              },
              "sum": 0
          }
      }
  },
  "airbnb": {
      "occupancy": 60.5,
      "cash_flow": 1450.4772222222225,
      "roi": 214.88551440329223,
      "cap_rate": 19.80173682214638,
      "rental_income": 2440.4305555555557,
      "maintenance_cost": 73.25,
      "airbnb_utilities": 170,
      "management_cost": 244.04305555555558,
      "airbnb_property_tax": 70,
      "airbnb_home_owner_insurance": 91,
      "airbnb_rental_income_tax": 341.6602777777778,
      "cleaningFees": 0,
      "total_expenses": 989.9533333333334,
      "airbnb_other": 0,
      "hoa_dues": 0,
      "expenses_details": {
          "utilities": {
              "expenses": {
                  "trash": null,
                  "water": null,
                  "cable": null,
                  "electricity": null,
                  "fuel": null
              },
              "sum": 0
          }
      }
  },
  "property_tax": 70
}
```

### Property Data Dictionary
| Attribute | Definition | Possible Returns |
|-------------|-------------------------------------------------------|---------------------------|
| Traditional Rental       | The expected monthly rent if the property is rented out traditionally (long-term rental) | Double |
| Traditional ROI          | Measures the returns of a property based on the amount of cash put down: (Cash Flow X 12 Months X 100)/Total Cash Invested                                                                            | Double |
| Traditional Cap Rate     | Measures the expected income and potential return of a property; does not take property financing into consideration, gives return as if property is paid off: (Cash Flow X 12 Months)/Property Price | Double |
| Traditional Vacancy Rate | The expected number of days the property won’t be reserved/rented per year.                                                                                                                           | Double |
| AirBnB Rental            | The expected monthly rent if the property is listed on Airbnb (short-term vacation rental) versus if the property is rented out traditionally (long-term rental)                                      | Double |
| AirBnB ROI               | Measures the returns of a property based on the amount of cash put down: (Cash Flow X 12 Months X 100)/Total Cash Invested                                                                            | Double |
| AirBnB Cap Rate          | Measures the expected income and potential return of a property; does not take property financing into consideration, gives return as if property is paid off: (Cash Flow X 12 Months)/Property Price | Double |
| AirBnB Occupancy         | The expected number of days the property will be reserved/rented per year. num of days per year, or a percentage Based on "is_days" param, eg: 70 as a percentage, or 150 as days| Double |
| Down Payment | Down payment | Integer |
| Loan Type | Loan type | Integer |
| Interest Rate| Interest rate | Double |
| Payment Type| loan, or cash | String <br>Default: cash |
| Traditional Occupancy| num of days per year, or a percentage Based on "is_days" param, eg: 70 as a percentage, or 150 as days | Double |
| Is Days| If it's set to 0, the "traditional_occupancy" is considered as a percentage, if it's 1, it's considered as num of days per year | Integer <br> Default: 0 |
| Max Bid| Sets the property listing price to its value | Integer |
| Traditional Maintenance Cost| Sets the traditional maintenance cost, e.g: 250 | Double |
| Airbnb Maintenance Cost| Sets the airbnb maintenance cost, e.g: 230 | Double |
| Traditional Management Cost| Sets the traditional management cost, e.g: 130 | Double |
| Airbnb Management Cost| Sets the airbnb management cost, e.g: 120 | Double |
| Airbnb Property Tax| Sets the airbnb property tax value, e.g: 1705 | Float |
| Traditional Property Tax| Sets the traditional property tax value, e.g: 1705 | Float |
| Airbnb Home Owner Insurance | Sets the airbnb home owner insurance cost, e.g: 83 | Integer |
| Traditional Home Owner Insurance | Sets the traditional home owner insurance cost, e.g: 83 | Integer |
| Airbnb Total Expenses| Sets the airbnb total expenses, e.g: 1700 | Double  |
| Traditional Total Expenses | Sets the traditional total expenses, e.g: 1900 | Double |
| Startup Cost | First time costs, paid only once | Integer <br>Default: 8000 | 

## Get Investment Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/property/664367/investment?state=GA&payment_type=loan&interest_rate=0.5&loan_type=1&down_payment=100&valuation_score=true")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/property/664367/investment?state=GA&payment_type=loan&interest_rate=0.5&loan_type=1&down_payment=100&valuation_score=true",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/property/664367/investment');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));
$request->setQueryData(array(
  'state' => 'GA',
  'payment_type' => 'loan',
  'interest_rate' => '0.5',
  'loan_type' => '1',
  'down_payment' => '100',
  'valuation_score' => 'true'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/property/664367/investment?state=GA&payment_type=loan&interest_rate=0.5&loan_type=1&down_payment=100&valuation_score=true"

	req, _ := http.NewRequest("GET", url, nil)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "6dc17686-8955-e00f-f0bb-d8f60f49a16b")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "principle_with_interest": 7336.497772930145,
        "traditional": {
            "occupancy": 92.1,
            "traditional_night_price": "1900.0000",
            "cash_flow": -6077.390356263478,
            "roi": -900.3541268538486,
            "cap_rate": 17.189179749715592,
            "rental_income": 1749.9000000000003,
            "maintenance_cost": 73.25,
            "management_cost": 104.99400000000001,
            "traditional_home_owner_insurance": 83.33333333333333,
            "traditional_property_tax": 86.21525000000001,
            "total_expenses": 7828.290356263478,
            "hoa_dues": 0
        },
        "airbnb": {
            "occupancy": "60.0000",
            "airbnb_night_price": "212.0000",
            "cash_flow": -4085.4363562634785,
            "rental_income": 3869,
            "roi": -605.2498305575523,
            "cap_rate": 44.38309101251422,
            "maintenance_cost": 73.25,
            "management_cost": 232.14,
            "airbnb_home_owner_insurance": 83.33333333333333,
            "airbnb_property_tax": 86.21525000000001,
            "total_expenses": 7955.436356263479,
            "hoa_dues": 0
        },
        "property_tax": 86.21525000000001,
    }
}
```

This endpoint retrieves the property's investment performance. 

### HTTP Request

`GET https://api.mashvisor.com/v2/property/{id}/investment`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The property Id from the Mashvisor database.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.
down_payment | Integer | | Down payment
loan_type | Integer | | Loan type
interest_rate | Double | | Interest rate
payment_type | String | | loan, cash
airbnb_rental | Double | | Monthly Airbnb rental income, ex: 2000
traditional_rental | Double | | Monthly traditional rental income, ex: 1700
airbnb_occupancy | Double | |  num of days per year, or a percentage Based on "is_days" param, eg: 70 as a percentage, or 150 as days
traditional_occupancy | Double | |  num of days per year, or a percentage Based on "is_days" param, eg: 70 as a percentage, or 150 as days
is_days | Integer | 0 | If it's set to 0, the "traditional_occupancy" is considered as a percentage, if it's 1, it's considered as num of days per year
max_bid | Integer | | Sets the property listing price to its value
traditional_maintenance_cost | Double | | Sets the traditional maintenance cost, e.g: 250
airbnb_maintenance_cost | Double | | Sets the airbnb maintenance cost, e.g: 230
traditional_management_cost | Double | | Sets the traditional management cost, e.g: 130
airbnb_management_cost | Double | | Sets the airbnb management cost, e.g: 120
airbnb_property_tax | Float | | Sets the airbnb property tax value, e.g: 1705
traditional_property_tax | Float | | Sets the traditional property tax value, e.g: 1705
airbnb_home_owner_insurance | Integer | | Sets the airbnb home owner insurance cost, e.g: 83
traditional_home_owner_insurance | Integer | | Sets the traditional home owner insurance cost, e.g: 83
airbnb_total_expenses | Double | | Sets the airbnb total expenses, e.g: 1700
traditional_total_expenses | Double | | Sets the traditional total expenses, e.g: 1900
valuation_score | Boolean | false | If true, gets the property valuation score
startup_cost | Integer | 8000 | 

## Get Investment Breakdown

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/property/664367/investment/breakdown?state=GA&startup_cost=39000&recurring_cost=200&turnover_cost=200")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/property/664367/investment/breakdown?state=GA&startup_cost=39000&recurring_cost=200&turnover_cost=200",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/property/664367/investment/breakdown');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));
$request->setQueryData(array(
  'state' => 'GA',
  'startup_cost' => '39000',
  'recurring_cost' => '200',
  'turnover_cost' => '200'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/property/664367/investment/breakdown?state=GA&startup_cost=39000&recurring_cost=200&turnover_cost=200"

	req, _ := http.NewRequest("GET", url, nil)

  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")
	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "strategy": "Airbnb",
        "breakdown": [
            {
                "month": 1,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 35925
            },
            {
                "month": 2,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 32850
            },
            {
                "month": 3,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 29775
            },
            {
                "month": 4,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 26700
            },
            {
                "month": 5,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 23625
            },
            {
                "month": 6,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 20550
            },
            {
                "month": 7,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 17475
            },
            {
                "month": 8,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 14400
            },
            {
                "month": 9,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 11325
            },
            {
                "month": 10,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 8250
            },
            {
                "month": 11,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 5175
            },
            {
                "month": 12,
                "gross_rental_revenue": 6448,
                "cleaning_fee_collected": 300,
                "vacancy": 2579,
                "airbnb_hosting_fee": 193.44,
                "adjusted_gross_income": 3975.56,
                "net_rents": 3576,
                "yield_on_investment": 7.884615384615384,
                "balance": 2100
            }
        ],
        "avg_occupancy": 0.6,
        "days_leased_per_month": 18,
        "avg_daily_leased_rate": 212,
        "airbnb_tax": 501,
        "cash_flow": 3075,
        "net_operating_income": 3075,
        "rental_yield": 41.979522184300336,
        "annually_breakdown": [
            {
                "year": 1,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": 2100
            },
            {
                "year": 2,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -34800
            },
            {
                "year": 3,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -71700
            },
            {
                "year": 4,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -108600
            },
            {
                "year": 5,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -145500
            },
            {
                "year": 6,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -182400
            },
            {
                "year": 7,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -219300
            },
            {
                "year": 8,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -256200
            },
            {
                "year": 9,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -293100
            },
            {
                "year": 10,
                "gross_rental_revenue": 77376,
                "cleaning_fee_collected": 3600,
                "vacancy": 30951.9993216,
                "airbnb_hosting_fee": 2321.2799999999997,
                "adjusted_gross_income": 47706.72,
                "net_rents": 42912,
                "yield_on_investment": 7.884615384615384,
                "balance": -330000
            }
        ]
    }
}
```

This endpoint retrieves the property's investment breakdown performance for Airbnb or Traditional. 

### HTTP Request

`GET https://api.mashvisor.com/v2/property/{id}/investment/breakdown`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The property Id from the Mashvisor database.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.
airbnb_rental | Double | | Monthly Airbnb rental income, ex: 2000
traditional_rental | Double | | Monthly traditional rental income, ex: 1700
airbnb_occupancy | Double | |  num of days per year, or a percentage Based on "is_days" param, eg: 70 as a percentage, or 150 as days
traditional_occupancy | Double | |  num of days per year, or a percentage Based on "is_days" param, eg: 70 as a percentage, or 150 as days
is_days | Integer | 0 | If it's set to 0, the "traditional_occupancy" is considered as a percentage, if it's 1, it's considered as num of days per year
max_bid | Integer | | Sets the property listing price to its value
startup_cost | Double | 8000 | Startup cost for the investment, e.x: 8000
source | String | Airbnb | Defines the monthly calculations should be calculated for "Airbnb" or "Traditional"
recurring_cost | Double | | Recurring cost of the investment strategy, ex: 1435
turnover_cost | Double | | Turnover cost


## Get Property Marker

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/property/marker?state=CA&pid=2207289&type=Investment&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/property/marker?state=CA&pid=2207289&type=Investment&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/property/marker');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'pid' => '2207289',
  'type' => 'Investment',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/property/marker?state=CA&pid=2207289&type=Investment&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "id": 2207289,
        "neighborhood": {
            "id": 417524,
            "name": "Buena Vista Park"
        },
        "address": "110 Alpine Terrace",
        "city": "San Francisco",
        "state": "CA",
        "listPrice": 1695000,
        "ROI": {
            "airbnb_ROI": 0.620426,
            "traditional_ROI": -0.208019
        },
        "Cap": {
            "airbnb_Cap": 0.620426,
            "traditional_Cap": -0.208019
        }
    }
}
```

This endpoint retrieves snapshot data about a specific property.

### HTTP Request

`GET https://api.mashvisor.com/v2/property/marker`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
pid | Long | | The property Id from the Mashvisor database.
state | String | | The state of the property should be provided to the api or API will throw error 404.
type | String | | Investment, Airbnb, or Traditional 
payment | String | CASH | CASH, or LOAN 
downPayment | Integer | | The downpayment for mortgage calculations, e.g: 40000
loanType | Integer | | The loan type, e.g: 30
interestRate | Double | | The interest rate for mortgage, e.g: 3.51 

## Get Airbnb Comparable Listings

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/neighborhood/269590/airbnb/details?state=IL&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/neighborhood/269590/airbnb/details?state=IL&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/neighborhood/269590/airbnb/details');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));
$request->setQueryData(array(
  'state' => 'IL',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/neighborhood/269590/airbnb/details?state=IL&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "properties": [
            {
                "id": 21131720,
                "propertyId": "20992111",
                "source": "Airbnb",
                "status": "ACTIVE",
                "nightPrice": 235,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 2,
                "numOfRooms": 4,
                "occupancy": 56,
                "rentalIncome": 3948,
                "airbnbNeighborhoodId": 397651,
                "name": "Perfect getaway in the Hudson Valley",
                "address": "Red Hook, NY, United States",
                "airbnbNeighborhood": null,
                "airbnbCity": "Red Hook",
                "state": "NY",
                "capacityOfPeople": 6,
                "zip": "12571",
                "propertyType": "House",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 16,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2019-08-19T16:00:19.000Z",
                "updatedAt": "2019-08-19T16:00:19.000Z",
                "numOfBeds": 4,
                "lat": 41.9516716003418,
                "lon": -73.77474975585938,
                "image": "https://a0.muscache.com/im/pictures/883b6146-c323-45f7-a3c0-3339b36c3fbd.jpg?aki_policy=medium",
                "url": null,
                "rental_income": 3948.0000000000005,
                "neighborhood": {
                    "id": 397651,
                    "name": null
                },
                "nightRate": 235,
                "property_id": "20992111",
                "airbnbZIP": "12571",
                "distance": 6.204173070158869,
                "similarity": 0.5
            },
            {
                "id": 21131669,
                "propertyId": "15235032",
                "source": "Airbnb",
                "status": "ACTIVE",
                "nightPrice": 268,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1.5,
                "numOfRooms": 2,
                "occupancy": 84,
                "rentalIncome": 6754,
                "airbnbNeighborhoodId": 397651,
                "name": "Modern Upstate NY cabin + hot pool in the woods.",
                "address": "Red Hook, NY, United States",
                "airbnbNeighborhood": null,
                "airbnbCity": "Red Hook",
                "state": "NY",
                "capacityOfPeople": 6,
                "zip": "12571",
                "propertyType": "Cabin",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 90,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2019-08-19T15:59:49.000Z",
                "updatedAt": "2019-08-19T15:59:49.000Z",
                "numOfBeds": 3,
                "lat": 42.00767135620117,
                "lon": -73.7533187866211,
                "image": "https://a0.muscache.com/im/pictures/b0831a76-9ea9-4e45-97f1-29edab749b27.jpg?aki_policy=medium",
                "url": null,
                "rental_income": 6753.599999999999,
                "neighborhood": {
                    "id": 397651,
                    "name": null
                },
                "nightRate": 268,
                "property_id": "15235032",
                "airbnbZIP": "12571",
                "distance": 4.958961405286708,
                "similarity": 0.48
            },
            {
                "id": 21131735,
                "propertyId": "5602615",
                "source": "Airbnb",
                "status": "ACTIVE",
                "nightPrice": 965,
                "weeklyPrice": 4000,
                "monthlyPrice": 10000,
                "numOfBaths": 2.5,
                "numOfRooms": 4,
                "occupancy": 21,
                "rentalIncome": 6080,
                "airbnbNeighborhoodId": 397651,
                "name": "Lovely Hudson Valley Country Home",
                "address": "Red Hook, NY, United States",
                "airbnbNeighborhood": null,
                "airbnbCity": "Red Hook",
                "state": "NY",
                "capacityOfPeople": 8,
                "zip": "12571",
                "propertyType": "House",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 23,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2019-08-19T16:00:26.000Z",
                "updatedAt": "2019-08-19T16:00:26.000Z",
                "numOfBeds": 4,
                "lat": 42.0384407043457,
                "lon": -73.8933334350586,
                "image": "https://a0.muscache.com/im/pictures/98264481/28aadc99_original.jpg?aki_policy=medium",
                "url": null,
                "rental_income": 6079.5,
                "neighborhood": {
                    "id": 397651,
                    "name": null
                },
                "nightRate": 965,
                "property_id": "5602615",
                "airbnbZIP": "12571",
                "distance": 2.569544555210685,
                "similarity": 0.53
            }
        ],
        "num_of_properties": 23,
        "avg_occupancy": 45.913,
        "avg_price": 296.1304,
        "num_page_properties": 3,
        "page": "3"
    }
}
```

This endpoint retrieves the Airbnb neighborhood's listing data set in Mashvisor database with similiraty and distnace regarding the target MLS property.

### HTTP Request

`GET https://api.mashvisor.com/v2/neighborhood/{id}/airbnb/details`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.
page | Integer | 1 | Page number
items | Integer | 3 | items number
bedrooms | Integer | | bedrooms number
pid | Long | | Property to fetch comparble listings for.
sort_by | String | | Sorting type. <br>Possible input: <br> * name<br> * similarity<br> * distance<br> * address<br> * occupancy<br> * night_price<br> * rental_income<br> * num_of_baths<br> * num_of_rooms<br> * reviews_count
order | String | desc | Order type: desc, or asc
format | String | json | json, or xml

## Get Traditional Comparable Listings

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/neighborhood/397651/traditional/listing?_t=meowmeowmeow&format=json&items=9&order=desc&page=1&pid=325215&sort_by=address&state=ny")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/neighborhood/397651/traditional/listing?_t=meowmeowmeow&format=json&items=9&order=desc&page=1&pid=325215&sort_by=address&state=ny",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/neighborhood/397651/traditional/listing');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  '_t' => 'meowmeowmeow',
  'format' => 'json',
  'order' => 'desc',
  'pid' => '325215',
  'state' => 'ny',
  'items' => '4',
  'page' => '8',
  'sort_by' => 'address'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/neighborhood/397651/traditional/listing?_t=meowmeowmeow&format=json&items=9&order=desc&page=1&pid=325215&sort_by=address&state=ny"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "results": [
            {
                "id": 6699070,
                "title": "2-4 Family, Other - Red Hook, NY",
                "lon": -73.84407806396484,
                "lat": 42.02531051635742,
                "state": "NY",
                "city": "Red Hook",
                "county": "DUTCHESS COUNTY",
                "neighborhood": "Red Hook",
                "description": "This 4 BR/2 BA early Red Hook settlement colonial has just been beautifully renovated incorporating authentic period details while accentuating modern upgrades with charm & character. Spacious, light-filled rooms include a large eat-in kitchen with washer & dryer, a connected sunroom, formal living & dining rooms, separate studio or home office as well as a second-floor landing reading nook with built-in bookshelves. TERMS: 1st-month rent, last month rent, 1-month security deposit, 1/2 month broker's commission. Pets at the owner's discretion. Non-smoking residence. 12-month lease. Landlord provides lawn maintenance, snow plowing, garbage removal, and off-street parking. Available 8/1/19.",
                "price": 2300,
                "baths": 2,
                "beds": 4,
                "num_of_units": null,
                "sqft": 2600,
                "lot_size": 28314,
                "days_on_market": 26,
                "year_built": 1810,
                "tax": null,
                "tax_history": null,
                "videos": null,
                "virtual_tours": null,
                "parking_spots": null,
                "parking_type": "Off Street",
                "walkscore": null,
                "mls_id": "382940",
                "image": "http://photos.listhub.net/MIDHNY/382940/1?lm=20190628T235242",
                "extra_images": "http://photos.listhub.net/MIDHNY/382940/1?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/2?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/3?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/4?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/5?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/6?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/7?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/8?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/9?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/10?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/11?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/12?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/13?lm=20190628T235242,http://photos.listhub.net/MIDHNY/382940/14?lm=20190628T235242",
                "zipcode": "12571",
                "address": "14 SPRING LAKE RD",
                "type": "Other",
                "property_type": "Rental",
                "property_sub_type": "Other",
                "status": "rented",
                "listhub_key": "3yd-MIDHNY-382940",
                "broker_name": "GARY DiMAURO REAL ESTATE, INC.",
                "broker_number": "845 7575000",
                "broker_url": "http://www.garydimauro.com",
                "source": "GARY DiMAURO REAL ESTATE, INC.",
                "mls_name": "Mid-Hudson Multiple Listing Service",
                "original_source": "Listhub",
                "architecture_style": "Other",
                "has_pool": null,
                "is_water_front": null,
                "heating_system": "Forced Air",
                "cooling_system": "None",
                "view_type": null,
                "schools": "[{\"category\":\"Elementary\",\"name\":\"Mill Road - Primary Grades\",\"district\":\"Red Hook Central\"},{\"category\":\"High\",\"name\":\"Red Hook Senior High School\",\"district\":\"Red Hook Central\"},{\"category\":\"JuniorHigh\",\"name\":null,\"district\":\"Red Hook Central\"},{\"category\":\"Middle\",\"name\":\"Linden Avenue Middle School\",\"district\":\"Red Hook Central\"}]",
                "parcel_number": "13488900637300012828230000",
                "neighborhood_id": 397651,
                "url": "https://listings.listhub.net/pages/MIDHNY/382940/?channel=mashv",
                "listing_date": "2019-06-28T00:00:00.000Z",
                "modification_timestamp": "2019-07-13T00:18:44.000Z",
                "created_at": "2019-06-30T01:04:43.000Z",
                "updated_at": "2019-07-24T04:27:49.000Z",
                "distance": 0.2280876552393839,
                "similarity": 0.45
            },
            {
                "id": 6584461,
                "title": "Single Family Detached, Ranch - V. Red Hook, NY",
                "lon": -73.87642669677734,
                "lat": 42.00033187866211,
                "state": "NY",
                "city": "Red Hook",
                "county": null,
                "neighborhood": "Red Hook",
                "description": "If you are looking for a home on a beautiful quiet street in the Village, across from a walking park, near rec park, and within a short distance to the center of the village, then check out this 4 bedroom, 2 full bathroom home. Owner has just made many updates and the home is fresh and waiting for the next tenant. Includes use of unfinished basement that contains a drive under garage and a laundry/utility. Does not include finished part of basement that the owner uses for storage. Nice yard to chill out in the summer, enough space for the kids to play outside. Qualified applicants only.",
                "price": 2300,
                "baths": 2,
                "beds": 4,
                "num_of_units": null,
                "sqft": 1435,
                "lot_size": null,
                "days_on_market": null,
                "year_built": 1950,
                "tax": null,
                "tax_history": null,
                "videos": null,
                "virtual_tours": null,
                "parking_spots": null,
                "parking_type": null,
                "walkscore": null,
                "mls_id": "376976",
                "image": "http://photos.listhub.net/MIDHNY/376976/1?lm=20181128T224222",
                "extra_images": null,
                "zipcode": "12571",
                "address": "14 PARK AVENUE",
                "type": "single_home",
                "property_type": null,
                "property_sub_type": null,
                "status": "rented",
                "listhub_key": "3yd-MIDHNY-376976",
                "broker_name": "Berkshire Hathaway HomeServices Hudson Valley Properties",
                "broker_number": "(845) 905-8747",
                "broker_url": null,
                "source": "Berkshire Hathaway HomeServices Hudson Valley Properties",
                "mls_name": null,
                "original_source": null,
                "architecture_style": null,
                "has_pool": null,
                "is_water_front": null,
                "heating_system": null,
                "cooling_system": null,
                "view_type": null,
                "schools": null,
                "parcel_number": null,
                "neighborhood_id": 397651,
                "url": "https://listings.listhub.net/pages/MIDHNY/376976/?channel=mashv",
                "listing_date": null,
                "modification_timestamp": null,
                "created_at": "2018-11-30T01:21:38.000Z",
                "updated_at": "2019-03-08T01:34:44.000Z",
                "distance": 2.1697949933012572,
                "similarity": 0.6
            },
            {
                "id": 6756141,
                "title": "2-4 Family, Other - Red Hook, NY",
                "lon": -73.84525299072266,
                "lat": 42.03054809570313,
                "state": "NY",
                "city": "Red Hook",
                "county": "DUTCHESS COUNTY",
                "neighborhood": "Red Hook",
                "description": "This tree top apartment in an 1860 School House is flooded with light. The high ceiling, many windows and open floor plan provides a wonderful living space. The main floor offers a bedroom, office or library, kitchen great room and bath. The upper floor is an open, expansive loft which opens to a small exterior deck. Plenty of closets for storage and hard wood floors through out. Great location with easy access to the Village of Red Hook, Bard College and Greig Farm.",
                "price": 1450,
                "baths": 1,
                "beds": 2,
                "num_of_units": null,
                "sqft": 1100,
                "lot_size": 16988,
                "days_on_market": 6,
                "year_built": 1860,
                "tax": null,
                "tax_history": null,
                "videos": null,
                "virtual_tours": null,
                "parking_spots": null,
                "parking_type": "Off Street",
                "walkscore": null,
                "mls_id": "384191",
                "image": "http://photos.listhub.net/MIDHNY/384191/1?lm=20190905T215337",
                "extra_images": "http://photos.listhub.net/MIDHNY/384191/1?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/2?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/3?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/4?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/5?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/6?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/7?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/8?lm=20190905T215337,http://photos.listhub.net/MIDHNY/384191/9?lm=20190905T215337",
                "zipcode": "12571",
                "address": "123 OLD POST ROAD NORTH #B",
                "type": "Other",
                "property_type": "Rental",
                "property_sub_type": "Other",
                "status": "Active",
                "listhub_key": "3yd-MIDHNY-384191",
                "broker_name": "PAULA REDMOND LIC. R.E. BKR",
                "broker_number": "518 3983030",
                "broker_url": "http://www.paularedmond.com",
                "source": "PAULA REDMOND LIC. R.E. BKR",
                "mls_name": "Mid-Hudson Multiple Listing Service",
                "original_source": "Listhub",
                "architecture_style": "Other",
                "has_pool": null,
                "is_water_front": null,
                "heating_system": "Hot Water (Oil)",
                "cooling_system": "None",
                "view_type": null,
                "schools": "[{\"category\":\"Elementary\",\"name\":\"Mill Road - Primary Grades\",\"district\":\"Red Hook Central\"},{\"category\":\"High\",\"name\":\"Red Hook Senior High School\",\"district\":\"Red Hook Central\"},{\"category\":\"JuniorHigh\",\"name\":null,\"district\":\"Red Hook Central\"},{\"category\":\"Middle\",\"name\":\"Linden Avenue Middle School\",\"district\":\"Red Hook Central\"}]",
                "parcel_number": "13488900637400002520120000",
                "neighborhood_id": 397651,
                "url": "https://listings.listhub.net/pages/MIDHNY/384191/?channel=mashv",
                "listing_date": "2019-09-05T00:00:00.000Z",
                "modification_timestamp": "2019-09-06T03:19:16.000Z",
                "created_at": "2019-09-07T04:20:03.000Z",
                "updated_at": "2019-09-11T04:08:44.000Z",
                "distance": 0.5151012639728284,
                "similarity": 0.38
            },
            {
                "id": 3035205,
                "title": "2-4 Family, Other - Red Hook, NY",
                "lon": -73.84519958496094,
                "lat": 42.03060150146484,
                "state": "NY",
                "city": "Red Hook",
                "county": null,
                "neighborhood": "Red Hook",
                "description": "Built in 1860 and once the local school house this renovated 2nd floor tree top apartment offers very large windows, high ceilings, hard wood floors, sky lights with a lovely open floor plan. Located in the hamlet of Upper Red Hook, with easy access to Bard and the Village of Red Hook.",
                "price": 1400,
                "baths": 2,
                "beds": 2,
                "num_of_units": null,
                "sqft": 950,
                "lot_size": null,
                "days_on_market": null,
                "year_built": 1860,
                "tax": null,
                "tax_history": null,
                "videos": null,
                "virtual_tours": null,
                "parking_spots": null,
                "parking_type": null,
                "walkscore": null,
                "mls_id": "379210",
                "image": "http://photos.listhub.net/MIDHNY/379210/1?lm=20190312T194736",
                "extra_images": null,
                "zipcode": "12571",
                "address": "123 N OLD POST ROAD #A",
                "type": "Other",
                "property_type": null,
                "property_sub_type": null,
                "status": "rented",
                "listhub_key": "3yd-MIDHNY-379210",
                "broker_name": "PAULA REDMOND LIC. R.E. BKR",
                "broker_number": "518 3983030",
                "broker_url": null,
                "source": "PAULA REDMOND LIC. R.E. BKR",
                "mls_name": null,
                "original_source": null,
                "architecture_style": null,
                "has_pool": null,
                "is_water_front": null,
                "heating_system": null,
                "cooling_system": null,
                "view_type": null,
                "schools": null,
                "parcel_number": null,
                "neighborhood_id": 397651,
                "url": "https://listings.listhub.net/pages/MIDHNY/379210/?channel=mashv",
                "listing_date": null,
                "modification_timestamp": null,
                "created_at": "2017-11-03T01:13:44.000Z",
                "updated_at": "2019-04-09T01:09:43.000Z",
                "distance": 0.5193335664792641,
                "similarity": 0.4
            }
        ],
        "total_results": 35,
        "total_pages": 9,
        "current_page": "8"
    }
}
```

This endpoint retrieves the traditional neighborhood's listing data set in Mashvisor database with similiraty and distnace regarding the target MLS property.

### HTTP Request

`GET https://api.mashvisor.com/v2/neighborhood/{id}/traditional/listing`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.
page | Integer | 1 | Page number
items | Integer | 3 | items number
category | Integer | | bedrooms number
min_price | Integer | | min_price of rental value
max_price | Integer | | max_price of rental value
pid | Long | | Property to fetch comparble listings for.
sort_by | String | | Sorting type. <br>Possible input: <br> * address<br> * similarity<br> * distance<br> * beds<br> * baths<br> * price
order | String | desc | Order type: desc, or asc
format | String | json | json, or xml

# Rental Rates
## The Rental Rates Object

> The Rental Rates Object:

```json
{
  "retnal_rates": {
    "studio_value": 2057.364054361979,
    "one_room_value": 2093.0895256629356,
    "two_room_value": 2688.2876882245464,
    "three_room_value": 3611.8709511828065,
    "four_room_value": 3241.519084257238
  }
}
```

### Property Data Dictionary
| Attribute 	   | Definition															  | Possible Returns |
|------------------|----------------------------------------------------------------------|------------------|
| Studio Value     | The expected monthly rent if a studio property is rented out         | Double			 |
| One Rroom Value  | The expected monthly rent if a one bedroom property is rented out    | Double			 |
| Two Room Value   | The expected monthly rent if a two bedrooms property is rented out   | Double			 |
| Three Room Value | The expected monthly rent if a three bedrooms property is rented out | Double			 |
| Four Room Value  | The expected monthly rent if a four bedrooms property is rented out  | Double			 |

Mashvisor API lets you find out an estiamted rental rate for a specific location eaither for long term rentals (traditional way), or for short term rentals (Airbnb, VRBO, or Homeaway).
These estiamtes categorized by the number of bedrooms of a property you're trying to get the estimates for.
The estimates are based on 12 months historical performance for the target area, and they are calculated over several similar listings was rented in the area, or currently avaialble for renting. 

## Get Rental Rates
```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/rental-rates?_t=meowmeowmeow&city=Chicago&state=IL&neighborhood=138261&source=airbnb")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/rental-rates?_t=meowmeowmeow&city=Chicago&state=IL&neighborhood=138261&source=airbnb",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/neighborhood/rental-rates');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  '_t' => 'meowmeowmeow',
  'city' => 'Chicago',
  'state' => 'IL',
  'neighborhood' => '138261',
  'source' => 'airbnb'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/rental-rates?_t=meowmeowmeow&city=Chicago&state=IL&neighborhood=138261&source=airbnb"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "retnal_rates": {
    "studio_value": 2057.364054361979,
    "one_room_value": 2093.0895256629356,
    "two_room_value": 2688.2876882245464,
    "three_room_value": 3611.8709511828065,
    "four_room_value": 3241.519084257238
  }
}
```

This endpoint retrieves the traditional neighborhood's listing data set in Mashvisor database with similiraty and distnace regarding the target MLS property.

### HTTP Request

`GET https://api.mashvisor.com/v2/rental-rates`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.
source | String | | Targeting service to fetch estiamtes for.<br>Possible inputs: <br>* airbnb<br>* traditional

# Predictive Scores

## Investment Liklihood

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n  \"airbnb_ROI\": 9.33728,\n  \"airbnb_rental\": 3235.36,\n  \"traditional_ROI\": 1.92281,\n  \"traditional_rental\": 1270,\n  \"baths\": 10,\n  \"beds\": 10,\n  \"days_on_market\": 152,\n  \"home_type\": \"Multi Family\",\n  \"list_price\": 599000,\n  \"sqft\": 2000\n}");
Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/ml/investment-liklihood")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/ml/investment-liklihood",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json"
  },
  "processData": false,
  "data": "{\n  \"airbnb_ROI\": 9.33728,\n  \"airbnb_rental\": 3235.36,\n  \"traditional_ROI\": 1.92281,\n  \"traditional_rental\": 1270,\n  \"baths\": 10,\n  \"beds\": 10,\n  \"days_on_market\": 152,\n  \"home_type\": \"Multi Family\",\n  \"list_price\": 599000,\n  \"sqft\": 2000\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/ml/investment-liklihood');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'Content-Type' => 'application/json'
));

$request->setBody('{
  "airbnb_ROI": 9.33728,
  "airbnb_rental": 3235.36,
  "traditional_ROI": 1.92281,
  "traditional_rental": 1270,
  "baths": 10,
  "beds": 10,
  "days_on_market": 152,
  "home_type": "Multi Family",
  "list_price": 599000,
  "sqft": 2000
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/ml/investment-liklihood"

	payload := strings.NewReader("{\n  \"airbnb_ROI\": 9.33728,\n  \"airbnb_rental\": 3235.36,\n  \"traditional_ROI\": 1.92281,\n  \"traditional_rental\": 1270,\n  \"baths\": 10,\n  \"beds\": 10,\n  \"days_on_market\": 152,\n  \"home_type\": \"Multi Family\",\n  \"list_price\": 599000,\n  \"sqft\": 2000\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "contact": {
      "prediction": {
        "Value": 1
      },
      "prediction_likelihood": {
        "Value": 67.31213123
      }
    }
  },
  "message": "prediction_likelihood succeeded"
}
```

In the last year we were trying to go over the traditional technique for searching an area per area for the best investment home to buy or rent over like other listings site, so went over this with our new product the “Property Finder”, the model built over a machine learning model **Investment Likelihood** telling the score of each MLS listing if it’s suitable for investment or not, and the customer could easily search within a short listed of listings that are suitable for investment in multiple areas (up to 5 different areas concurrently). <br> <br>
The model had 3 developments iterations yet, and we achieved more than 86% accuracy with it in our last iteration with our data scientist and real estate experience with help of multiple real estate brokers and agents who were using the product for the past recent months.
The model designed to get use of all sold listings for investment use them in next training cycle to guarantee model evolving upon time automatically as well as our data scientists keeps working on the best machine learning algorithm to introduce a very high quality investment listings for our customers.<br> <br>
The model has shown a very good impressions by our customers and recently it’s our most performing product with a thank for our developed machine learning algorithms. 
Currently our data team is working on having a new feature over the Property Finder and this investment likelihood model for predicting the most likely investment listings characters that the lead would be interested to buy through defining and implementing new machine learning models having in respect the advantage of the investment likelihood model itself as a basement, with mode dependency over the persons financials situations, demographics, and lifestyle intestates.

### HTTP Request

`POST https://api.mashvisor.com/v2/ml/investment-liklihood`

### HTTP Headers

Header | Value | Default | 
--------- | ------- | ------- |
Content-Type | application/json | | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Body Parameters

Parameter | Value | Required | Description
--------- | ------- | ------- | -----------
airbnb_ROI | Double | YES | Airbnb cash on cash (rent over investment)
airbnb_rental | Double | YES | Airbnb monthly rental income
traditional_ROI | Double | YES | Airbnb cash on cash (rent over investment)
traditional_rental | Double | YES | Traditional monthly rental income
baths | Integer | YES | Property bathrooms
beds | Integer | YES |Property bedrooms
days_on_market | Integer | NO <br> Replace it with 0 with when missed | How many days the listing has been active on market
home_type | String | YES | Property home type <br> Possible input: <br> * Condo/Coop <br> * Multi Family <br> * Other <br> * Single Family Residential <br> * Townhouse
list_price | Integer | NO <br> Replace it with 0 with when missed | Guest Message
sqft | Integer |NO <br> Replace it with 0 with when missed | Guest Message

## Mashmeter

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\"airbnb_listings\":104,\"median_airbnb_coc\":1.60582,\"airbnb_price_to_rent_ratio\":17.884447053896,\"traditional_listings\":7,\"median_traditional_coc\":0.7074975,\"traditional_price_to_rent_ratio\":28.650655961001,\"walkscore\":55}");
Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/ml/mashmeter")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Host", "api-ml-build.mashvisor.com")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/ml/mashmeter",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "Host": "api-ml-build.mashvisor.com"
  },
  "processData": false,
  "data": "{\"airbnb_listings\":104,\"median_airbnb_coc\":1.60582,\"airbnb_price_to_rent_ratio\":17.884447053896,\"traditional_listings\":7,\"median_traditional_coc\":0.7074975,\"traditional_price_to_rent_ratio\":28.650655961001,\"walkscore\":55}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/ml/mashmeter');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'Host' => 'api-ml-build.mashvisor.com',
  'Content-Type' => 'application/json'
));

$request->setBody('{"airbnb_listings":104,"median_airbnb_coc":1.60582,"airbnb_price_to_rent_ratio":17.884447053896,"traditional_listings":7,"median_traditional_coc":0.7074975,"traditional_price_to_rent_ratio":28.650655961001,"walkscore":55}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/ml/mashmeter"

	payload := strings.NewReader("{\"airbnb_listings\":104,\"median_airbnb_coc\":1.60582,\"airbnb_price_to_rent_ratio\":17.884447053896,\"traditional_listings\":7,\"median_traditional_coc\":0.7074975,\"traditional_price_to_rent_ratio\":28.650655961001,\"walkscore\":55}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Accept", "*/*")
	req.Header.Add("Host", "api-ml-build.mashvisor.com")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
      "traditional_mashmeter": "75.09",
      "airbnb_mashmeter": "67.79",
      "traditional_weight": "0.46",
      "airbnb_weight": "2.52",
      "strategy": "Airbnb",
      "mashmeter": "67.79"
    },
    "message": "Mashmeter values fetched successfully"
}
```

The Mashmeter is a unique function build over machine learning algorithms and a developed mathematical formula by our data engineers, which only Mashvisor offers to real estate investors. This simply shows you if a real estate investment in a certain neighborhood is a good or bad real estate investment decision.<br><br>
The goal of this model is to evaluate a neighbourhood by predicting how much it is good for investment. The resulting score is what so-called **Mashmeter**.

### HTTP Request

`POST https://api.mashvisor.com/v2/ml/mashmeter` 

### HTTP Headers

Header | Value | Default | 
--------- | ------- | ------- |
Content-Type | application/json | | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
airbnb_listings | Integer | | Number of properties listed for sale in a given neighbourhood
median_airbnb_coc | Double | | Median Airbnb cash on cash (rent over investment) for a neighborhood
airbnb_price_to_rent_ratio | Double | | Airbnb price to rent ratio
traditional_listings | Integer | | Number of properties listed on Airbnb in a given neighbourhood
median_traditional_coc | Double | | Median traditional cash on cash (rent over investment) for a neighborhood
traditional_price_to_rent_ratio | Double | | Traditional price to rent ratio
walkscore | Integer | | Neighborhood Walkscore value

## Property Recommender

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n  \"lead_info\": {\n    \"AgeRange\": \"45-54\",\n    \"WealthScore\": \"50.0\",\n    \"Gender\": \"Female\",\n    \"EstimatedHouseholdIncome\": \"> $250,000\",\n    \"PresenceOfChildren\": \"UNKNOWN\",\n    \"NumberOfChildren\": \"1\",\n    \"MaritalStatusInHousehold\": \"Single\",\n    \"Investing\": \"YES\",\n    \"EstWealth\": \"> $499,999\",\n    \"NumberCreditLines\": \"1\",\n    \"LengthOfResidence\": \"11 - 15 years\",\n    \"Sale1 Transfer Amt\": \"590000.0\",\n    \"BusinessOwner\": \"UNKNOWN\"\n  }\n}");
Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/ml/recommended_property")
  .post(body)
  .addHeader("Content-Type", "application/json")
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/ml/recommended_property",
  "method": "POST",
  "headers": {
    "Content-Type": "application/json",
    "Authorization": "Bearer {JWT_TOKEN}"
  },
  "processData": false,
  "data": "{\n  \"lead_info\": {\n    \"AgeRange\": \"45-54\",\n    \"WealthScore\": \"50.0\",\n    \"Gender\": \"Female\",\n    \"EstimatedHouseholdIncome\": \"> $250,000\",\n    \"PresenceOfChildren\": \"UNKNOWN\",\n    \"NumberOfChildren\": \"1\",\n    \"MaritalStatusInHousehold\": \"Single\",\n    \"Investing\": \"YES\",\n    \"EstWealth\": \"> $499,999\",\n    \"NumberCreditLines\": \"1\",\n    \"LengthOfResidence\": \"11 - 15 years\",\n    \"Sale1 Transfer Amt\": \"590000.0\",\n    \"BusinessOwner\": \"UNKNOWN\"\n  }\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/ml/recommended_property');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}',
  'Content-Type' => 'application/json'
));

$request->setBody('{
  "lead_info": {
    "AgeRange": "45-54",
    "WealthScore": "50.0",
    "Gender": "Female",
    "EstimatedHouseholdIncome": "> $250,000",
    "PresenceOfChildren": "UNKNOWN",
    "NumberOfChildren": "1",
    "MaritalStatusInHousehold": "Single",
    "Investing": "YES",
    "EstWealth": "> $499,999",
    "NumberCreditLines": "1",
    "LengthOfResidence": "11 - 15 years",
    "Sale1 Transfer Amt": "590000.0",
    "BusinessOwner": "UNKNOWN"
  }
}');

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/ml/recommended_property"

	payload := strings.NewReader("{\n  \"lead_info\": {\n    \"AgeRange\": \"45-54\",\n    \"WealthScore\": \"50.0\",\n    \"Gender\": \"Female\",\n    \"EstimatedHouseholdIncome\": \"> $250,000\",\n    \"PresenceOfChildren\": \"UNKNOWN\",\n    \"NumberOfChildren\": \"1\",\n    \"MaritalStatusInHousehold\": \"Single\",\n    \"Investing\": \"YES\",\n    \"EstWealth\": \"> $499,999\",\n    \"NumberCreditLines\": \"1\",\n    \"LengthOfResidence\": \"11 - 15 years\",\n    \"Sale1 Transfer Amt\": \"590000.0\",\n    \"BusinessOwner\": \"UNKNOWN\"\n  }\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("Content-Type", "application/json")
	req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "property_type": {
    "SINGLE FAMILY": 28.1,
    "MULTIPLE FAMILY": 27.4
  },
  "bedrooms": {
    "4-Greater": 78,
    "2-3": 17.7
  },
  "bathrooms": {
    "1-2": 50,
    "4-Greater": 32.7
  },
  "home_value": {
    "> $1,000,000": 87.5,
    "$500,000-999,999": 11.5
  }
}
```

The API is to return a json object holding data representing specifications for recommended properties based on the a person demographics and financials. The specifications including: property type, number of rooms, number of bathrooms, and the home value.

### HTTP Request

`POST https://api.mashvisor.com/v2/ml/recommended_property` 

### HTTP Headers

Header | Value | Default | 
--------- | ------- | ------- |
Content-Type | application/json | | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
AgeRange | String | | Person age range <br> Possbile Inputs: <br> * '18-24'<br> * '25-34'<br> * '35-44'<br> * '45-54'<br> * '55-64'<br> * '65-74'<br> * '75+'<br> * 'UNKNOWN'
WealthScore | Integer | | Any from 0 to 100<br> Or 'UNKNOWN'
Gender | String | | Possbile Inputs: <br> * Male<br> * Female<br> * UNKNOWN
EstimatedHouseholdIncome | String | | Possbile Inputs: <br> * '< $20,000'<br> * '$10,000-49,999'<br> * '$50,000-99,999'<br> * '$100,000-149,999'<br> * '$150,000-199,999'<br> * '$200,000-249,999'<br> * $250,000'<br> *'UNKNOWN'
PresenceOfChildren | String | | Possbile Inputs: <br> * 'YES'<br> * UNKNOWN
NumberOfChildren | String | | Any positive integer number <br> If missing, value should be sent as  -1
MaritalStatusInHousehold | String | | Possbile Inputs: <br> * Married<br> * Signle<br> * UNKNOWN
Investing | String | | Possbile Inputs: <br> * 'YES'<br> * UNKNOWN
EstWealth | String | | Possbile Inputs: <br> * '< $1'<br> *'$1-4,999'<br> *'$5,000-9,999'<br> *'$10,000-24,999'<br> *'$25,000-49,999'<br> *'$50,000-99,999'<br> *'$100,000-249,999'<br> *'$250,000-499,999'<br> *'>$499,999'<br> *'UNKNOWN'
NumberCreditLines | String | | Any positive integer number
LengthOfResidence | String | | Possbile Inputs: <br> * '1 - 4 year'<br> * '11 - 15 years'<br> * '5 - 10 years'<br> * UNKNOWN
Sale1 Transfer Amt | String | | Any positive number
BusinessOwner | String | | Possbile Inputs: <br> * Accountant<br> * 'Contractor'<br> * 'Owner','Partner'<br> *'Person Owns a Business'<br> * Self Employed'<br> * 'UNKNOWN'

# Short Term Rentals
Mashvisor prvides data and anlysis for different short term rentals services presenting them for the investment listings, including AirBnB, HomeAway, and VRBO. <br>
* **AirBnB** <br>
Mashvisor started integrating with AirBnB since the first day we founded the company - late 2014. We have data for all U.S listings in a location, storing all listing detailed info, reviews, photos, host info, and yearly calendar for day per day booking availability and booking price per night. We currently having 2M+ listings available in our database. <br>
Mashvisor also developed an occupancy calculator algotherm evolved over the last 5 years calculating the occupancy rate for each listing month by month upon its historical performance and available future bookings. Our algorithms could currently distinguish between booked days and blocked days from booking, also calculate the estimated monthly rental income for the listings for future predictions, and availability to provide rental incomes for all the past months for the listing history. Moreover, we’ve implemented different mathematical algorithms helping us into our calculations, and we’re working on a new machine learning algorithms would help determining listings outliers, calculated occupancy rates. <br>
Recently, we started the process of reviewing our occupancy rates calculations with verified AirBnB hosts who have multiple listings over there to guarantee better service introduced for our customers and superiority over our main competitor AirDna.
States breakdown coverage is attached in appendix D.<br>

* **HomeAway** <br>
Mashvisor started integrating with HomeAway since mid of 2016. We go over all neighborhoods and cities available in our database on monthly basis getting all listings within a neighborhood, storing all listing detailed info, reviews, photos, and yearly calendar for day per day booking availability. We currently having 500K+ listings available in our database.<br>
Our crawling cycle areas coverage crawling automatically month by month whenever we have a new city or neighborhood covered into our database. <br>
Mashvisor also developed an occupancy calculator algotherm evolved over the last 3 years calculating the occupancy rate for each listing month by month upon its historical performance and available future bookings. Also calculate the estimated monthly rental income for the listings for future predictions, and availability to provide rental incomes for all the past months for the listing history.

## Get Airbnb Listing Info

This endpoint retrieves the Airbnb property detailed information, reviews, photos, host, estiamted rental income, calculated occupancy rate.

### Airbnb Property Data Dictionary
| Attribute                     | Definition                                                                                                                                                              | Possible Returns      |
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| id                            | Airbnb listing ID: 9998508                                                                                                                                              | Integer               |
| name                          | Listing full name                                                                                                                                                       | String                |
| neighborhood                  | Listing neighborhood                                                                                                                                                    | Boolean               |
| city                          | The city where the listing is located                                                                                                                                   | String                |
| state                         | The state where the property is located                                                                                                                                 | String                |
| zip code                      | Postal code where a listing is located                                                                                                                                  | Integer               |
| country                       | County where a listing is located                                                                                                                                       | String                |
| smart_location                | Full location of listing                                                                                                                                                | String                |
| address                       | Address of listing entered by host                                                                                                                                      | String                |
| public_address                | Full address along with the country                                                                                                                                     | String                |
| country_code                  | Listing’s country code, ex: US                                                                                                                                          | String                |
| market                        | Listing market                                                                                                                                                          | String                |
| lat                           | Latitude of listing location                                                                                                                                            | Float                 |
| lng                           | Longitude of listing location                                                                                                                                           | Float                 |
| instant_bookable              | Indicator if listing is available for instant booking                                                                                                                   | Boolean               |
| picture_url                   | Main picture url                                                                                                                                                        | String                |
| thumbnail_url                 | Main thumbnail picture url                                                                                                                                              | String                |
| medium_url                    | Main XL picture url                                                                                                                                                     | String                |
| xl_picture_url                | All XL pictures urls.                                                                                                                                                   | String                |
| picture_urls                  | All pictures url                                                                                                                                                        | String - array        |
| thumbnail_urls                | All thumbnail pictures url                                                                                                                                              | String - array        |
| xl_picture_urls               | All XL pictures urls.                                                                                                                                                   | String - array        |
| picture_count                 | Count of all pictures                                                                                                                                                   | Integer               |
| picture_captions              | All pictures captions                                                                                                                                                   | String - array        |
| map_image_url                 | Google map image url                                                                                                                                                    | String                |
| user_id                       | Listing’s host ID                                                                                                                                                       | Integer               |
| price                         | Listing current booking price per night                                                                                                                                 | Integer               |
| native_currency               | Natiec price currency, ex: “USD”                                                                                                                                        | String                |
| price_native                  | Listing nartive price                                                                                                                                                   | Integer               |
| price_formatted               | Price along with the currency                                                                                                                                           | String                |
| price_for_extra_person_native | Extra person’s price                                                                                                                                                    | Integer               |
| weekly_price_native           | Weekly price after the discount                                                                                                                                         | Integer               |
| monthly_price_native          | Monthly price after the discount                                                                                                                                        | Integer               |
| currency_symbol_left          | Currency symbol, ex: “$”                                                                                                                                                | String                |
| currency_symbol_right         | Currency symbol, ex: “€”                                                                                                                                                | String                |
| security_deposit_native       | Security deposit price                                                                                                                                                  | Integer               |
| security_price_native         | Security deposit native price                                                                                                                                           | Integer               |
| security_deposit_formatted    | Security deposit price with currency                                                                                                                                    | String                |
| bedrooms                      | Number of bedrooms                                                                                                                                                      | Integer               |
| beds                          | Number of beds                                                                                                                                                          | Integer               |
| bathrooms                     | Number of bathrooms                                                                                                                                                     | Integer               |
| min_nights                    | Min allowed booking nights                                                                                                                                              | Integer               |
| person_capacity               | Max listing capacity of persons                                                                                                                                         | Integer               |
| user                          | The time of the open house starting                                                                                                                                     | User Object           |
| cancellation_policy           | Cancellation policy category                                                                                                                                            | String                |
| cancel_policy                 | Cancellation policy category ID                                                                                                                                         | Integer               |
| cancel_policy_short_str       | Summary of cancellation policy                                                                                                                                          | String                |
| has_double_blind_reviews      | Boolean indicator for blind reviews                                                                                                                                     | Boolean               |
| property_type                 | Property main type                                                                                                                                                      | String <br> Available types: <br> * House <br> * Apartment <br> * Bed and breakfast <br> * Boutique hotel <br> * More information <br> * Bungalow <br> * Cabin <br> * Chalet <br> * Cottage <br> * Guest suite <br> * Guesthouse <br> * Hostel <br> * Hotel <br> * Loft <br> * Resort <br> * Townhouse <br> * Villa  
| reviews_count                 | Total reviews count                                                                                                                                                     | Integer               |
| review_scores                 | Detailed reviews scores per category                                                                                                                                    | Review Scores object  |
| room_type                     | Listing room type                                                                                                                                                       | String <br> Available types: <br> * Entire home/apt <br> * Private room <br> * Shared room |
| room_type_category            | Room type category                                                                                                                                                      | String                |
| bed_type                      | Bed type                                                                                                                                                                | String                |
| bed_type_category             | Bed type category                                                                                                                                                       | String                |
| require_guest_profile_picture |                                                                                                                                                                         | Boolean               |
| Require_guest_phone_          |                                                                                                                                                                         | Boolean               |
| verification                  |                                                                                                                                                                         |                       |
| force_mobile_legal_modal      |                                                                                                                                                                         | Boolean               |
| check_in_time                 | Check in time hour                                                                                                                                                      | Integer               |
| check_out_time                | Check out time hour                                                                                                                                                     | Integer               |
| guests_included               | Number of guests included                                                                                                                                               | Integer               |
| license                       | AirBnB license for listing                                                                                                                                              | String                |
| max_nights                    | Max booking nights                                                                                                                                                      | Integer               |
| square_feet                   | Listing living area                                                                                                                                                     | Integer               |
| locale                        | Listing’s locale                                                                                                                                                        | String                |
| has_viewed_terms              |                                                                                                                                                                         | Boolean               |
| has_viewed_cleaning           |                                                                                                                                                                         | Boolean               |
| has_agreed_to_legal_terms     |                                                                                                                                                                         | Boolean               |
| Has_viewed_ib_                |                                                                                                                                                                         | Boolean               |
| perf_dashboard_panel          |                                                                                                                                                                         |                       |
| language                      | Listing page language                                                                                                                                                   | String                |
| experiences_offered           | Listing’ experience offered along with booking                                                                                                                          | String                |
| max_nights_input_value        |                                                                                                                                                                         | Integer               |
| min_nights_input_value        |                                                                                                                                                                         | Integer               |
| requires_license              | Indicator if the listing requires licence                                                                                                                               | Boolean               |
| property_type_id              | Property type ID                                                                                                                                                        | Integer               |
| house_rules                   | Hosting rules provided by host when booking                                                                                                                             | String                |
| description                   | Listing full description                                                                                                                                                | String                |
| description_locale            | Description locale                                                                                                                                                      | String                |
| summary                       | Description summary                                                                                                                                                     | String                |
| space                         | Listing space                                                                                                                                                           | String                |
| access                        | Allowed accesses in the listing from host                                                                                                                               | String                |
| interaction                   | Host interaction                                                                                                                                                        | String                |
| neighborhood_overview         | Listing neighborhood overview                                                                                                                                           | String                |
| transit                       | Listing around transit                                                                                                                                                  | String                |
| amenities                     | All included amenities                                                                                                                                                  | String - array        |
| amenities_ids                 | All included amenities                                                                                                                                                  | String - array        |
| is_location_exact             | Verified exact location                                                                                                                                                 | Boolean               |
| recent_review                 | Last review over the listing                                                                                                                                            | Review object         |
| calendar_updated_at           | Calendar last update                                                                                                                                                    | String                |
| star_rating                   | Total start rating                                                                                                                                                      | Float                 |
| time_zone_name                | Full timezone name                                                                                                                                                      | String                |
| calendar                      | Object indicates month by month and day per day booking availability during a year since listing was created at first, and with each night associated price for booking | Calendar Object       |
| created_at                    | Listing creation date and time                                                                                                                                          | Timestamp             |
| updated_at                    | Listing updates date and time                                                                                                                                           | Timestamp             |
| exists                        | Indicator if the listing is still active over AirBnB or not.                                                                                                            | Boolean               |
| Reviews                       | Array of all associated reviews                                                                                                                                         | Review object - array |

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/22625220?state=CA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/property/22625220?state=CA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/property/22625220');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));
$request->setQueryData(array(
  'state' => 'CA'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/property/22625220?state=CA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "listing": {
      "id": 22625220,
      "airbnb_id": 19680922,
      "city": "San Francisco",
      "picture_url": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=large",
      "thumbnail_url": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=small",
      "medium_url": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=medium",
      "xl_picture_url": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=x_large",
      "user_id": 12703126,
      "price": 105,
      "native_currency": "USD",
      "price_native": 105,
      "price_formatted": "$105",
      "lat": 37.79291,
      "lng": -122.408,
      "country": "United States",
      "name": "Classic 20's  boutique apt. with charming updates",
      "smart_location": "San Francisco, CA",
      "has_double_blind_reviews": false,
      "instant_bookable": false,
      "bedrooms": 0,
      "beds": 2,
      "bathrooms": 1,
      "market": "San Francisco",
      "min_nights": 30,
      "neighborhood": "Chinatown",
      "person_capacity": 4,
      "state": "CA",
      "zipcode": "94108",
      "address": "San Francisco, CA, United States",
      "country_code": "US",
      "cancellation_policy": "strict_14_with_grace_period",
      "property_type": "Apartment",
      "reviews_count": 3,
      "room_type": "Entire home/apt",
      "room_type_category": "entire_home",
      "picture_urls": [
        "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=large",
        "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=large"
      ],
      "picture_count": 11,
      "currency_symbol_left": "$",
      "currency_symbol_right": null,
      "picture_captions": [
        "Livingroom area with Recliner chair, sofa/sleeper, coffee table",
        "Livingroom area showing queen size bed",
        "Dining Area",
        "Galley Kitchen with period cabinets, nice size refrigerator/freezer and updated granite counter tops",
        "Kitchen has 4 burner gas range oven/broiler, built in microwave and stainless steel sink",
        "In kitchen looking at dining area",
        "Bathroom vanity with updated vessel sink and granite countertops ",
        "Large walk-in closet",
        "",
        "Bathtub / shower combination ",
        "Tile shelf’s in shower with ample supplies to get started "
      ],
      "bed_type": "Real Bed",
      "bed_type_category": "real_bed",
      "require_guest_profile_picture": false,
      "require_guest_phone_verification": false,
      "force_mobile_legal_modal": true,
      "cancel_policy": 44,
      "check_in_time": 15,
      "check_out_time": 12,
      "guests_included": 1,
      "license": null,
      "max_nights": 180,
      "square_feet": null,
      "locale": "en",
      "has_viewed_terms": null,
      "has_viewed_cleaning": null,
      "has_agreed_to_legal_terms": true,
      "has_viewed_ib_perf_dashboard_panel": null,
      "language": "en",
      "public_address": "San Francisco, CA, United States",
      "map_image_url": "https://maps.googleapis.com/maps/api/staticmap?maptype=roadmap&markers=37.79291%2C-122.408&size=480x320&zoom=15&client=gme-airbnbinc&channel=monorail-prod&signature=2Qbg19W31PTrfmmba2XtI0dc8k8%3D",
      "experiences_offered": "none",
      "max_nights_input_value": 180,
      "min_nights_input_value": 30,
      "requires_license": true,
      "property_type_id": 1,
      "house_rules": "",
      "security_deposit_native": 500,
      "security_price_native": 500,
      "security_deposit_formatted": "$500",
      "description": "Quintessential San Francisco large Studio Apartment on Nob Hill, 1/2 block to the Fairmont, 1 block to the Mark Hopkins and 3 blocks to the Ritz Carlton, Paramont location just a stones throw to China Town, Union Square and North Beach. Classic  boutique building with updated charm. If your looking for a great location, super clean, bright and clean accommodations, at a fraction of the nearby hotels, You just found it. All you need is your suitcase and toothbrush. Welcome to San Francisco\n\nFantastic apartment one block from the top of Nob Hill, steps to the Fairmont, Grace Cathedral, China Town, North Beach (little Italy, downtown shopping at Union Square, with great bus connections: #1 California 25 feet away, Mason and Hyde Street Cable Car in front of building, the #30 Stockton one block away. Large Flat Street T.V. And high speed wifi. The apartment has a new Queen size pillow top mattress, additionally in the event you have an overnight guest the sofa will make into a single sleeper, with additional sheets and pillows in large walk-in closet. Based on what I would enjoy, I've tried to think of everything to create a place at a fraction of the cost of the nearby hotels for my guest to experience San Francisco in a safe, clean and romantically authentic setting.  Whether you're here on business, extended vacation, relocating, or visiting family,  I am confident if you choose these accommodations you will not be disappointed.\n\nThis apartment is totally private, you do not share any part with anyone, it's your own home away from home, no strange roommates.\n\nI will make sure you get settled in, everything is in order, after that you will have total privacy to enjoy this great city, if you have any issues, I'm just a cell phone call away to help anyway I can.",
      "description_locale": "en",
      "summary": "Quintessential San Francisco large Studio Apartment on Nob Hill, 1/2 block to the Fairmont, 1 block to the Mark Hopkins and 3 blocks to the Ritz Carlton, Paramont location just a stones throw to China Town, Union Square and North Beach. Classic  boutique building with updated charm. If your looking for a great location, super clean, bright and clean accommodations, at a fraction of the nearby hotels, You just found it. All you need is your suitcase and toothbrush. Welcome to San Francisco",
      "space": "Fantastic apartment one block from the top of Nob Hill, steps to the Fairmont, Grace Cathedral, China Town, North Beach (little Italy, downtown shopping at Union Square, with great bus connections: #1 California 25 feet away, Mason and Hyde Street Cable Car in front of building, the #30 Stockton one block away. Large Flat Street T.V. And high speed wifi. The apartment has a new Queen size pillow top mattress, additionally in the event you have an overnight guest the sofa will make into a single sleeper, with additional sheets and pillows in large walk-in closet. Based on what I would enjoy, I've tried to think of everything to create a place at a fraction of the cost of the nearby hotels for my guest to experience San Francisco in a safe, clean and romantically authentic setting.  Whether you're here on business, extended vacation, relocating, or visiting family,  I am confident if you choose these accommodations you will not be disappointed.",
      "access": "This apartment is totally private, you do not share any part with anyone, it's your own home away from home, no strange roommates.",
      "interaction": "I will make sure you get settled in, everything is in order, after that you will have total privacy to enjoy this great city, if you have any issues, I'm just a cell phone call away to help anyway I can.",
      "neighborhood_overview": "",
      "transit": "",
      "amenities": [
        "TV",
        "Wifi",
        "Kitchen",
        "Elevator",
        "Heating",
        "Washer",
        "Dryer",
        "Smoke detector",
        "Carbon monoxide detector",
        "Essentials",
        "Shampoo",
        "Lock on bedroom door",
        "Hangers",
        "Iron",
        "Private entrance",
        "Microwave",
        "Coffee maker",
        "Refrigerator",
        "Dishes and silverware",
        "Cooking basics",
        "Oven",
        "Stove",
        "Long term stays allowed",
        "Host greets you"
      ],
      "amenities_ids": [
        1,
        4,
        8,
        21,
        30,
        33,
        34,
        35,
        36,
        40,
        41,
        42,
        44,
        46,
        57,
        89,
        90,
        91,
        93,
        94,
        95,
        96,
        104,
        129
      ],
      "is_location_exact": true,
      "recent_review": {
        "review": {
          "comments": "It was a wonderful place!",
          "created_at": "2019-07-13T21:07:13Z",
          "id": 487146877,
          "listing_id": 19680922,
          "reviewee_id": 12703126,
          "reviewer": {
            "user": {
              "first_name": "Soong",
              "has_profile_pic": true,
              "id": 39697902,
              "picture_url": "https://a0.muscache.com/im/pictures/user/6de492d2-be84-4281-9a91-c234588ffe35.jpg?aki_policy=profile_x_medium",
              "smart_name": "Soong",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/user/6de492d2-be84-4281-9a91-c234588ffe35.jpg?aki_policy=profile_small"
            }
          },
          "reviewer_id": 39697902,
          "role": "guest",
          "user_flag": null
        }
      },
      "calendar_updated_at": "6 months ago",
      "cancel_policy_short_str": "Strict (grace period)",
      "star_rating": 5,
      "price_for_extra_person_native": 0,
      "weekly_price_native": null,
      "monthly_price_native": null,
      "time_zone_name": "America/Los_Angeles",
      "loc": {
        "type": "Point",
        "coordinates": [
          -122.408,
          37.79291
        ]
      },
      "exists": true,
      "created_at": "2018-07-31T23:02:34.752Z",
      "updated_at": "2019-07-25T21:40:49.824Z"
    }
  }
}
```

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/{id}`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property Id.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.

## Get Airbnb Historical Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/22625220/historical?state=CA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/airbnb-property/22625220/historical?state=CA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/airbnb-property/22625220/historical');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));
$request->setQueryData(array(
  'state' => 'CA'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/airbnb-property/22625220/historical?state=CA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "name": "Classic 20's  boutique apt. with charming updates",
        "property_id": "19680922",
        "months": [
            {
                "year": 2018,
                "month": 10,
                "nightly_price": 105,
                "revenue": 3150,
                "occupancy": 30
            },
            {
                "year": 2018,
                "month": 11,
                "nightly_price": 105,
                "revenue": 94.5,
                "occupancy": 1
            },
            {
                "year": 2018,
                "month": 12,
                "nightly_price": 105,
                "revenue": 0,
                "occupancy": 0
            },
            {
                "year": 2019,
                "month": 1,
                "nightly_price": 0,
                "revenue": 0,
                "occupancy": 0
            },
            {
                "year": 2019,
                "month": 2,
                "nightly_price": 105,
                "revenue": 3150,
                "occupancy": 30
            },
            {
                "year": 2019,
                "month": 3,
                "nightly_price": 105,
                "revenue": 3150,
                "occupancy": 30
            },
            {
                "year": 2019,
                "month": 4,
                "nightly_price": 105,
                "revenue": 3150,
                "occupancy": 30
            },
            {
                "year": 2019,
                "month": 5,
                "nightly_price": 105,
                "revenue": 3150,
                "occupancy": 30
            },
            {
                "year": 2019,
                "month": 6,
                "nightly_price": 105,
                "revenue": 3150,
                "occupancy": 30
            },
            {
                "year": 2019,
                "month": 7,
                "nightly_price": 105,
                "revenue": 2835,
                "occupancy": 27
            },
            {
                "year": 2019,
                "month": 8,
                "nightly_price": 105,
                "revenue": 2331,
                "occupancy": 22
            },
            {
                "year": 2019,
                "month": 9,
                "nightly_price": 105,
                "revenue": 0,
                "occupancy": 0
            }
        ]
    }
}
```

This endpoint retrieves the Airbnb property 12 historical records - nightly price, revenue, and occupancy - for a specific property. 

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/{id}/historical`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property record Id from the Mashvisor database.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.

## Get Host Info

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/19680922/host?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/airbnb-property/19680922/host?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/airbnb-property/19680922/host');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'page' => '1',
  'state' => 'IL',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/airbnb-property/19680922/host?state=IL&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "user": {
      "first_name": "Jeff",
      "has_profile_pic": true,
      "id": 12703126,
      "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
      "smart_name": "Jeff",
      "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small",
      "acceptance_rate": "N/A",
      "created_at": "2014-03-01T21:16:11Z",
      "identity_verified": false,
      "is_superhost": true,
      "picture_large_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_large",
      "recommendation_count": 0,
      "response_rate": "100%",
      "response_time": "within an hour",
      "reviewee_count": 24,
      "thumbnail_medium_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_medium",
      "neighborhood": "Chinatown",
      "verification_labels": [
        "Email address",
        "Phone number",
        "Reviewed"
      ],
      "verifications": [
        "email",
        "phone",
        "reviews"
      ],
      "about": "Friendly, accomadating, respectful, polite, easy going regular person. ",
      "all_active_phone_numbers": [],
      "friends_count": 0,
      "guidebooks_count": 0,
      "has_available_payout_info": true,
      "identity_mt_verified": false,
      "identity_v2_verified": false,
      "is_generated_user": false,
      "is_trip_host": false,
      "is_marketplace_cohost": false,
      "languages": [
        "English"
      ],
      "listings_count": 5,
      "location": "San Francisco, CA",
      "recent_recommendation": null,
      "recent_review": {
        "review": {
          "comments": "Jeff is a wonderful host! He responds to questions and concerns very promptly. The place is small but it has everything you will need. It’s very cozy and comfortable to live in. The location is super convenient. I really enjoyed my stay!!",
          "created_at": "2019-07-16T23:27:35Z",
          "id": 489450656,
          "listing_id": 18853563,
          "reviewee_id": 12703126,
          "reviewer": {
            "user": {
              "first_name": "Lanting",
              "has_profile_pic": true,
              "id": 204093245,
              "picture_url": "https://a0.muscache.com/im/pictures/user/737bd62a-859b-400b-8a4f-42749ef8908c.jpg?aki_policy=profile_x_medium",
              "smart_name": "Lanting",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/user/737bd62a-859b-400b-8a4f-42749ef8908c.jpg?aki_policy=profile_small"
            }
          },
          "reviewer_id": 204093245,
          "role": "guest",
          "user_flag": null,
          "listing": {
            "listing": {
              "city": "San Francisco",
              "collection_ids": null,
              "country": "United States",
              "has_double_blind_reviews": false,
              "id": 18853563,
              "instant_book_enabled": false,
              "instant_bookable": false,
              "lat": 37.79252,
              "lng": -122.4081,
              "medium_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=medium",
              "name": "Nob Hill Jewel Box",
              "native_currency": "USD",
              "picture_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=large",
              "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAUAAAAECAIAAADJUWIXAAAAS0lEQVQIHQFAAL//AXNWOO7s7/r9Ae7o5iI4RgFgQiMPBQU7W3SJfnuVqbMBRjoyKCYqHiAfq6CUN0dUAUU5MBgcKdbe6frv2vPz9WRpG/xGx/8wAAAAAElFTkSuQmCC",
              "price": 100,
              "price_formatted": "$100",
              "price_native": 100,
              "scrim_color": "#120806",
              "smart_location": "San Francisco, CA",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=small",
              "user": {
                "user": {
                  "first_name": "Jeff",
                  "has_profile_pic": true,
                  "id": 12703126,
                  "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
                  "smart_name": "Jeff",
                  "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
                }
              },
              "user_id": 12703126,
              "x_medium_picture_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=x_medium",
              "xl_picture_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=x_large"
            }
          },
          "reviewee": {
            "user": {
              "first_name": "Jeff",
              "has_profile_pic": true,
              "id": 12703126,
              "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
              "smart_name": "Jeff",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
            }
          }
        }
      },
      "school": "High school, some college",
      "show_travel_for_work": false,
      "signup_method": 0,
      "total_listings_count": 5,
      "user_flag": null,
      "work": "Property management "
    }
  }
}
```

This endpoint retrieves the host info for a specific AirBnB property.

### Host Info Data Dictionary
| Attribute                 | Definition                                | Possible Returns |
|---------------------------|-------------------------------------------|------------------|
| id                        | AirBnB host ID                            | Integer          |
| first_name                | Host first name                           | String           |
| has_profile_pic           | Indicator if the host has profile picture | Boolean          |
| picture_url               | Profile picture url                       | String           |
| smart_name                | Host provided name                        | String           |
| thumbnail_url             | Thumbnail profile picture url             | String           |
| acceptance_rate           | Booking acceptance rate                   | String           |
| created_at                | Host created at time                      | Timestamp        |
| identity_verified         | Verified host identity or not             | Boolean          |
| is_superhost              | Indicator if the host is superhost        | Boolean          |
| picture_large_url         | Large profile picture url                 | String           |
| recommendation_count      | How many users recommended the host       | Integer          |
| response_rate             | Responsiveness rate                       | Percentage       |
| response_time             | Responsiveness time summary               | String           |
| reviewee_count            | How many reviewee the host had            | Integer          |
| thumbnail_medium_url      | Thumbnail medium image url                | String           |
| neighborhood              | Host neighborhood                         | String           |
| verifications             | Email, phone, reviews, and location       | String - array   |
| about                     | Summary about the host                    | String           |
| all_active_phone_numbers  | Host phone numbers                        | String - array   |
| friends_count             | Host friends count over AirBnB            | Integer          |
| has_available_payout_info | Boolean indicator about the payouts       | Boolean          |
| identity_mt_verified      |                                           | Boolean          |
| identity_v2_verified      |                                           | Boolean          |
| is_generated_user         |                                           | Boolean          |
| is_trip_host              |                                           | Boolean          |
| is_marketplace_cohost     |                                           | Boolean          |
| languages                 | Host languages                            | String - array   |
| listings_count            | Host listings count                       | Integer          |
| location                  | Host location                             | String           |
| recent_recommendation     | Recent recommendation host made           | Json array       |
| recent_review             | Latest review over the host               | Review object    |
| show_travel_for_work      |                                           | Boolean          |
| signup_method             | AirBnB signup method                      | String           |
| total_listings_count      |                                           | String           |
| user_flag                 |                                           | Boolean          |
| work                      | Host current work                         | String           |


### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/{id}/host` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property Id.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.

## Get Review Scores Info

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/19680922/review-score?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/airbnb-property/19680922/review-score?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/airbnb-property/19680922/review-score');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'page' => '1',
  'state' => 'IL',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/airbnb-property/19680922/review-score?state=IL&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "review_scores": {
      "accuracy": 10,
      "checkin": 10,
      "cleanliness": 10,
      "communication": 10,
      "location": 10,
      "rating": 90,
      "value": 9
    }
  }
}
```

This endpoint retrieves the review score object for a specific AirBnB property.

### The Review Score Data Dictionary
| Attribute     | Definition                                | Possible Returns |
|---------------|-------------------------------------------|------------------|
| accuracy      | Total reviews about listing accuracy      | Integer          |
| checkin       | Total reviews about listing check in      | Integer          |
| cleanliness   | Total reviews about listing cleanliness   | Integer          |
| communication | Total reviews about listing communication | Integer          |
| location      | Total reviews about listing location      | Integer          |
| rating        | Total reviews about listing rating        | Integer          |
| value         | Total reviews about listing value         | Integer          |

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/{id}/review-score` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property Id.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.


## Get Reviews

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/19680922/reviews?state=CA&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/airbnb-property/19680922/reviews?state=CA&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/airbnb-property/19680922/reviews');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/airbnb-property/19680922/reviews?state=CA&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "reviews": [
      {
        "author": {
          "first_name": "Soong",
          "has_profile_pic": true,
          "id": 39697902,
          "picture_url": "https://a0.muscache.com/im/pictures/user/6de492d2-be84-4281-9a91-c234588ffe35.jpg?aki_policy=profile_x_medium",
          "smart_name": "Soong",
          "thumbnail_url": "https://a0.muscache.com/im/pictures/user/6de492d2-be84-4281-9a91-c234588ffe35.jpg?aki_policy=profile_small"
        },
        "author_id": 39697902,
        "can_be_edited": false,
        "comments": "It was a wonderful place!",
        "created_at": "2019-07-13T21:07:13Z",
        "hide_author_profile": false,
        "id": 487146877,
        "listing_id": 19680922,
        "recipient_id": 12703126,
        "collection_tag": null,
        "listing": {
          "id": 19680922,
          "name": "Classic 20's  boutique apt. with charming updates"
        },
        "rating": 5,
        "recipient": {
          "first_name": "Jeff",
          "has_profile_pic": true,
          "id": 12703126,
          "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
          "smart_name": "Jeff",
          "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
        },
        "response": "",
        "role": "guest",
        "language": "en",
        "user_flag": null
      },
      {
        "author": {
          "first_name": "Steve",
          "has_profile_pic": true,
          "id": 39943239,
          "picture_url": "https://a0.muscache.com/im/pictures/user/ee2cdaa9-4cff-4978-af81-491453dae4e9.jpg?aki_policy=profile_x_medium",
          "smart_name": "Steve",
          "thumbnail_url": "https://a0.muscache.com/im/pictures/user/ee2cdaa9-4cff-4978-af81-491453dae4e9.jpg?aki_policy=profile_small"
        },
        "author_id": 39943239,
        "can_be_edited": false,
        "comments": "From the ease of booking and quick responses back on any questions to the checking in and help while staying there to the checking out Jeff was outstanding. The place is awesome and very roomy for a studio.  Everything worked and was very clean.  Bed was comfortable, neighbors were quiet and location was incredible.   When we showed up Jeff was there waiting for us with beverages in the refrigerator.  After we checked in Jeff showed us around the neighborhood as this was a new area to us.  He spent time letting us know where the essentials were.  During the stay he was available for any questions and when we checked out he actually found our cell phone that was misplaced in the facilities area.  Incredible....he just kept pleasantly surprising us.  I would recommend staying at this unit long or short term.  The location was perfect for access to the financial district as well as Union Square and waterfront.  It sits on the top of Nob Hill, which is clean and safe and beautiful!!\n\nWe are making plans to go back!!\n\n",
        "created_at": "2018-08-18T20:22:51Z",
        "hide_author_profile": false,
        "id": 309737489,
        "listing_id": 19680922,
        "recipient_id": 12703126,
        "collection_tag": null,
        "listing": {
          "id": 19680922,
          "name": "Classic 20's  boutique apt. with charming updates"
        },
        "rating": 5,
        "recipient": {
          "first_name": "Jeff",
          "has_profile_pic": true,
          "id": 12703126,
          "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
          "smart_name": "Jeff",
          "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
        },
        "response": "",
        "role": "guest",
        "language": "en",
        "user_flag": null
      },
      {
        "author": {
          "first_name": "Nasser",
          "has_profile_pic": true,
          "id": 147937651,
          "picture_url": "https://a0.muscache.com/im/pictures/user/c03709f5-687c-4968-9a42-30aa51102338.jpg?aki_policy=profile_x_medium",
          "smart_name": "Nasser",
          "thumbnail_url": "https://a0.muscache.com/im/pictures/user/c03709f5-687c-4968-9a42-30aa51102338.jpg?aki_policy=profile_small"
        },
        "author_id": 147937651,
        "can_be_edited": false,
        "comments": "Foi ótima minha primeira experiência com locação de imóvel através da Airbnb. \nFui muito feliz na escolha do imóvel do Sr. Jeff. O imóvel estava perfeito, exatamente como observei no site.  O Sr. Jeff é uma pessoa atenciosa e gentil. O apartamento estava perfeito, tudo muito limpo, tinha tudo que precisávamos. Cama ótima, roupa de cama limpa, cozinha muito bem mobiliada. O local do imóvel é silencioso, TV, AR quente, internet, lavanderia, tudo funcionando perfeitamente. O local é seguro e com transporte á sua porta.\nVoltando em SF certamente irei alugar esse imóvel novamente, se possível.\nDeixo aqui meus cumprimentos e meus agradecimentos ao S. Jeff.\nGrato.\nNasser José Bhering Nasser e do meu filho Nasser Bhering Barbosa Nasser",
        "created_at": "2018-02-04T23:22:52Z",
        "hide_author_profile": false,
        "id": 232418679,
        "listing_id": 19680922,
        "recipient_id": 12703126,
        "collection_tag": null,
        "listing": {
          "id": 19680922,
          "name": "Classic 20's  boutique apt. with charming updates"
        },
        "rating": 5,
        "recipient": {
          "first_name": "Jeff",
          "has_profile_pic": true,
          "id": 12703126,
          "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
          "smart_name": "Jeff",
          "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
        },
        "response": "",
        "role": "guest",
        "language": "pt",
        "user_flag": null
      }
    ]
  }
}
```

This endpoint retrieves an AirBnB listing's reviews array.

### Review Object Data Dictionary
| Attribute      | Definition                     | Possible Returns |
|----------------|--------------------------------|------------------|
| author         | Author id and name             | String           |
| can_be_edited  | If the review is editable      | Boolean          |
| comments       | Guest comment over the listing | String           |
| created_at     | Review creation date and time  | Timestamp        |
| id             | Review ID                      | Integer          |
| listing_id     | AirBnB listing ID              | Integer          |
| recipient_id   | Host ID                        | Integer          |
| collection_tag | Tags for reviews               | String           |
| rating         | Review rating                  | Integer          |
| response       | Comment reply                  | String           |
| role           | Author role                    | String           |
| language       | Author language                | String           |

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/{id}/reviews` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property Id.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.

## Get Photos

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/19680922/photos?state=CA&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/airbnb-property/19680922/photos?state=CA&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/airbnb-property/19680922/photos');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/airbnb-property/19680922/photos?state=CA&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "photos": [
      {
        "id": 337504512,
        "picture": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=large",
        "sort_order": 1,
        "caption": "Livingroom area with Recliner chair, sofa/sleeper, coffee table",
        "large": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=mini_square",
        "scrim_color": "#261005",
        "small": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAUAAAAECAIAAADJUWIXAAAAS0lEQVQIHQFAAL//AYx0WAcJDQoD+grsvxQcKQGomoX8CBUQAvYF1YcHH1EBSioU/gsQBwkKNxry/PL2AXNBIgwZFx0fH//z6+Te148yFxTxIM31AAAAAElFTkSuQmCC",
        "x_large": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/8239be3b-34a2-4b7e-b457-0eb695394f68.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514315,
        "picture": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=large",
        "sort_order": 2,
        "caption": "Livingroom area showing queen size bed",
        "large": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=mini_square",
        "scrim_color": "#230F06",
        "small": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAUAAAAECAIAAADJUWIXAAAAS0lEQVQIHQFAAL//AXlRKPX9BRkdHvj7AfDn3gGPXiji9xBOZ4D18/DQr48BWTof8e/7DSQs//v3Hgz1AYRmSg8TF+jx+NLJwf/18w9IIn8/TQnwAAAAAElFTkSuQmCC",
        "x_large": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/5268e49f-f7d3-463e-aaf9-aa33f4daabf2.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514414,
        "picture": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=large",
        "sort_order": 3,
        "caption": "Dining Area",
        "large": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=mini_square",
        "scrim_color": "#231E1B",
        "small": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/AZqAZhkbIAgKCtTOyQGMcFwiFf3z9/z9+/sBkYZ8BPPe8fL3CgYBAYSDgefb3uvr5iwxJgFgYWb2+fvl39YD/vUK0yMhvhSWjQAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/fbbe5275-7059-451c-bd2c-05bf94586ec4.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514492,
        "picture": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=large",
        "sort_order": 4,
        "caption": "Galley Kitchen with period cabinets, nice size refrigerator/freezer and updated granite counter tops",
        "large": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=mini_square",
        "scrim_color": "#321108",
        "small": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/AamOceDg4RIUE/rx7AG0noLd19EsOkj11rgBtqWUz8jAHSAk//HjAaqtr93Aq/z69vXv6wGdrLPmwavm188rMjfs0Cfakj9QNAAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/8d7546da-bb03-4759-bbca-2a65ce2890af.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514550,
        "picture": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=large",
        "sort_order": 5,
        "caption": "Kitchen has 4 burner gas range oven/broiler, built in microwave and stainless steel sink",
        "large": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=mini_square",
        "scrim_color": "#623D20",
        "small": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAUAAAAECAIAAADJUWIXAAAAS0lEQVQIHQFAAL//AbmUbvXiyvHu7Q8UGRg0TgHRuqH92qcADSkBBxUcQl8Bq4Ff/Pbr5PIDHSQpNk9jAcPKyPDe0uXKuAcOGDxXaNk1HdTVxRasAAAAAElFTkSuQmCC",
        "x_large": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/642bb902-5967-4d68-b071-38e2dc6d8f9e.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514646,
        "picture": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=large",
        "sort_order": 6,
        "caption": "In kitchen looking at dining area",
        "large": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=mini_square",
        "scrim_color": "#2C180F",
        "small": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAUAAAAECAIAAADJUWIXAAAAS0lEQVQIHQFAAL//Ab2JPggJBQAA/wP88t/wCAGog1csQFzd1s3lzaYIEhkBnX1UIjti6d7WAOW1BAoHAZJxTev+EQYA+hD33+Dn4GWFHQtIYnX0AAAAAElFTkSuQmCC",
        "x_large": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/9ec61251-5d80-48bf-9be2-a87956ab66af.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514752,
        "picture": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=large",
        "sort_order": 7,
        "caption": "Bathroom vanity with updated vessel sink and granite countertops ",
        "large": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=mini_square",
        "scrim_color": "#39230E",
        "small": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/AbKXdismEuz2DczCzgGpqaMqEe7b5gLn1NABkYl/DPvmChMl7d3XAXVVNhAWHPHv8Q4LEwFWPSYtKi39+egCAgr+lRywRSWShwAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/5df7d3e5-98f5-486e-ac4b-330edc142e0e.jpg?aki_policy=xx_large"
      },
      {
        "id": 337514847,
        "picture": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=large",
        "sort_order": 8,
        "caption": "Large walk-in closet",
        "large": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=mini_square",
        "scrim_color": "#1E202C",
        "small": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/Ab+kehMWGwkKC5WXugGmlnshJTDj7P6nmZ4BjYRyFBgj0eD31L22AYqCcdvd6env+P8A+QGKfmivuM34/wUdIB/TtSCmT7p/WAAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/e429266b-c6d9-44bd-9020-8f0172b1d1f2.jpg?aki_policy=xx_large"
      },
      {
        "id": 337515159,
        "picture": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=large",
        "sort_order": 9,
        "caption": "",
        "large": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=mini_square",
        "scrim_color": "#14100D",
        "small": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/AZmFZvX1+9/m8ycyPAGgj2/t5ebr7/1RZXUBqZx+49nb7u/7Wm9/AVYxIQ0PC9/2/y4uNAFIMyj48vPmAAsZHCjOOiGPSJGPcQAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/97d29a00-c93a-493b-93e5-9f50db3c6d71.jpg?aki_policy=xx_large"
      },
      {
        "id": 459520697,
        "picture": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=large",
        "sort_order": 10,
        "caption": "Bathtub / shower combination ",
        "large": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=mini_square",
        "scrim_color": "#42311F",
        "small": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/AdnMvdLOzNTOxf76+AHTxbrd29jPyb8FAgABx7qw4d/c2dPJA/77AcOyqNfZ1dXQyg4KBQGllYjt7er08/ILCQSfWClOjvre5gAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/e36b36f8-9377-4ca1-9ad5-e4ba3ec7d3c1.jpg?aki_policy=xx_large"
      },
      {
        "id": 459521152,
        "picture": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=large",
        "sort_order": 11,
        "caption": "Tile shelf’s in shower with ample supplies to get started ",
        "large": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=large",
        "large_cover": "https://a0.muscache.com/ac/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?interpolation=lanczos-none&size=large_cover&output-format=jpg&output-quality=70",
        "medium": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=medium",
        "mini_square": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=mini_square",
        "scrim_color": "#521B07",
        "small": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=small",
        "thumbnail": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=small",
        "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAQAAAAFCAIAAADtz9qMAAAATElEQVQIHQFBAL7/Ac6ujfr5+OPj4ufp7QHOrY/2+PjV1tX19fYBx6iL9PX20dPS6d7gAb6hhvb19dLT0vz3+AGxlXz5+PfQ09ABAAFpTy/rv9tePwAAAABJRU5ErkJggg==",
        "x_large": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=x_large",
        "x_large_cover": "https://a0.muscache.com/ac/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?interpolation=lanczos-none&size=x_large_cover&output-format=jpg&output-quality=70",
        "x_medium": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=x_medium",
        "x_small": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=x_small",
        "xl_picture": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=x_large",
        "xx_large": "https://a0.muscache.com/im/pictures/3319c11d-8560-49c1-95e3-50c98de40781.jpg?aki_policy=xx_large"
      }
    ]
  }
}
```

This endpoint retrieves all listings photos, with their orders and different sizes.

### Photo Object Data Dictionary
| Attribute     | Definition          | Possible Returns |
|---------------|---------------------|------------------|
| id            | ID of the photo     | Integer          |
| picture       | Main url            | String           |
| sort_order    | Photo sorting order | Integer          |
| caption       | Photo caption       | String           |
| large         |                     | String           |
| large_cover   |                     | String           |
| medium        |                     | String           |
| mini_square   |                     | String           |
| scrim_color   |                     | String           |
| small         |                     | String           |
| thumbnail     |                     | String           |
| x_large       |                     | String           |
| x_large_cover |                     | String           |
| x_medium      |                     | String           |
| x_small       |                     | String           |
| xl_picture    |                     | String           |
| xx_large      |                     | String           |

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/{id}/photos` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property Id.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.

## Get Airbnb Calendars

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/airbnb-property/19680922/calendar?state=CA&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/airbnb-property/19680922/calendar?state=CA&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/airbnb-property/19680922/calendar');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/airbnb-property/19680922/calendar?state=CA&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "id": 19680922,
    "created_at": "2018-07-31T23:02:34.752Z",
    "updated_at": "2019-07-25T21:40:49.824Z",
    "calendar_2019": {
      "metadata": "N/A",
      "calendar_months": [
        {
          "abbr_name": "May",
          "day_names": [
            "Mon",
            "Tue",
            "Wed",
            "Thu",
            "Fri",
            "Sat",
            "Sun"
          ],
          "days": [
            {
              "available": false,
              "date": "2019-04-29",
              "available_for_checkin": false,
              "price": {
                "date": "2019-04-29",
                "local_adjusted_price": 105,
                "local_currency": "USD",
                "local_price": 105,
                "native_adjusted_price": 105,
                "native_currency": "USD",
                "native_price": 105,
                "type": "default",
                "local_price_formatted": "$105",
                "is_price_upon_request": null
              },
              "min_nights": 30,
              "max_nights": 180
            },
            {
              "available": false,
              "date": "2019-04-30",
              "available_for_checkin": false,
              "price": {
                "date": "2019-04-30",
                "local_adjusted_price": 105,
                "local_currency": "USD",
                "local_price": 105,
                "native_adjusted_price": 105,
                "native_currency": "USD",
                "native_price": 105,
                "type": "default",
                "local_price_formatted": "$105",
                "is_price_upon_request": null
              },
              "min_nights": 30,
              "max_nights": 180
            },
            {
              "available": false,
              "date": "2019-05-01",
              "available_for_checkin": false,
              "price": {
                "date": "2019-05-01",
                "local_adjusted_price": 105,
                "local_currency": "USD",
                "local_price": 105,
                "native_adjusted_price": 105,
                "native_currency": "USD",
                "native_price": 105,
                "type": "default",
                "local_price_formatted": "$105",
                "is_price_upon_request": null
              },
              "min_nights": 30,
              "max_nights": 180
            },
            {
              "available": false,
              "date": "2019-05-02",
              "available_for_checkin": false,
              "price": {
                "date": "2019-05-02",
                "local_adjusted_price": 105,
                "local_currency": "USD",
                "local_price": 105,
                "native_adjusted_price": 105,
                "native_currency": "USD",
                "native_price": 105,
                "type": "default",
                "local_price_formatted": "$105",
                "is_price_upon_request": null
              },
              "min_nights": 30,
              "max_nights": 180
            },
            {
              "available": false,
              "date": "2019-05-03",
              "available_for_checkin": false,
              "price": {
                "date": "2019-05-03",
                "local_adjusted_price": 105,
                "local_currency": "USD",
                "local_price": 105,
                "native_adjusted_price": 105,
                "native_currency": "USD",
                "native_price": 105,
                "type": "default",
                "local_price_formatted": "$105",
                "is_price_upon_request": null
              },
              "min_nights": 30,
              "max_nights": 180
            },
            {
              "available": false,
              "date": "2019-05-04",
              "available_for_checkin": false,
              "price": {
                "date": "2019-05-04",
                "local_adjusted_price": 105,
                "local_currency": "USD",
                "local_price": 105,
                "native_adjusted_price": 105,
                "native_currency": "USD",
                "native_price": 105,
                "type": "default",
                "local_price_formatted": "$105",
                "is_price_upon_request": null
              },
              "min_nights": 30,
              "max_nights": 180
            },
            ...
          ],
          "prices_to_be_highlighted": null
        },
        ...
      ]
    }
  }
}
```

This endpoint retrieves an array of month by month, and day per day for each day availability and day booking price, below is an explanation for each day object elements.

### Calendars Data Dictionary
| Attribute     | Definition            | Possible Returns |
|---------------|-----------------------|------------------|
| calendar_2014 | Calendar days of 2014 | Calendar object  |
| calendar_2015 | Calendar days of 2015 | Calendar object  |
| calendar_2016 | Calendar days of 2016 | Calendar object  |
| calendar_2017 | Calendar days of 2017 | Calendar object  |
| calendar_2018 | Calendar days of 2018 | Calendar object  |
| calendar_2019 | Calendar days of 2019 | Calendar object  |

### Calendar Data Dictionary
| Attribute            | Definition                                                | Possible Returns |
|----------------------|-----------------------------------------------------------|------------------|
| available            | Indicator whether the day is available for booking or not | Boolean          |
| date                 | The date of the day                                       | Date             |
| local_adjusted_price | The local price for that day                              | Integer          |
| local_currency       | The local price currency                                  | String           |
| native_price         | The native price for that day of booking                  | Integer          |

### HTTP Request

`GET https://api-build.mashvisor.com/v2/airbnb-property/{id}/calendar` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The Airbnb property Id.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the property should be provided to the api or api will throw error 404.





## Get Historical Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/neighborhood/268201/historical/airbnb?_t=meowmeowmeow&average_by=revenue&state=CA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/neighborhood/268201/historical/airbnb?_t=meowmeowmeow&average_by=revenue&state=CA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/neighborhood/268201/historical/airbnb');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/neighborhood/268201/historical/airbnb?_t=meowmeowmeow&average_by=revenue&state=CA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured for occupancy category like this:

```json
{
    "status": "success",
    "content": {
        "results": [
            {
                "year": 2018,
                "month": 10,
                "value": 71
            },
            {
                "year": 2018,
                "month": 11,
                "value": 42
            },
            {
                "year": 2018,
                "month": 12,
                "value": 17
            },
            {
                "year": 2019,
                "month": 1,
                "value": 65
            },
            {
                "year": 2019,
                "month": 2,
                "value": 76
            },
            {
                "year": 2019,
                "month": 3,
                "value": 83
            },
            {
                "year": 2019,
                "month": 4,
                "value": 73
            },
            {
                "year": 2019,
                "month": 5,
                "value": 84
            },
            {
                "year": 2019,
                "month": 6,
                "value": 79
            },
            {
                "year": 2019,
                "month": 7,
                "value": 79
            },
            {
                "year": 2019,
                "month": 8,
                "value": 66
            },
            {
                "year": 2019,
                "month": 9,
                "value": 55
            }
        ]
    },
    "message": "Historical Data fetched successfully"
}
```

> The above command returns JSON structured for revenue category like this:

```json
{
    "status": "success",
    "content": {
        "results": [
            {
                "year": 2018,
                "month": 10,
                "value": 6056
            },
            {
                "year": 2018,
                "month": 11,
                "value": 3767
            },
            {
                "year": 2018,
                "month": 12,
                "value": 1797
            },
            {
                "year": 2019,
                "month": 1,
                "value": 4739
            },
            {
                "year": 2019,
                "month": 2,
                "value": 5738
            },
            {
                "year": 2019,
                "month": 3,
                "value": 5970
            },
            {
                "year": 2019,
                "month": 4,
                "value": 4398
            },
            {
                "year": 2019,
                "month": 5,
                "value": 5751
            },
            {
                "year": 2019,
                "month": 6,
                "value": 5398
            },
            {
                "year": 2019,
                "month": 7,
                "value": 6004
            },
            {
                "year": 2019,
                "month": 8,
                "value": 4999
            },
            {
                "year": 2019,
                "month": 9,
                "value": 3998
            }
        ]
    },
    "message": "Historical Data fetched successfully"
}
```

Get a submarket (neighborhood) short term historical performance for its listings as an array


### HTTP Request

`GET https://api.mashvisor.com/v2/neighborhood/{id}/historical/airbnb` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | Neighborhood id to fetch data for

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
percentile_rate | Double | 1 | Percentile rate
average_by | String | occupancy | Neighborhood id you're targeting. <br> Possbile Inputs: <br> * occupancy <br> * price <br> * revenue
category | String | | AirBnB category type. <br> Possbile Inputs: <br> * flat <br> * house <br> * apartment <br> * loft
beds | Integer | | 0 to 4 bedrooms value

## Get Listings

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/active-listings?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/active-listings?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/active-listings');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/active-listings?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "properties": [
            {
                "id": 18894069,
                "propertyId": "4733174",
                "source": "Airbnb",
                "nightPrice": 307,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1.5,
                "numOfRooms": 3,
                "name": "Huge Apt in Lincoln Park Mansion!",
                "address": "Chicago, IL, United States",
                "airbnbNeighborhood": "Lincoln Park",
                "airbnbCity": "Chicago",
                "capacityOfPeople": 9,
                "zip": "60614",
                "propertyType": "Apartment",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 51,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2017-07-08T18:29:04.000Z",
                "updatedAt": "2017-07-08T18:29:04.000Z",
                "numOfBeds": 5,
                "lat": "41.92822647094727",
                "lon": "-87.64620208740234",
                "image": "https://a0.muscache.com/im/pictures/c9b83f11-4d98-4ce0-afba-5ee06b3b7d7e.jpg?aki_policy=medium"
                "nightRate": 307,
                "property_id": "4733174",
                "airbnbZIP": "60614"
            },
            {
                "id": 18894071,
                "propertyId": "14222880",
                "source": "Airbnb",
                "nightPrice": 164,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1,
                "numOfRooms": 2,
                "name": "Lincoln park spacious 2.5 bedroom",
                "address": "Chicago, IL 60614, United States",
                "airbnbNeighborhood": "Lincoln Park",
                "airbnbCity": "Chicago",
                "capacityOfPeople": 6,
                "zip": "60614",
                "propertyType": "Condominium",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 15,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2017-07-08T18:29:08.000Z",
                "updatedAt": "2017-07-08T18:29:08.000Z",
                "numOfBeds": 3,
                "lat": "41.91649627685547",
                "lon": "-87.65447998046875",
                "image": "https://a0.muscache.com/im/pictures/9e351be6-21f6-4b23-b741-62e08da102f1.jpg?aki_policy=medium",
                "nightRate": 164,
                "property_id": "14222880",
                "airbnbZIP": "60614"
            },
            {
                "id": 18894074,
                "propertyId": "9577653",
                "source": "Airbnb",
                "nightPrice": 128,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1,
                "numOfRooms": 1,
                "name": "Modern Lincoln Park 1bd 1ba Parking",
                "address": "Chicago, IL 60614, United States",
                "airbnbNeighborhood": "Lincoln Park",
                "airbnbCity": "Chicago",
                "capacityOfPeople": 3,
                "zip": "60614",
                "propertyType": "Apartment",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 57,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2017-07-08T18:29:12.000Z",
                "updatedAt": "2017-07-08T18:29:12.000Z",
                "numOfBeds": 1,
                "lat": "41.92398071289063",
                "lon": "-87.66230773925781",
                "image": "https://a0.muscache.com/im/pictures/15e2919c-bab4-4071-a907-2e7454851cf8.jpg?aki_policy=medium",
                "nightRate": 128,
                "property_id": "9577653",
                "airbnbZIP": "60614"
            }
        ],
        "num_of_properties": 114,
        "num_page_properties": 3,
        "page": "1"
    }
}
```

List all active short term rentals for a specific location: city, zip code, or a neighborhood.

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/active-listings` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.
page | Integer | | Page number
items | Integer | 4 | Items number per page.

## Get Market Summary

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/market-summary?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/market-summary?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/market-summary');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/market-summary?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "listings_count": 161,
    "average_occupancy": 82.7578,
    "average_price": 191.5714,
    "rental_income": 3,
    "property_types": 3,
    "occupancy_histogram": {
      "average_occupancy": 193,
      "histogram": [
        50.4,
        23.3,
        43.2,
        56.4,
        80.4,
        43.2,
        21.1,
        41,
        26.3,
        37.3,
        64.7,
        90.1,
        11.3
      ]
    },
    "night_price_histogram": {
      "average_price": 153,
      "histogram": [
        134,
        126,
        137,
        152,
        161,
        150,
        168,
        160,
        151,
        145,
        156,
        114,
        116
      ]
    }
  }
}
```

Get a summary an overview for a specific location: city, zip code, or a neighborhood.

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/market-summary` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.

## Get Airbnb Occupancy Rates

For each Airbnb listing, we calculate its occupancy rate, month per month, and an annual rate, and we offer our clients a 12-month historical performance for the occupancy rates. We store each listing’s bookings and calendar since the day the listing became active over AirBnB. <br>
We have access to a day per day performance, nightly price, and if the property was available for booking or not. So for each month, we check day over day if it was booked or not, and how much the host made off that booking, whether it was a one night booking, or a booking for a few nights in a row. <br>
Sometimes, a host makes the listing calendar look like it’s occupied and not available for booking, even though it is not booked by a guest. Generally speaking, this might cause inaccurate calculations for the occupancy rates and the listing rental rate. At Mashvisor, we have identified this issue and solved it by the continuous hard working cycle over cycle over the past 4 years to enhance how we calculate the occupancy and to verify if a night was really booked or only blocked by the host from booking.<br>
We also calculate the nightly price rate based on the nights that were actually booked. We calculate the nightly price as the average of all booked nights in a month.<br>
Also, when Mashvisor sees a month is almost fully booked, we review the month’s reviews and compare it to the number of bookings. This guarantees the bookings are real and the data and calculation we made are right. If the validation fails, we don’t consider the month’s bookings.
Finally, the listing’s occupancy rate is calculated as the average (mean) occupancy rate of the previous 12 months’ occupancies to make sure that seasonality is considered in the analysis. 

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/occupancy-rates?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/occupancy-rates?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/occupancy-rates');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/occupancy-rates?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "studio": 57.2,
    "one_bedroom": 82.75,
    "two_bedrooms": 71.4,
    "three_bedrooms": 72.76,
    "four_bedrooms": 55.26
  }
}
```

Market occupancy rates for a zip code or a neighborhood.

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/occupancy-rates` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.

## Get Property Types

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/property-types?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/property-types?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/property-types');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/property-types?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "Apartment": 4,
    "House": 21,
    "Serviced apartment": 14,
    "Townhouse": 3,
    "Condominium": 6
  }
}
```

Check all market property types for a zip code or a neighborhood and return their counts.
###Available Property Types:
* Apartment
* Other
* House
* Bed & Breakfast
* Condominium
* Townhouse
* Loft
* Cottage
* Guesthouse
* Farm stay
* Bungalow
* Guest suite
* Cabin
* Barn
* Dome house
* Villa
* Chalet
* Tiny house
* Serviced apartment
* Bed and breakfast
* Earth house
* Lighthouse
* Nature lodge

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/property-types` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.

## Get Super Hosts

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/super-hosts?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/super-hosts?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/super-hosts');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/super-hosts?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": [
    {
      "first_name": "Jeff",
      "has_profile_pic": true,
      "id": 12703126,
      "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
      "smart_name": "Jeff",
      "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small",
      "acceptance_rate": "N/A",
      "created_at": "2014-03-01T21:16:11Z",
      "identity_verified": false,
      "is_superhost": true,
      "picture_large_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_large",
      "recommendation_count": 0,
      "response_rate": "100%",
      "response_time": "within an hour",
      "reviewee_count": 24,
      "thumbnail_medium_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_medium",
      "neighborhood": "Chinatown",
      "verification_labels": [
        "Email address",
        "Phone number",
        "Reviewed"
      ],
      "verifications": [
        "email",
        "phone",
        "reviews"
      ],
      "about": "Friendly, accomadating, respectful, polite, easy going regular person. ",
      "all_active_phone_numbers": [],
      "friends_count": 0,
      "guidebooks_count": 0,
      "has_available_payout_info": true,
      "identity_mt_verified": false,
      "identity_v2_verified": false,
      "is_generated_user": false,
      "is_trip_host": false,
      "is_marketplace_cohost": false,
      "languages": [
        "English"
      ],
      "listings_count": 5,
      "location": "San Francisco, CA",
      "recent_recommendation": null,
      "recent_review": {
        "review": {
          "comments": "Jeff is a wonderful host! He responds to questions and concerns very promptly. The place is small but it has everything you will need. It’s very cozy and comfortable to live in. The location is super convenient. I really enjoyed my stay!!",
          "created_at": "2019-07-16T23:27:35Z",
          "id": 489450656,
          "listing_id": 18853563,
          "reviewee_id": 12703126,
          "reviewer": {
            "user": {
              "first_name": "Lanting",
              "has_profile_pic": true,
              "id": 204093245,
              "picture_url": "https://a0.muscache.com/im/pictures/user/737bd62a-859b-400b-8a4f-42749ef8908c.jpg?aki_policy=profile_x_medium",
              "smart_name": "Lanting",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/user/737bd62a-859b-400b-8a4f-42749ef8908c.jpg?aki_policy=profile_small"
            }
          },
          "reviewer_id": 204093245,
          "role": "guest",
          "user_flag": null,
          "listing": {
            "listing": {
              "city": "San Francisco",
              "collection_ids": null,
              "country": "United States",
              "has_double_blind_reviews": false,
              "id": 18853563,
              "instant_book_enabled": false,
              "instant_bookable": false,
              "lat": 37.79252,
              "lng": -122.4081,
              "medium_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=medium",
              "name": "Nob Hill Jewel Box",
              "native_currency": "USD",
              "picture_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=large",
              "preview_encoded_png": "iVBORw0KGgoAAAANSUhEUgAAAAUAAAAECAIAAADJUWIXAAAAS0lEQVQIHQFAAL//AXNWOO7s7/r9Ae7o5iI4RgFgQiMPBQU7W3SJfnuVqbMBRjoyKCYqHiAfq6CUN0dUAUU5MBgcKdbe6frv2vPz9WRpG/xGx/8wAAAAAElFTkSuQmCC",
              "price": 100,
              "price_formatted": "$100",
              "price_native": 100,
              "scrim_color": "#120806",
              "smart_location": "San Francisco, CA",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=small",
              "user": {
                "user": {
                  "first_name": "Jeff",
                  "has_profile_pic": true,
                  "id": 12703126,
                  "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
                  "smart_name": "Jeff",
                  "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
                }
              },
              "user_id": 12703126,
              "x_medium_picture_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=x_medium",
              "xl_picture_url": "https://a0.muscache.com/im/pictures/aeb9bdc7-2fad-4072-a8d3-4e65e9366042.jpg?aki_policy=x_large"
            }
          },
          "reviewee": {
            "user": {
              "first_name": "Jeff",
              "has_profile_pic": true,
              "id": 12703126,
              "picture_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_x_medium",
              "smart_name": "Jeff",
              "thumbnail_url": "https://a0.muscache.com/im/pictures/7406e94f-e5b0-4ba4-9739-eb90b739bef5.jpg?aki_policy=profile_small"
            }
          }
        }
      },
      "school": "High school, some college",
      "show_travel_for_work": false,
      "signup_method": 0,
      "total_listings_count": 5,
      "user_flag": null,
      "work": "Property management "
    },
    ...
  ]
}
```

Obtain a list of all market super hosts for a zip code or a neighborhood.

### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/super-hosts` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.

## Get Top Reviewed Homes

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/top-reviewed?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/top-reviewed?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/top-reviewed');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/top-reviewed?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "properties": [
            {
                "id": 21131720,
                "propertyId": "20992111",
                "source": "Airbnb",
                "status": "ACTIVE",
                "nightPrice": 235,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 2,
                "numOfRooms": 4,
                "occupancy": 56,
                "rentalIncome": 3948,
                "airbnbNeighborhoodId": 397651,
                "name": "Perfect getaway in the Hudson Valley",
                "address": "Red Hook, NY, United States",
                "airbnbNeighborhood": null,
                "airbnbCity": "Red Hook",
                "state": "NY",
                "capacityOfPeople": 6,
                "zip": "12571",
                "propertyType": "House",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 166,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2019-08-19T16:00:19.000Z",
                "updatedAt": "2019-08-19T16:00:19.000Z",
                "numOfBeds": 4,
                "lat": 41.9516716003418,
                "lon": -73.77474975585938,
                "image": "https://a0.muscache.com/im/pictures/883b6146-c323-45f7-a3c0-3339b36c3fbd.jpg?aki_policy=medium",
                "url": null,
                "rental_income": 3948.0000000000005,
                "neighborhood": {
                    "id": 397651,
                    "name": null
                },
                "nightRate": 235,
                "property_id": "20992111",
                "airbnbZIP": "12571",
                "distance": 6.204173070158869,
                "similarity": 0.5
            },
            {
                "id": 21131669,
                "propertyId": "15235032",
                "source": "Airbnb",
                "status": "ACTIVE",
                "nightPrice": 268,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1.5,
                "numOfRooms": 2,
                "occupancy": 84,
                "rentalIncome": 6754,
                "airbnbNeighborhoodId": 397651,
                "name": "Modern Upstate NY cabin + hot pool in the woods.",
                "address": "Red Hook, NY, United States",
                "airbnbNeighborhood": null,
                "airbnbCity": "Red Hook",
                "state": "NY",
                "capacityOfPeople": 6,
                "zip": "12571",
                "propertyType": "Cabin",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 152,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2019-08-19T15:59:49.000Z",
                "updatedAt": "2019-08-19T15:59:49.000Z",
                "numOfBeds": 3,
                "lat": 42.00767135620117,
                "lon": -73.7533187866211,
                "image": "https://a0.muscache.com/im/pictures/b0831a76-9ea9-4e45-97f1-29edab749b27.jpg?aki_policy=medium",
                "url": null,
                "rental_income": 6753.599999999999,
                "neighborhood": {
                    "id": 397651,
                    "name": null
                },
                "nightRate": 268,
                "property_id": "15235032",
                "airbnbZIP": "12571",
                "distance": 4.958961405286708,
                "similarity": 0.48
            },
            {
                "id": 21131735,
                "propertyId": "5602615",
                "source": "Airbnb",
                "status": "ACTIVE",
                "nightPrice": 965,
                "weeklyPrice": 4000,
                "monthlyPrice": 10000,
                "numOfBaths": 2.5,
                "numOfRooms": 4,
                "occupancy": 21,
                "rentalIncome": 6080,
                "airbnbNeighborhoodId": 397651,
                "name": "Lovely Hudson Valley Country Home",
                "address": "Red Hook, NY, United States",
                "airbnbNeighborhood": null,
                "airbnbCity": "Red Hook",
                "state": "NY",
                "capacityOfPeople": 8,
                "zip": "12571",
                "propertyType": "House",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 103,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2019-08-19T16:00:26.000Z",
                "updatedAt": "2019-08-19T16:00:26.000Z",
                "numOfBeds": 4,
                "lat": 42.0384407043457,
                "lon": -73.8933334350586,
                "image": "https://a0.muscache.com/im/pictures/98264481/28aadc99_original.jpg?aki_policy=medium",
                "url": null,
                "rental_income": 6079.5,
                "neighborhood": {
                    "id": 397651,
                    "name": null
                },
                "nightRate": 965,
                "property_id": "5602615",
                "airbnbZIP": "12571",
                "distance": 2.569544555210685,
                "similarity": 0.53
            }
        ],
        "num_of_properties": 23,
        "num_page_properties": 3,
        "page": "3"
    }
}
```
List all short term rentals of top reviewed and most counts of reviews for a specific location: city, zip code, or a neighborhood.
### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/top-reviewed` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.
reviews_count | Integer | 30 | Any valid integer to fetch listings counts more than the number.

## Get Newly Listed Homes

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v2/airbnb-property/newly-listed?state=CA&city=San%20Francisco&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v2/airbnb-property/newly-listed?state=CA&city=San%20Francisco&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/airbnb-property/newly-listed');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San%20Francisco',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api.mashvisor.com/v2/airbnb-property/newly-listed?state=CA&city=San%20Francisco&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "properties": [
            {
                "id": 18894069,
                "propertyId": "4733174",
                "source": "Airbnb",
                "nightPrice": 307,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1.5,
                "numOfRooms": 3,
                "name": "Huge Apt in Lincoln Park Mansion!",
                "address": "Chicago, IL, United States",
                "airbnbNeighborhood": "Lincoln Park",
                "airbnbCity": "Chicago",
                "capacityOfPeople": 9,
                "zip": "60614",
                "propertyType": "Apartment",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 51,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2017-07-08T18:29:04.000Z",
                "updatedAt": "2017-07-08T18:29:04.000Z",
                "numOfBeds": 5,
                "lat": "41.92822647094727",
                "lon": "-87.64620208740234",
                "image": "https://a0.muscache.com/im/pictures/c9b83f11-4d98-4ce0-afba-5ee06b3b7d7e.jpg?aki_policy=medium"
                "nightRate": 307,
                "property_id": "4733174",
                "airbnbZIP": "60614"
            },
            {
                "id": 18894071,
                "propertyId": "14222880",
                "source": "Airbnb",
                "nightPrice": 164,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1,
                "numOfRooms": 2,
                "name": "Lincoln park spacious 2.5 bedroom",
                "address": "Chicago, IL 60614, United States",
                "airbnbNeighborhood": "Lincoln Park",
                "airbnbCity": "Chicago",
                "capacityOfPeople": 6,
                "zip": "60614",
                "propertyType": "Condominium",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 15,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2017-07-08T18:29:08.000Z",
                "updatedAt": "2017-07-08T18:29:08.000Z",
                "numOfBeds": 3,
                "lat": "41.91649627685547",
                "lon": "-87.65447998046875",
                "image": "https://a0.muscache.com/im/pictures/9e351be6-21f6-4b23-b741-62e08da102f1.jpg?aki_policy=medium",
                "nightRate": 164,
                "property_id": "14222880",
                "airbnbZIP": "60614"
            },
            {
                "id": 18894074,
                "propertyId": "9577653",
                "source": "Airbnb",
                "nightPrice": 128,
                "weeklyPrice": 0,
                "monthlyPrice": 0,
                "numOfBaths": 1,
                "numOfRooms": 1,
                "name": "Modern Lincoln Park 1bd 1ba Parking",
                "address": "Chicago, IL 60614, United States",
                "airbnbNeighborhood": "Lincoln Park",
                "airbnbCity": "Chicago",
                "capacityOfPeople": 3,
                "zip": "60614",
                "propertyType": "Apartment",
                "roomType": "Entire home/apt",
                "roomTypeCategory": "entire_home",
                "amenities": null,
                "reviewsCount": 57,
                "startRating": 5,
                "reviews": null,
                "createdAt": "2017-07-08T18:29:12.000Z",
                "updatedAt": "2017-07-08T18:29:12.000Z",
                "numOfBeds": 1,
                "lat": "41.92398071289063",
                "lon": "-87.66230773925781",
                "image": "https://a0.muscache.com/im/pictures/15e2919c-bab4-4071-a907-2e7454851cf8.jpg?aki_policy=medium",
                "nightRate": 128,
                "property_id": "9577653",
                "airbnbZIP": "60614"
            }
        ],
        "num_of_properties": 114,
        "num_page_properties": 3,
        "page": "1"
    }
}
```

List all short term rentals that are recently listed for a specific location: city, zip code, or a neighborhood.
### HTTP Request

`GET https://api.mashvisor.com/v2/airbnb-property/newly-listed` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
city | String | | A specific city you're looking for.
neighborhood | Long | | Neighborhood id you're targeting
zip_code | Integer | | Any postal zip code.
page | Integer | | Page number
items | Integer | 4 | Items number per page.

# Long Term Rentals
## The Traditional Property Object
> The Traditional Property Object:

```json
{
  "id": 5637233,
  "title": "Condominium, Traditional - Los Angeles (City), CA",
  "lon": -118.381,
  "lat": 34.0568,
  "state": "CA",
  "city": "Los Angeles",
  "county": "LOS ANGELES",
  "neighborhood": {
    "id": 275024,
    "name": "Pico-Robertson",
    "country": "United States",
    "city": "Los Angeles",
    "state": "CA",
    "latitude": 34.053022,
    "longitude": -118.383312,
    "singleHomeValue": 1237000,
    "mashMeter": 66.99,
    "description": null,
    "is_village": 0
  },
  "description": "Bright and modern one bedroom condo for lease located in convenient and desirable Beverly Hills adjacent location. Don't miss this very spacious unit with open floor plan and extra large patio for additional outdoor living space. Features include: Wood floors, recessed lighting, clean kitchen with stainless appliances, remodeled bathroom and walk in closet. Property has central heat and air, in unit washer/dryer and 2 parking spaces.  Amazing location near Cedars-Sinai, Century City and all the parks, shops and restaurants of Beverly Hills.",
  "price": 3300,
  "baths": 1,
  "beds": 1,
  "num_of_units": null,
  "sqft": 1028,
  "lot_size": 12787,
  "days_on_market": 3,
  "year_built": 1981,
  "tax": null,
  "tax_history": null,
  "videos": null,
  "virtual_tours": null,
  "parking_spots": 2,
  "parking_type": "Garage",
  "walkscore": null,
  "mls_id": "19508890",
  "image": "http://photos.listhub.net/CLAWCA/19508890/1?lm=20190911T083436",
  "extra_images": [
    "http://photos.listhub.net/CLAWCA/19508890/1?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/2?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/3?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/4?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/5?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/6?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/7?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/8?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/9?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/10?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/11?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/12?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/13?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/14?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/15?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/16?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/17?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/18?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/19?lm=20190911T083436",
    "http://photos.listhub.net/CLAWCA/19508890/20?lm=20190911T083436"
  ],
  "zipcode": "90035",
  "address": "1110 South SHENANDOAH Street #2",
  "type": "apartment",
  "property_type": "Rental",
  "property_sub_type": "Condominium",
  "status": "Active",
  "listhub_key": "3yd-CLAWCA-19508890",
  "broker_name": "Compass",
  "broker_number": null,
  "broker_url": "https://www.compass.com/",
  "source": "Compass",
  "mls_name": "Combined LA Westside Multiple Listing Service, Inc",
  "original_source": "Listhub",
  "architecture_style": "New Traditional",
  "has_pool": null,
  "is_water_front": null,
  "heating_system": "Central Furnace",
  "cooling_system": "Central A/C",
  "view_type": null,
  "schools": null,
  "parcel_number": "4332019046",
  "neighborhood_id": 275024,
  "url": "https://listings.listhub.net/pages/CLAWCA/19508890/?channel=mashv",
  "listing_date": "2019-09-09T00:00:00.000Z",
  "modification_timestamp": "2019-09-11T08:33:26.000Z",
  "created_at": "2019-09-12T04:50:05.000Z",
  "updated_at": "2019-09-12T05:31:02.000Z",
  "agents": [
    {
      "id": 101289,
      "agent_id": 101289,
      "property_id": 5637233,
      "created_at": "2017-06-21T09:37:15.000Z",
      "updated_at": "2019-09-01T09:43:53.000Z",
      "first_name": "Nikki",
      "last_name": "Hochstein",
      "email": "nik@nikkih.com",
      "primary_phone": "(310) 968-1116",
      "phone_number": "(310) 437-7500",
      "role": "Listing",
      "office_id": 1643,
      "website": "https://www.compass.com/",
      "address": "2113-2115 Main St.",
      "city": "SANTA MONICA",
      "state": "CA",
      "county": "Los Angeles",
      "zip_code": "90405",
      "company": "Compass",
      "image": "http://brokerlogos.listhub.net/CLAWCA/acbfbc71874811e5803c125f38ce48fb/20160601185736249.png",
      "real_estate_licence": "01338003",
      "years_of_experience": null,
      "areas_served": null,
      "agent_specialities": null,
      "agent_experience": null,
      "summary": null,
      "title": null,
      "mls_id": null,
      "price_range": null,
      "sold_properties": null,
      "active_properties": null,
      "mailchimp_transfer_date": null,
      "source": "Listhub",
      "listhub_id": "3yd-CLAWCA-X55624"
    }
  ]
}
```

Mashvisor has agreements with multiple MLS' providers and we're currently finalizing agreements with multiple others.<br><br>
We currently have in 1,5M+ rental listings in total in our databases (active and inactive). 450K+ Active rental listings from them nationwide.
Integration and agreements are the same included in MLS Listings section above.

### Traditional Property Data Dictionary

| Attribute | Definition | Possible Returns |
|-------------|-------------------------------------------------------|---------------------------|
| id          | Mashvisor Traditional Property ID                                 | Integer                   |
| title       | A short title for the property                        | String                    |
| description | Longer description of the property                    | String                    |
| type   | The property sub type as provided by the MLS provider | String <br>Possible values: <br>1. single_home <br>2.apartment <br>3.townhouse <br>4.Multi Family <br>5. Other|
| property_type | The property main type as provided by the MLS provider| String <br>Possible values: <br>* Commercial <br>* Lots And Land <br>* MultiFamily <br>* Other <br>* Rental <br>* Residential           |
| property_sub_type  | The property property listing category                                       | String <br>Possible values:  <br>* Apartment <br>* Condominium <br>* Duplex <br>* Other <br>* Quadruplex <br>* Single Family Attached <br>* Single Family Detached <br>* Townhouse <br>* Triplex                  |
| address            | The full street address of the property, ex:<br> 36981 Newark Blvd #B | String                |
| city               | The city where the property is located                                | String                |
| state              | The state where the property is located                               | String                |
| county             | County where a property is located                                    | String                |
| zipcode                | Postal code where a property is located                               | Integer               |
| neighborhood           | The neighborhood where the property is located                        | String                |
| beds               | Property full bedrooms count                                          | Integer               |
| baths              | Property full bathrooms count                                         | Integer               |
| num_of_units       | Number of units in the property, only exists with multifamily properties | Integer               |
| sqft               | Property living area in square feet unit                                 | Integer               |
| lot_size           | The lot size of the property in square feet unit                         | Integer               |
| parcel_number        | The property APN assigned by tax assessor                | String                                |
| mls_id           | The MLS ID of the property                               | String                                |
| year_built           | The year was constructed in                              | Integer                               |
| walkscore            | The walkscore value of the property address              | Integer                               |
| tax                  | The last knows tax amount                                | Integer                               |
| tax_history          | Collection of all the taxes reported for a property      | JSON Array                            |
| price           | The listed rent price for the property                        | Integer                               |
| price_per_sqft       | Price per sqft value                                     | Float                                 |
| days_on_market       | Number of days since the property was on market for sale | Integer                               |
| parking_spots        | Number of parking spots                                  | Integer                               |
| parking_type         | An indicator for the parking type                        | Integer                               |
| url                        | The URL of the property                                         | String           |
| source                     | The name of the entity authorized the property to be syndicated | String           |
| mls_name                   | The name of the MLS                                             | String           |
| broker_name                | The broker’s name                                               | String           |
| broker_number              | The broker’s phone number                                       | String           |
| lat                   | Latitude of the property                                        | Float            |
| lon                  | Longitude of the property                                       | Float            |
| heating_system             | The heating system type                                         | String           |
| cooling_system             | The cooling system type                                         | String           |
| neighborhood_id            | The property neighborhood ID                                    | Integer          |
| schools                    | Collection of all the schools nearby a property                 | JSON Array       |
| view_type                  | The property view type                                          | String <br> Possible values: <br>* Airport <br>* Average <br>* Bluff <br>* Bridge <br>* Canyon <br>* City <br>* Desert <br>* Forest <br>* Golf Course <br>* Harbor <br>* Hills <br>* Lake <br>* Marina <br>* Mountain <br>* None <br>* Ocean <br>* Other <br>* Panorama <br>* Park <br>* Ravine <br>* River <br>* Territorial <br>* Unknown <br>* Valley <br>* Vista <br>* Water |
| image          | The property main image URL                            | String                                        |
| extra_images       | List of the images associated with a property          | String                                        |
| videos             | Videos associated with a property                      | String                                        |
| virtual_tours      | Virtual tour link for a property                       | String                                        |
| listing_date       | The date when the property was listed for sale         | Date                                          |
| updated_at         | Date it’s updated in the database                      | Date                                          |
| agent_id           | The property’s agent ID associated to it               | Integer                                       |
| appliances      | A description of the appliance as provided                                                            | JSON Array <br> Possible values:<br>* BarbequeorGrill <br>* CoffeeSystem <br>* CoffeeSystem-Roughin <br>* Cooktop <br>* Cooktop-Electric <br>* Cooktop-Electric2burner <br>* Cooktop-Electric6burner <br>* Cooktop-Gas <br>* Cooktop-Gas2burner <br>* Cooktop-Gas5burner <br>* Cooktop-Gas6burner <br>* Cooktop-GasCustom <br>* Cooktop-Induction <br>* Cooktop-Induction2burner <br>* Cooktop-Induction6burner <br>* Dishwasher <br>* Dishwasher-Drawer <br>* Dishwasher-Twoormore <br>* Dryer <br>* Dryer-Dualfuel <br>* Dryer-Electric110V <br>* Dryer-Electric220V <br>* Dryer-Gas <br>* Dryer-Gasroughin <br>* Freezer <br>* Freezer-Compact <br>* Freezer-Upright <br>* GarbageDisposer <br>* IceMaker <br>* Microwave <br>* None <br>* Other <br>* Oven <br>* Oven-Convection <br>* Oven-Double <br>* Oven-DoubleElectric <br>* Oven-DoubleGas <br>* Oven-Gas <br>* Oven-Gas3wide <br>* Oven-Self-Cleaning <br>* Oven-Steam <br>* Oven-Twin <br>* Oven-TwinElectric <br>* Oven-TwinGas <br>* Oven-TwinGas3wide <br>* Oven-TwinMixed <br>* Range <br>* Range-BuiltIn <br>* Range-Dual <br>* Range-Dual10burner <br>* Range-Dual6burner <br>* Range-Dual8burner <br>* Range-Electric <br>* Range-Gas <br>* Range-Gas10burner <br>* Range-Gas6burner <br>* Range-Gas8burner <br>* Range-Induction <br>* Range-Other <br>* Rangetop-Electric <br>* Rangetop-Electric2burner <br>* Rangetop-Electric6burner <br>* Rangetop-Gas <br>* Rangetop-Gas10burner <br>* Rangetop-Gas2burner <br>* Rangetop-Gas4burnercompact <br>* Rangetop-Gas6burner <br>* Rangetop-Gas8burner <br>* Rangetop-GasCustom <br>* Rangetop-Induction <br>* Rangetop-Induction2burner <br>* Rangetop-Induction6burner <br>* Refrigerator <br>* Refrigerator-Bar <br>* Refrigerator-Built-in <br>* Refrigerator-Built-inWithPlumbing <br>* Refrigerator-Drawer <br>* Refrigerator-SidebySide <br>* Refrigerator-Undercounter <br>* Refrigerator-WineStorage <br>* Refrigerator-WithPlumbing <br>* TrashCompactor <br>* VacuumSystem <br>* VacuumSystem-Roughin <br>* VentHood <br>* VentHood10burner <br>* VentHood6burner <br>* VentHood8burner <br>* WarmingDrawer <br>* Washer <br>* Washer-Frontload <br>* Washer-Steamer <br>* Washer-Topload <br>* Washer/DryerCombo <br>* Washer/DryerStack <br>* Water-Filter <br>* Water-InstantHot <br>* Water-Purifier <br>* Water-Softener|
| detailed_characteristics | Detailed characteristics                          | JSON Array |

## Get Traditional Property

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/traditional-property?id=5637233&state=CA&_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/traditional-property?id=5637233&state=CA&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/traditional-property');
$request->setMethod(HTTP_METH_GET);
$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  'state' => 'CA',
  'id' => 5637233,
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/traditional-property?id=5637233&state=CA&_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "id": 5637233,
        "title": "Condominium, Traditional - Los Angeles (City), CA",
        "lon": -118.381,
        "lat": 34.0568,
        "state": "CA",
        "city": "Los Angeles",
        "county": "LOS ANGELES",
        "neighborhood": {
            "id": 275024,
            "name": "Pico-Robertson",
            "country": "United States",
            "city": "Los Angeles",
            "state": "CA",
            "latitude": 34.053022,
            "longitude": -118.383312,
            "singleHomeValue": 1237000,
            "mashMeter": 66.99,
            "description": null,
            "is_village": 0
        },
        "description": "Bright and modern one bedroom condo for lease located in convenient and desirable Beverly Hills adjacent location. Don't miss this very spacious unit with open floor plan and extra large patio for additional outdoor living space. Features include: Wood floors, recessed lighting, clean kitchen with stainless appliances, remodeled bathroom and walk in closet. Property has central heat and air, in unit washer/dryer and 2 parking spaces.  Amazing location near Cedars-Sinai, Century City and all the parks, shops and restaurants of Beverly Hills.",
        "price": 3300,
        "baths": 1,
        "beds": 1,
        "num_of_units": null,
        "sqft": 1028,
        "lot_size": 12787,
        "days_on_market": 3,
        "year_built": 1981,
        "tax": null,
        "tax_history": null,
        "videos": null,
        "virtual_tours": null,
        "parking_spots": 2,
        "parking_type": "Garage",
        "walkscore": null,
        "mls_id": "19508890",
        "image": "http://photos.listhub.net/CLAWCA/19508890/1?lm=20190911T083436",
        "extra_images": [
            "http://photos.listhub.net/CLAWCA/19508890/1?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/2?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/3?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/4?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/5?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/6?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/7?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/8?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/9?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/10?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/11?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/12?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/13?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/14?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/15?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/16?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/17?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/18?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/19?lm=20190911T083436",
            "http://photos.listhub.net/CLAWCA/19508890/20?lm=20190911T083436"
        ],
        "zipcode": "90035",
        "address": "1110 South SHENANDOAH Street #2",
        "type": "apartment",
        "property_type": "Rental",
        "property_sub_type": "Condominium",
        "status": "Active",
        "listhub_key": "3yd-CLAWCA-19508890",
        "broker_name": "Compass",
        "broker_number": null,
        "broker_url": "https://www.compass.com/",
        "source": "Compass",
        "mls_name": "Combined LA Westside Multiple Listing Service, Inc",
        "original_source": "Listhub",
        "architecture_style": "New Traditional",
        "has_pool": null,
        "is_water_front": null,
        "heating_system": "Central Furnace",
        "cooling_system": "Central A/C",
        "view_type": null,
        "schools": null,
        "parcel_number": "4332019046",
        "neighborhood_id": 275024,
        "url": "https://listings.listhub.net/pages/CLAWCA/19508890/?channel=mashv",
        "listing_date": "2019-09-09T00:00:00.000Z",
        "modification_timestamp": "2019-09-11T08:33:26.000Z",
        "created_at": "2019-09-12T04:50:05.000Z",
        "updated_at": "2019-09-12T05:31:02.000Z",
        "agents": [
            {
                "id": 101289,
                "agent_id": 101289,
                "property_id": 5637233,
                "created_at": "2017-06-21T09:37:15.000Z",
                "updated_at": "2019-09-01T09:43:53.000Z",
                "first_name": "Nikki",
                "last_name": "Hochstein",
                "email": "nik@nikkih.com",
                "primary_phone": "(310) 968-1116",
                "phone_number": "(310) 437-7500",
                "role": "Listing",
                "office_id": 1643,
                "website": "https://www.compass.com/",
                "address": "2113-2115 Main St.",
                "city": "SANTA MONICA",
                "state": "CA",
                "county": "Los Angeles",
                "zip_code": "90405",
                "company": "Compass",
                "image": "http://brokerlogos.listhub.net/CLAWCA/acbfbc71874811e5803c125f38ce48fb/20160601185736249.png",
                "real_estate_licence": "01338003",
                "years_of_experience": null,
                "areas_served": null,
                "agent_specialities": null,
                "agent_experience": null,
                "summary": null,
                "title": null,
                "mls_id": null,
                "price_range": null,
                "sold_properties": null,
                "active_properties": null,
                "mailchimp_transfer_date": null,
                "source": "Listhub",
                "listhub_id": "3yd-CLAWCA-X55624"
            }
        ]
    }
}
```

This endpoint retrieves the traditional property's detailed data set stored in Mashvisor database. 

### HTTP Request

`GET https://api.mashvisor.com/v2/traditional-property`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The traditional property Id from the Mashvisor database.
state | String | | The state of the property should be provided to the api or api will throw error 404.
parcel_number | String | | Property parcel or APN
mls_id | String | | Property MLS id
address | String | | Property street address
city | String | | Property city
zip_code | String | | Property zip code

<aside class="success">
Remember — a happy request is an authenticated one!
</aside>

## Get Historical Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/neighborhood/268201/historical/traditional?_t=meowmeowmeow&state=CA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/neighborhood/268201/historical/traditional?_t=meowmeowmeow&state=CA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v2/neighborhood/268201/historical/traditional');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/neighborhood/268201/historical/traditional?_t=meowmeowmeow&state=CA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> The above command returns JSON structured like this:

```json
{
  "status": "success",
  "content": {
    "months": [
      {
        "year": 2019,
        "month": 9,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 8,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 11196
      },
      {
        "year": 2019,
        "month": 7,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 6,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 5,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 4,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 3,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 2,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2019,
        "month": 1,
        "zero_room_value": 2130,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 4570
      },
      {
        "year": 2018,
        "month": 12,
        "zero_room_value": null,
        "one_room_value": 3683.02,
        "two_room_value": 4151.85,
        "three_room_value": 4525.05,
        "four_room_value": 5070
      },
      {
        "year": 2018,
        "month": 11,
        "zero_room_value": null,
        "one_room_value": 3158.4,
        "two_room_value": 4365.73,
        "three_room_value": 5569.59,
        "four_room_value": 8354.67
      },
      {
        "year": 2018,
        "month": 10,
        "zero_room_value": null,
        "one_room_value": 2920,
        "two_room_value": 3650,
        "three_room_value": 4760,
        "four_room_value": 11568
      }
    ],
    "averages": {
      "zero_room_value": 2130,
      "one_room_value": 3575.72,
      "two_room_value": 4127.85,
      "three_room_value": 4631.67,
      "four_room_value": 6062.39
    }
  },
  "message": "Historical Data fetched successfully"
}
```

Get a submarket (neighborhood) short term historical performance for its listings as an array


### HTTP Request

`GET https://api.mashvisor.com/v2/neighborhood/{id}/historical/traditional` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | Neighborhood id to fetch data for

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state should be provided to the api or api will throw error 404.
month | Integer | | A month to fetch after
year | Integer | | A month to fetch after
beds | Integer | | 0 to 4 bedrooms value


# Trends
## Get Top Airbnb Cities

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/trends/cities?_t=meowmeowmeow&state=GA")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/trends/cities?_t=meowmeowmeow&state=GA",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/trends/cities');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  'state' => 'GA',
  'items' => '5'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/trends/cities?_t=meowmeowmeow&state=GA"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "total_results": 5,
        "current_page": 1,
        "state": "GA",
        "cities": [
            {
                "city": "Atlanta",
                "state": "GA",
                "occupancy": 48.51257395,
                "total_listing": 7505,
                "occ_listing": 364086.86748725
            },
            {
                "city": "Decatur",
                "state": "GA",
                "occupancy": 57.34344286,
                "total_listing": 810,
                "occ_listing": 46448.18871417
            },
            {
                "city": "Savannah",
                "state": "GA",
                "occupancy": 67.9532,
                "total_listing": 470,
                "occ_listing": 31938.004
            },
            {
                "city": "COLUMBUS",
                "state": "GA",
                "occupancy": 64.76057273,
                "total_listing": 452,
                "occ_listing": 29271.7788726
            },
            {
                "city": "Brookhaven",
                "state": "GA",
                "occupancy": 48.97408,
                "total_listing": 428,
                "occ_listing": 20960.90624
            }
        ]
    }
}
```

This endpoint retrieves the cities has the highest occupancy rates with their total Airbnb active listings in a specific state. 

### HTTP Request

`GET https://api-build.mashvisor.com/v2/trends/cities` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
items | Integer | 5 | The items to return the content for. Valid values: 10, ... etc.

## Get City Summary

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/summary/listing/IL/Chicago?_t=meowmeowmeow")
  .get()
  .addHeader("Authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/summary/listing/IL/Chicago?_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "Authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/summary/listing/IL/Chicago');
$request->setMethod(HTTP_METH_GET);

$request->setHeaders(array(
  'Authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/summary/listing/IL/Chicago?_t=meowmeowmeow"

  req, _ := http.NewRequest("GET", url, nil)
  
  req.Header.Add("Authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "airbnb_listings": 1146,
        "traditional_listings": 14651,
        "investment_properties": 5049,
        "active_neighborhoods": 227,
        "avg_occupancy": 58.671,
        "avg_nightly_price": 132.7625,
        "avg_property_price": 435929.1957,
        "avg_airbnb_ROI": 1.6541749305165958,
        "avg_traditional_ROI": 0.9134450166166765
    }
}
```

This endpoint retrieves a summary of airbnb properties, traditional properties, investment properties, and active neighborhoods available on Mashvisor.com for a specific .

### HTTP Request

`GET https://api.mashvisor.com/v.1/summary/listing/{state}/{city}` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
city | String* | | City name, ex: Las Vegas.

## Get Location Heatmap

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v2/search/heatmap?state=IL&type=AirbnbCoc&sw_lat=41.888509508814266&sw_lng=-87.7059177836914&ne_lat=41.93992529459902&ne_lng=-87.60995907397461&_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v2/search/heatmap?state=IL&type=AirbnbCoc&sw_lat=41.888509508814266&sw_lng=-87.7059177836914&ne_lat=41.93992529459902&ne_lng=-87.60995907397461&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v2/search/heatmap');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'IL',
  'type' => 'AirbnbCoc',
  'sw_lat' => '41.888509508814266',
  'sw_lng' => '-87.7059177836914',
  'ne_lat' => '41.93992529459902',
  'ne_lng' => '-87.60995907397461',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}'
));

try {
  $response = $request->send();

  echo $response->getBody();
} catch (HttpException $ex) {
  echo $ex;
}
```

```go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v2/search/heatmap?state=IL&type=AirbnbCoc&sw_lat=41.888509508814266&sw_lng=-87.7059177836914&ne_lat=41.93992529459902&ne_lng=-87.60995907397461&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this:

```json
{
    "status": "success",
    "content": {
        "min": -5,
        "max": 6,
        "total_results": 121,
        "results": [
            {
                "id": 3111,
                "boundary": "POLYGON((-87.692773 41.93213,-87.692738 41.931393,-87.692658 41.928508,-87.692591 41.926671,-87.692528 41.924855,-87.689397 41.924883,-87.687642 41.924901,-87.685209 41.924932,-87.683871 41.924952,-87.683726 41.924954,-87.677899 41.925026,-87.674403 41.925069,-87.675094 41.926748,-87.679577 41.928349,-87.682661 41.932231,-87.683285 41.93327,-87.68563 41.933871,-87.687404 41.935777,-87.687986 41.936062,-87.687904 41.93217,-87.692773 41.93213))",
                "airbnb_coc": -4.776479425529639,
                "border_color": "f7b5a7",
                "color": "f06b50"
            },
            {
                "id": 387,
                "boundary": "POLYGON((-87.643667 41.918253,-87.64355 41.914625,-87.642937 41.914634,-87.641744 41.914653,-87.641135 41.914661,-87.638704 41.914676,-87.638762 41.91651,-87.638816 41.918322,-87.641246 41.918286,-87.643667 41.918253))",
                "airbnb_coc": -1.0222971960902214,
                "border_color": "f7b5a7",
                "color": "f06b50"
            },
            {
                "id": 716,
                "boundary": "POLYGON((-87.644886 41.932801,-87.644274 41.931338,-87.643898 41.930703,-87.642924 41.929662,-87.642232 41.928533,-87.641807 41.927813,-87.639228 41.928665,-87.639265 41.929696,-87.640634 41.929242,-87.641467 41.930661,-87.640869 41.930856,-87.641786 41.93236,-87.641343 41.93287,-87.644886 41.932801))",
                "airbnb_coc": -0.5738812344414848,
                "border_color": "f7b5a7",
                "color": "f06b50"
            },
            {
                "id": 3113,
                "boundary": "POLYGON((-87.711675 41.902788,-87.714583 41.90277,-87.711551 41.900148,-87.713455 41.901015,-87.714057 41.90095,-87.713997 41.89913,-87.713873 41.895483,-87.711436 41.895507,-87.706556 41.895553,-87.704134 41.895579,-87.702204 41.895595,-87.701881 41.896418,-87.701951 41.899238,-87.706674 41.899195,-87.706731 41.901006,-87.70679 41.90285,-87.711675 41.902788))",
                "airbnb_coc": 0,
                "border_color": "f7b5a7",
                "color": "f06b50"
            }
        ]
    }
}
```

This endpoint retrieves the investment performance heatmap for a specific geo area.

### HTTP Request

`GET https://api.mashvisor.com/v2/search/heatmap` 

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state to search in. e.g: CA
sw_lat | Double | | To search to a specific geo area, south west point latitude. e.g: 33.76436731683163
sw_lng | Double | | To search to a specific geo area, south west point longitude. e.g: -118.72974734005544
ne_lat | Double | | To search to a specific geo area, north east point latitude. e.g: 34.410846062851626
ne_lng | Double | | To search to a specific geo area, north east point longitude. e.g: -117.99366335568044
type | String | | AirbnbCoc, or listingPrice, TraditionalCoc, OccupancyRate, AirbnbRental, TraditionalRental
 