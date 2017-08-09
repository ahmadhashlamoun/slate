---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - java
  - javascript
  - php
  - go

toc_footers:
  - <a href='https://www.mashvisor.com/signup'>Sign Up for Mashvisor</a>
  - <a href='https://www.mashvisor.com/'>Mashvisor Co.</a>

includes:
  - errors

search: true
---

# Introduction

> Live API Endpoint:

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api.mashvisor.com/v1?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api.mashvisor.com/v1?_t=meowmeowmeow",
  "method": "GET",
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api.mashvisor.com/v1');
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

	url := "https://api.mashvisor.com/v1?_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, payload)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

> Test API Endpoint:

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1?_t=meowmeowmeow",
  "method": "GET",
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1');
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

	url := "https://api-build.mashvisor.com/v1?_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, payload)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
Welcome to the Mashvisor API! You can use our API to access Mashvisor API endpoints needed by developers to build there applications on top of Mashvisor, which can get real estate information on various cities, zip codes, and neighborhoods in our database.

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
  .url("https://api-build.mashvisor.com/v1?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1');
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

	url := "https://api-build.mashvisor.com/v1?_t=meowmeowmeow"

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
  "exp": 1497957785,
  "iss": "Mashvisor.com",
  "user": {
    "role": "Agent",
    "provider": "MASHVISOR",
    "subscription_end_at": null,
    "name": "Ahmad Hashlamoun",
    "created_at": 1447587245000,
    "id": 579,
    "locale": null,
    "auth_token": null,
    "email": "ahmadh@mashvisor.com",
    "subscription_plan": "MASHVISOR_EXPERT_AGENT"
  }
}
```

Mashvisor uses API keys to allow access to the API. You can ask for a new Mashvisor API key via sending an email to *mohd@mashvisor.com*.

Mashvisor expects for the API key to be included in all API requests to the server in a **_t** query parameter that looks like the following:

`_t=meowmeowmeow`

Moreover, Mashvisor allows you to authenticate your account when using the API by including your secret authorization header in the request which is basically a [JWT](https://en.wikipedia.org/wiki/JSON_Web_Token) token. Such authentication to the API is performed via [HTTP Basic Auth](https://en.wikipedia.org/wiki/Basic_access_authentication). 

All API requests requires the JWT authentication must be made over [HTTPS](https://en.wikipedia.org/wiki/HTTP_Secure). Calls made over plain HTTP will fail.

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# CORE RESOURCES
# Agent

## Get Agent's Leads

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1.1/agents/579/leads?page=1&page_count=10&_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1.1/agents/579/leads?page=1&page_count=10&_t=meowmeowmeow",
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
$request->setUrl('http://api-build.mashvisor.com/v1.1/agents/579/leads');

$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'page' => '1',
  'page_count' => '10',
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

	url := "http://api-build.mashvisor.com/v1.1/agents/579/leads?page=1&page_count=10&_t=meowmeowmeow"

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
        "leadsCount": 3,
        "leadsList": [
            {
                "id": 144,
                "name": "Ak45",
                "phone": null,
                "email": "chenguoying@gmail.com",
                "logActivity": null,
                "leadStatus": null,
                "responsiveness": null,
                "motivationToBuy": null,
                "financialSituation": null,
                "created_at": "2017-04-09T08:33:04.000Z",
                "assigned_at": null,
                "info": {
                    "location": {
                        "city_name": null,
                        "region_name": null,
                        "zip_code": null
                    },
                    "cities": null,
                    "zipCodes": null
                }
            },
            {
                "id": 145,
                "name": "Ak44",
                "phone": null,
                "email": "dpipito@ezlandlordforms.com",
                "logActivity": null,
                "leadStatus": null,
                "responsiveness": null,
                "motivationToBuy": null,
                "financialSituation": null,
                "created_at": "2017-04-09T08:33:04.000Z",
                "assigned_at": null,
                "info": {
                    "location": {
                        "city_name": null,
                        "region_name": null,
                        "zip_code": null
                    },
                    "cities": null,
                    "zipCodes": null
                }
            },
            {
                "id": 146,
                "name": "Josh Feingold",
                "phone": "(435) 786-2930",
                "email": "joshfeingold@gmail.com",
                "logActivity": null,
                "leadStatus": null,
                "responsiveness": null,
                "motivationToBuy": null,
                "financialSituation": null,
                "created_at": "2017-04-09T08:33:04.000Z",
                "assigned_at": null,
                "info": {
                    "location": {
                        "city_name": null,
                        "region_name": null,
                        "zip_code": null
                    },
                    "cities": null,
                    "zipCodes": null
                }
            }
        ]
    }
}
```

This endpoint retrieves all the leads for the given agent, with a support of pagination.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/agents/579/leads`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page_count | Integer | 10 | The number of items per page (pagination support).
page | Integer | 1 | The number of page (pagination support).
agent_id | Integer |  | The agent id of which api will fetch leads for.
term | String |  | The name, email, or phone term you want to filter leads by.

<aside class="success">
Remember — a happy request is an authenticated one!
</aside>

## Get City's/Zip Code's Agents

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/agents?city=chicago&state=IL&_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/agents?city=chicago&state=IL&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/agents');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'city' => 'chicago',
  'state' => 'IL',
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1.1/agents?city=chicago&state=IL&_t=meowmeowmeow"

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
        "count": 2,
        "agents": [
            {
                "id": 5483,
                "name": null,
                "first_name": "Mohammed",
                "last_name": "Jebrini",
                "phone_number": "+14157428118",
                "email": "mohd+apriltest2@mashvisor.com",
                "address": null,
                "city": null,
                "state": null,
                "image": "https://1206571fb332126daea3-f9af1674472c570d09a77c409717e529.ssl.cf5.rackcdn.com/UserImages/5483/5483_agency.png",
                "agent_image": "https://1206571fb332126daea3-f9af1674472c570d09a77c409717e529.ssl.cf5.rackcdn.com/UserImages/5483/5483_profile.png",
                "company": "Mashvisor"
            },
            {
                "id": 38,
                "name": "Mohd Jebrini",
                "first_name": "Mohammad",
                "last_name": "Jebrini",
                "phone_number": " ",
                "email": "mohd@mashvisor.com",
                "address": null,
                "city": "San Diego",
                "state": "CA",
                "image": "https://1206571fb332126daea3-f9af1674472c570d09a77c409717e529.ssl.cf5.rackcdn.com/UserImages/38/38_agency.png",
                "agent_image": "https://1206571fb332126daea3-f9af1674472c570d09a77c409717e529.ssl.cf5.rackcdn.com/UserImages/38/38_profile.png",
                "company": "Jebrini Agency"
            }
        ]
    }
}
```

This endpoint retrieves the agents of given city or zip code.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/agents`


### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
zip_code | Integer | | Area zipCode (of which agents cover).
city | String | | Area city.
state | String | | Area state.

## Get City's/Zip Code's Agent

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/agents/search?userId=5402&state=IL&city=Chicago&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/agents/search?userId=5402&state=IL&city=Chicago&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/agents/search');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'userId' => '5402',
  'state' => 'IL',
  'city' => 'Chicago',
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

	url := "https://api-build.mashvisor.com/v1.1/agents/search?userId=5402&state=IL&city=Chicago&_t=meowmeowmeow"

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
        "agent": {
            "id": 38,
            "name": "Mohd Jebrini",
            "first_name": "Mohammad",
            "last_name": "Jebrini",
            "phone_number": " ",
            "email": "mohd@mashvisor.com",
            "address": null,
            "city": "San Diego",
            "state": "CA",
            "image": "https://1206571fb332126daea3-f9af1674472c570d09a77c409717e529.ssl.cf5.rackcdn.com/UserImages/38/38_agency.png",
            "agent_image": "https://1206571fb332126daea3-f9af1674472c570d09a77c409717e529.ssl.cf5.rackcdn.com/UserImages/38/38_profile.png",
            "company": "Jebrini Agency"
        }
    }
}
```

This endpoint retrieves a random agent for given non-agent user.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/agents/search`


### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
zipCode | Integer | | Area zipCode (of which agents cover).
city | String | | Area city.
state | String | | Area state.
userId | Integer | | Requester User Id.

## Get City's/Zip Code's MLS Agents

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/agents/profile/list?state=CA&city=San%20Diego&items=2&page=1&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/agents/profile/list?state=CA&city=San%20Diego&items=2&page=1&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/agents/profile/list');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'city' => 'San Diego',
  'items' => '2',
  'page' => '1',
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

	url := "https://api-build.mashvisor.com/v1.1/agents/profile/list?state=CA&city=San%20Diego&items=2&page=1&_t=meowmeowmeow"

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
        "count": 1590,
        "agents": [
            {
                "id": 45471,
                "first_name": "A.J.",
                "last_name": "Michaels",
                "email": "realtypro@hotmail.com",
                "phone_number": "(858) 273-7373",
                "office_id": 9405,
                "website": null,
                "address": null,
                "city": null,
                "state": null,
                "company": "The Michaels Realty Group",
                "image": null,
                "real_estate_licence": null,
                "years_of_experience": null,
                "areas_served": null,
                "agent_specialities": null,
                "agent_experience": null,
                "summary": null,
                "title": null,
                "mls_id": null,
                "source": null,
                "created_at": "2017-01-08T08:57:36.000Z",
                "updated_at": "2017-01-08T08:57:36.000Z",
                "listhub_id": "3yd-SANDICOR-618668"
            },
            {
                "id": 6363,
                "first_name": "Aaron",
                "last_name": "Castagna",
                "email": "aaron@aaroncastagna.com",
                "phone_number": "(760) 607-5900",
                "office_id": 1528,
                "website": "http://www.HSRealtyWest.com",
                "address": "2776 Gateway Road Ste. 100",
                "city": "Carlsbad",
                "state": "CA",
                "company": "HomeSmart Realty West",
                "image": "http://brokerlogos.listhub.net/SANDICOR/f3794581783011e1ae67123139008121/20140904011053191.png",
                "real_estate_licence": null,
                "years_of_experience": null,
                "areas_served": null,
                "agent_specialities": null,
                "agent_experience": null,
                "summary": null,
                "title": null,
                "mls_id": null,
                "source": "Listhub",
                "created_at": "2016-12-13T11:54:23.000Z",
                "updated_at": "2017-07-25T02:48:18.000Z",
                "listhub_id": "3yd-SANDICOR-655460"
            }
        ]
    }
}
```

This endpoint retrieves a random agent for given non-agent user.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/agents/search`


### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | Area city.
state | String | | Area state.
zipCode | String | | Area zip code.
page | Integer | 1| For pagination.
items | Integer | 10| For pagination.

## Get Agent Profile

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/agents/profile/detail?name=Jeffrey-Wilkin&id=3&_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/agents/profile/detail?name=Jeffrey-Wilkin&id=3&_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1.1/agents/profile/detail');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'name' => 'Jeffrey-Wilkin',
  'id' => '3',
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setContentType('application/x-www-form-urlencoded');

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

	url := "https://api-build.mashvisor.com/v1.1/agents/profile/detail?name=Jeffrey-Wilkin&id=3&_t=meowmeowmeow"

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
    "status": 200,
    "content": {
        "agentData": {
            "id": 3,
            "first_name": "Jeffrey",
            "last_name": "Wilkin",
            "email": "jeff@coloradomountainland.net",
            "phone_number": "(719) 873-1012",
            "office_id": 1,
            "website": "http://www.landpropertiessouthfork.com",
            "address": null,
            "city": "Breckenridge",
            "state": "CO",
            "company": "Land Properties, LLC",
            "image": null,
            "real_estate_licence": null,
            "years_of_experience": null,
            "areas_served": null,
            "agent_specialities": null,
            "agent_experience": null,
            "summary": null,
            "title": null,
            "mls_id": null,
            "source": null,
            "created_at": "2016-12-12T16:24:21.000Z",
            "updated_at": "2016-12-12T16:24:21.000Z",
            "listhub_id": "3yd-CRENCO-5937",
            "_agent_profile_id": null,
            "_first_name": null,
            "_last_name": null,
            "_title": null,
            "_company": null,
            "_real_estate_licence": null,
            "_years_of_experience": null,
            "_areas_served": null,
            "_agent_specialities": null,
            "_agent_experience": null,
            "_summary": null,
            "agent_id": 3
        },
        "agentDataConnection": "1",
        "approvedClaims": 0,
        "canEdit": true,  //if user token is sent
        "claimStatus": "APPROVED" //if user token is sent
    },
    "message": ""
}
```

This endpoint retrieves an agent profile of given name and id

### HTTP Request

`GET http://api.mashvisor.com/v1.1/agents/profile/details`

### Request Headers

Parameter | Value
--------- | -------
Authorization | **optional** User Authentication JWT Token, ex:Bearer {JWT_TOKEN} to return user permission over the requested agent profile

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
name | String | | Area city.
id | Integer | | Area state.

## Update Agent Profile

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("text/plain");
RequestBody body = RequestBody.create(mediaType, "{\n    \"id\":579,\n    \"first_name\":Ahmad,\n    \"last_name\":Hash\n}");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/agents/profile/edit?_t=meowmeowmeow")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/json")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/agents/profile/edit?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/json",
  },
  "data": "{\n    \"id\":579,\n    \"first_name\":Ahmad,\n    \"last_name\":Hash\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/agents/profile/edit');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/json',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setBody('{
    "id":579,
    "first_name":Ahmad,
    "last_name":Hash
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

	url := "https://api-build.mashvisor.com/v1.1/agents/profile/edit?_t=meowmeowmeow"

	payload := strings.NewReader("{\n    \"id\":579,\n    \"first_name\":Ahmad,\n    \"last_name\":Hash\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/json")

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
    "content": "updated successfully"
}
```

This endpoint updates the agent profile with given values

### HTTP Request

`POST http://api.mashvisor.com/v1.1/agents/profile/edit`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Request Body (JSON-Format) Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Integer | | (must) - agent id
agentDataConnection | Integer | | (must) - the db connection agent profile exists - this value returns in the above api (profile fetch)
first_name | String | | (optional)
last_name | String | | (optional)
title | String | | (optional)
company | String | | (optional)
real_estate_licence | String | | (optional)
years_of_experience | Integer | | (optional)
areas_served | String | | (optional) - list comma seperated
agent_specialities | String | | (optional) - list comma seperated
agent_experience | String | | (optional) - list comma seperated
summary | String | | (optional)

## Add Agent Profile Claim

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n    \"agent_profile_id\":430,\n    \"connection\":3\n}");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/agents/profile/claim?_t=meowmeowmeow")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/json")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/agents/profile/claim?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/json"
  },
  "processData": false,
  "data": "{\n    \"agent_profile_id\":430,\n    \"connection\":3\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/agents/profile/claim');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/json',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setBody('{
	"agent_profile_id":430,
	"connection":3
	
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

	url := "https://api-build.mashvisor.com/v1.1/agents/profile/claim?_t=meowmeowmeow"

	payload := strings.NewReader("{\n    \"agent_profile_id\":430,\n    \"connection\":3\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/json")

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
    "content": "permission added succesfully"
}
```

This endpoint adds user permission for agent profile edit

### HTTP Request

`POST http://api.mashvisor.com/v1.1/agents/profile/claim`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Request Body (JSON-Format) Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
agent_profile_id | Integer | | (must) - agent id
connection | Integer | | (must) - the db connection agent profile exists - this value returns in the above api (profile fetch)

## Check Agent Profile Claim

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1.1/agents/profile/claim/check?agent_profile_id=4&connection=1&_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1.1/agents/profile/claim/check?agent_profile_id=4&connection=1&_t=meowmeowmeow",
  "method": "GET",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}"
  },
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://api-build.mashvisor.com/v1.1/agents/profile/claim/check');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'agent_profile_id' => '4',
  'connection' => '1',
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "http://api-build.mashvisor.com/v1.1/agents/profile/claim/check?agent_profile_id=4&connection=1&_t=meowmeowmeow"

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
        "claim": "PENDING" // or "APPROVED" or "NO-CLAIM"
    }
}
```

This endpoint checks the permission of user over given agent profile.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/agents/profile/claim/check`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
agent_profile_id | Integer | | Id of agent profile to check
connection | Integer | | Server connection

# Checkout

## Purchase a Plan

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "plan=Mashvisor_Basic&token=tok_1AUYbCGYREWu4WN3pRhh7SSe");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/checkout/confirm?_t=meowmeowmeow")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/checkout/confirm?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "plan": "Mashvisor_Basic",
    "token": "tok_1AUYbCGYREWu4WN3pRhh7SSe"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/checkout/confirm');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'plan' => 'Mashvisor_Basic',
  'token' => 'tok_1AUYbCGYREWu4WN3pRhh7SSe'
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

	url := "https://api-build.mashvisor.com/v1/checkout/confirm?_t=meowmeowmeow"

	payload := strings.NewReader("plan=Mashvisor_Basic&token=tok_1AUYbCGYREWu4WN3pRhh7SSe")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
        "message": "Your payment have been done successfully"
    },
    "message": "result"
}
```

This endpoint confirms a payment by Stripe to subscribe in one of Mashvisor's paid plans.

### HTTP Request

`POST http://api.mashvisor.com/v1/checkout/confirm`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
token | String | | Token generated by stipe in each payment
plan | String | | Stripe's subscription plan, ex: Mashvisor_Basic
coupon | String | | The promo code you want to discount of, ex.: Labor40

### Valid Mashvisor Plans

PLAN NAME |
--------- |
Mashvisor_Basic |
Mashvisor_Basic_Quarterly |
Mashvisor_Professional |
Mashvisor_Professional_Quarterly |
Mashvisor_Expert |
Mashvisor_Expert_Quarterly |
Mashvisor_Pro_Agent_Quarterly |
Mashvisor_Pro_Agent_Annual |
Mashvisor_Expert_Agent_Quarterly |
Mashvisor_Expert_Agent_Annual |
Mashvisor_Top_Agent_Quarterly |
Mashvisor_Top_Agent_Annual |

## Get Coupon

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1/checkout/coupon/Labor40?plan=Mashvisor_Basic&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1/checkout/coupon/Labor40?plan=Mashvisor_Basic&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://api-build.mashvisor.com/v1/checkout/coupon/Labor40');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'plan' => 'Mashvisor_Basic',
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

	url := "http://api-build.mashvisor.com/v1/checkout/coupon/Labor40?plan=Mashvisor_Basic&_t=meowmeowmeow"

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
    "id": "Labor40",
    "amount_off": null,
    "percent_off": 40,
    "valid": true,
    "currency": null,
    "trial_days": null,
    "charge_immediately": true
  },
  "message": "Coupon object fetched successfully"
}
```
<aside class="notice">The coupon name you want to fetch is a path paramter in the API request.</aside>

This endpoint retrieves the coupon info from Stripe.

### HTTP Request

`GET http://api.mashvisor.com/v1/coupon/{coupon}`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
coupon | String | | The promo code you want to discount of, ex.: Labor40

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
plan | String | | Stripe's subscription plan, ex: Mashvisor_Basic

## Unsubscribe

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "reason=Other");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/checkout/unsubscribe?_t=meowmeowmeow")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/checkout/unsubscribe?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "reason": "Other"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/checkout/unsubscribe');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'reason' => 'Other'
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

	url := "https://api-build.mashvisor.com/v1/checkout/unsubscribe?_t=meowmeowmeow"

	payload := strings.NewReader("reason=Other")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
    "message": "You've been unsubscriped from Mashvisor."
  },
  "message": "result"
}
```

This endpoint unsubscribes a logged in user from Stripe and Mashvisor.

### HTTP Request

`POST http://api.mashvisor.com/v1/checkout/unsubscribe`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
reason | String | | The reason specified by the user why he's cancelling.

### Valid Reasons

Reason |
--------- |
This is temporary and I'll be back |
I don't understand how to use Mashvisor |
I didn't get relevant real estate data or I couldn't find my area |
I did my research and no longer have a need for Mashvisor |
It is too expensive |
Other |

## Upgrade

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "plan=Mashvisor_Top_Agent_Annual");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/checkout/upgrade?_t=meowmeowmeow")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/checkout/upgrade?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "plan": "Mashvisor_Top_Agent_Annual"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/checkout/upgrade');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'plan' => 'Mashvisor_Top_Agent_Annual'
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

	url := "https://api-build.mashvisor.com/v1/checkout/upgrade?_t=meowmeowmeow"

	payload := strings.NewReader("plan=Mashvisor_Top_Agent_Annual")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
        "message": "Congratulations, you have been upgraded to plan Mashvisor_Expert successfully."
    },
    "message": "result"
}
```

This endpoint upgrades a customer from a subscription plan to another plan.

### HTTP Request

`POST http://api.mashvisor.com/v1/checkout/upgrade`

### Request Headers

Parameter | Value
--------- | -------
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN}

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
plan | String | | Stripe's subscription plan, ex: Mashvisor_Basic
coupon | String | | The promo code you want to discount of, ex.: Labor40

### Valid Mashvisor Plans

PLAN NAME |
--------- |
Mashvisor_Basic |
Mashvisor_Basic_Quarterly |
Mashvisor_Professional |
Mashvisor_Professional_Quarterly |
Mashvisor_Expert |
Mashvisor_Expert_Quarterly |
Mashvisor_Pro_Agent_Quarterly |
Mashvisor_Pro_Agent_Annual |
Mashvisor_Expert_Agent_Quarterly |
Mashvisor_Expert_Agent_Annual |
Mashvisor_Top_Agent_Quarterly |
Mashvisor_Top_Agent_Annual |

# City

## Get CityGuide

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/city/overview/CA/San%20Francisco?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/city/overview/CA/San%20Francisco?_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/city/overview/CA/San%20Francisco');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/city/overview/CA/San%20Francisco?_t=meowmeowmeow"

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
        "city_guide": {
            "id": 1,
            "city": "San Francisco",
            "state": "CA",
            "country": "United States",
            "title": "San Francisco Investment Analysis",
            "subtitle": "Investment Properties in San Francisco, CA",
            "description": "<p>San Francisco is one of the most in-demand real estate markets in the nation and is considered a leading Real Estate Superstar City.&nbsp;Over the past several years, San Francisco properties have maintained their value better than the rest of the nation.&nbsp;&nbsp;</p>\r\n\r\n<p>Traditionally, San Francisco has held one of the highest&nbsp;<strong>buy-vs-rent</strong>&nbsp;ratio making it a rental market. However, purchasing&nbsp;an investment property in San Francisco will require a substantial down payment in order to be immediately cash flow positive.</p>\r\n\r\n<p>Buying a buy-and-hold in this city is one of the best real estate investments because there are so many things to do in San Francisco and in each of its neighborhoods -&nbsp;making it an optimal city for Airbnb and traditional real estate investing. The market analysis shows that an Airbnb investment property&nbsp;in San Francisco can sometimes provide higher returns than traditional real estate investing, which is greatly due to San Francisco tourism.&nbsp;</p>\r\n",
            "header_image": "https://www.mashvisor.com/application/files/thumbnails/file_manager_detail_2x/7914/5967/3185/san-francisco-city-investmetn-guide-mashvisor.jpg",
            "main_image": "https://www.mashvisor.com/application/files/thumbnails/file_blog_thumb_2x/8814/5967/3178/san-francisco-city-investment-guild-overview.jpg",
            "google_image": "https://bc9f40b414b80f1ce90f-212b46b1c531b50ebb00763170d70160.ssl.cf5.rackcdn.com/CityGuide/mashvisor-city-investment-fb-share-photo.jpg",
            "twitter_image": "https://bc9f40b414b80f1ce90f-212b46b1c531b50ebb00763170d70160.ssl.cf5.rackcdn.com/CityGuide/mashvisr-city-investment-guide-tw-share-image.jpg",
            "facebook_image": "https://bc9f40b414b80f1ce90f-212b46b1c531b50ebb00763170d70160.ssl.cf5.rackcdn.com/CityGuide/mashvisor-city-investment-fb-share-photo.jpg",
            "blog_rss": "https://www.mashvisor.com/blog/feed/",
            "latest_news_rss": "https://news.google.com/news?cf=all&hl=en&pz=1&ned=us&q=real+estate+investing+san+francisco&output=rss",
            "guides_and_tips_rss": "https://www.mashvisor.com/blog/feed/",
            "meta_title": "Investment Properties in San Francisco | Mashvisor",
            "meta_description": "San Francisco, CA Investment Property guide on Mashvisor.com. Find Investment Properties in San Francisco. Get an Investment Property Analysis for both Traditional and Airbnb investments.",
            "meta_keywords": "Real Estate Investment Properties, Investment Property, Real Estate Investments, Investment Property Analysis, Find Investment Property, Investment Property San Francisco, Real Estate Investment Properties San Francisco, Airbnb San Francisco, Real Estate Investing, Market Analysis, Best Real Estate Investments, Buy and Hold",
            "lat": "37.77399826049805",
            "lng": "-122.43099975585938"
        },
        "general_rental_resources": [],
        "property_management_companies": []
    },
    "message": "City Overview fetched successfully"
}
```

This endpoint retrieves CityGuide info for the required city.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/city/overview/{state}/{city}`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.

## Get Top Properties

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/city/properties/IL/Chicago?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/city/properties/IL/Chicago?_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/city/properties/IL/Chicago');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/city/properties/IL/Chicago?_t=meowmeowmeow"

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
        "properties": [
            {
                "id": 580002,
                "neighborhood": "Norwood Park West",
                "neighborhood_id": 403276,
                "address": "6480 North Northwest Highway #3",
                "city": "Chicago",
                "state": "IL",
                "image_url": "http://photos.listhub.net/MREDIL/09660935/1?lm=20170615T222750",
                "list_price": 144900,
                "list_price_formatted": "$144,900",
                "baths": 1,
                "beds": 2,
                "sqft": 0,
                "airbnb_cap": 42.07701863354037,
                "airbnb_ROI": 34.81700138026225,
                "traditional_ROI": 6.4640324361628725,
                "traditional_cap": 11.914285714285716
            },
            {
                "id": 285154,
                "neighborhood": "East Garfield Park",
                "neighborhood_id": 269577,
                "address": "3715 West Ferdinand Street",
                "city": "Chicago",
                "state": "IL",
                "image_url": "http://photos.listhub.net/MREDIL/09387384/1?lm=20170807T202311",
                "list_price": 78800,
                "list_price_formatted": "$78,800",
                "baths": 2,
                "beds": 3,
                "sqft": 1344,
                "airbnb_cap": 32.003891708972084,
                "airbnb_ROI": 23.775957698819543,
                "traditional_ROI": 14.928187817258884,
                "traditional_cap": 22.591370558375633
            },
            {
                "id": 553497,
                "neighborhood": "Park Manor",
                "neighborhood_id": 403356,
                "address": "6844 South Lafayette Avenue",
                "city": "Chicago",
                "state": "IL",
                "image_url": "http://photos.listhub.net/MREDIL/09636488/1?lm=20170529T111725",
                "list_price": 79900,
                "list_price_formatted": "$79,900",
                "baths": 2,
                "beds": 4,
                "sqft": 1500,
                "airbnb_cap": 30.08623279098874,
                "airbnb_ROI": 22.020809762202752,
                "traditional_ROI": 11.03033917396746,
                "traditional_cap": 18.39424280350438
            },
            {
                "id": 487212,
                "neighborhood": "Fifth City",
                "neighborhood_id": 403319,
                "address": "2950 West Adams Street",
                "city": "Chicago",
                "state": "IL",
                "image_url": "http://photos.listhub.net/MREDIL/09572551/1?lm=20170403T013847",
                "list_price": 139900,
                "list_price_formatted": "$139,900",
                "baths": 2,
                "beds": 4,
                "sqft": 990,
                "airbnb_cap": 24.62728139147248,
                "airbnb_ROI": 18.347257803194992,
                "traditional_ROI": 4.333929521086491,
                "traditional_cap": 9.7194853466762
            }
        ]
    },
    "message": "City Properties fetched successfully"
}
```

This endpoint retrieves the top city investment properties based on the csh on cash.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/city/properties/{state}/{city}`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.

## Get Invetment Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/city/investment/IL/Chicago?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/city/investment/IL/Chicago?_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/city/investment/IL/Chicago');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/city/investment/IL/Chicago?_t=meowmeowmeow"

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
        "median_price": "424394.6394",
        "sqft": "1284.4087",
        "investment_properties": 3411,
        "airbnb_properties": 2287,
        "traditional_properties": 38233,
        "occupancy": "44.9860",
        "traditional_coc": 1.976312990460984,
        "airbnb_coc": 1.322760716395628,
        "traditional_rental": 1858.7759822019848,
        "airbnb_rental": 1465.9541232350475,
        "airbnb_rental_rates": {
            "oneBedRoomHomeValue": "1175.2918563281525215",
            "twoBedRoomsHomeValue": "1646.4655581945417384",
            "threeBedRoomsHomeValue": "2072.0269370523959004",
            "fourBedRoomsHomeValue": "3302.8535329079079079"
        },
        "traditional_rental_rates": {
            "oneBedRoomHomeValue": 1003.149838067789,
            "twoBedRoomsHomeValue": 1321.028062728008,
            "threeBedRoomsHomeValue": 1721.0956060602805,
            "fourBedRoomsHomeValue": 1925.275995599016
        }
    },
    "message": "City Overview fetched successfully"
}
```

This endpoint retrieves the city investment performance.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/city/investment/{state}/{city}`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.

## Get Attractions

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/city/attractions/IL/Chicago?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/city/attractions/IL/Chicago?_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/city/attractions/IL/Chicago');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1/city/attractions/IL/Chicago?_t=meowmeowmeow"

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
        "count": 34,
        "data": [
            {
                "id": "4c06e1148a81c9b6aa6c2690",
                "name": "Millennium Park Welcome Center",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/21190380_CV_4gnBqYDF9QXr695ATLPU-mEpYLNB7ZonPgKkEYkc.jpg"
                },
                "distance": 199,
                "latitude": 41.88357389690436,
                "longitude": -87.62287281140273,
                "address": "201 E Randolph St",
                "type": "Monument / Landmark",
                "rating": 8.2
            },
            {
                "id": "4b01c67af964a520544522e3",
                "name": "Willie Dixon's Blues Heaven Foundation, Historic Site of Chess Records",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/KeG_shX_RvgljBL3p2vaeP7WeIGK58ZhPcL9usiFgdg.jpg"
                },
                "distance": 3141,
                "latitude": 41.853589,
                "longitude": -87.623936,
                "address": "2120 S Michigan Ave (bt E 21st St & Cermak Av)",
                "type": "Historic Site",
                "rating": 9
            },
            {
                "id": "4b2fcec7f964a52050f024e3",
                "name": "Historic Site of State Street Stroll",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/140037658_cdr3wRdg_0amYivWG-q1w64-qvjL3Sh7jrWnKaztf7Q.jpg"
                },
                "distance": 5657,
                "latitude": 41.8311046,
                "longitude": -87.6184003,
                "address": "E. 35th St. (at Calumet Ave.)",
                "type": "Historic Site",
                "rating": 8
            },
            {
                "id": "4e744808aeb780be09b1b0ee",
                "name": "Historic Logan Square",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/2119897_nPL6ucTQ4Qd9M2_QDoFjxHNrAO-OvsQTbdQYDQ5NvgU.jpg"
                },
                "distance": 8516,
                "latitude": 41.92791796622345,
                "longitude": -87.70521720486522,
                "address": "Chicago, IL 60647",
                "type": "Historic Site",
                "rating": 8.7
            }
        ]
    },
    "message": "Attractions venues fetched successfully"
}
```

This endpoint retrieves the city attractions.

### HTTP Request

`GET http://api.mashvisor.com/v1/city/attractions/{state}/{city}`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.

## Get Activites

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/city/activities/IL/Chicago?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/city/activities/IL/Chicago?_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/city/activities/IL/Chicago');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1/city/activities/IL/Chicago?_t=meowmeowmeow"

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
        "count": 34,
        "data": [
            {
                "id": "49c43594f964a520ac561fe3",
                "name": "Star of Siam",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/18428453_FBjyN16Dqh6pcTVnS6mSAhZI6BQ4WeNjEC2zz3lgh-I.jpg"
                },
                "distance": 1068,
                "latitude": 41.89088946232646,
                "longitude": -87.62734107919891,
                "address": "11 E Illinois Street #1 (btwn N State St & N Wabash Ave)",
                "type": "Thai Restaurant",
                "rating": 8.5
            },
            {
                "id": "4adf4ff4f964a520547921e3",
                "name": "REI",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/221761_Mq5ynTXD3BA7QLKEt0LznPRhj286i4tcSGRc_Rs1NNY.jpg"
                },
                "distance": 3618,
                "latitude": 41.908325,
                "longitude": -87.6484458,
                "address": "1466 N Halsted St (at Blackhawk St)",
                "type": "Sporting Goods Shop",
                "rating": 8.4
            }
        ]
    },
    "message": "Activities venues fetched successfully"
}
```

This endpoint retrieves the city activities.

### HTTP Request

`GET http://api.mashvisor.com/v1/city/activities/{state}/{city}`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.

## List CityGuides

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/city/guides?tab=coc&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/city/guides?tab=coc&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/city/guides');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'tab' => 'coc',
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

	url := "https://api-build.mashvisor.com/v1.1/city/guides?tab=coc&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
> The above command returns JSON structured like this with different responses based on the params:

```json
{
  "status": "success",
  "content": {
    "city_guides": [
      {
        "id": 1,
        "city": "San Francisco",
        "state": "CA",
        "country": "United States",
        "title": "San Francisco Investment Analysis",
        "subtitle": "Investment Properties in San Francisco, CA",
        "header_image": "https://www.mashvisor.com/application/files/thumbnails/file_manager_detail_2x/7914/5967/3185/san-francisco-city-investmetn-guide-mashvisor.jpg",
        "main_image": "https://www.mashvisor.com/application/files/thumbnails/file_blog_thumb_2x/8814/5967/3178/san-francisco-city-investment-guild-overview.jpg",
        "lat": 37.77399826049805,
        "lng": -122.43099975585938,
        "median_price": 1270556.8371,
        "traditional_coc": 1.7352041006088257,
        "airbnb_coc": 2.226914167404175
      },
      {
        "id": 2,
        "city": "Chicago",
        "state": "IL",
        "country": "United States",
        "title": "Chicago Investment Analysis",
        "subtitle": "Investment Properties in Chicago, IL ",
        "header_image": "https://www.mashvisor.com/application/files/thumbnails/file_manager_detail_2x/3614/5967/3185/chicago-city-investment-guide-mashvisor.jpg",
        "main_image": "https://www.mashvisor.com/application/files/thumbnails/file_blog_thumb_2x/3414/5967/3184/chicago-city-investment-guide-overview.jpg",
        "lat": 41.88180160522461,
        "lng": -87.62319946289062,
        "median_price": 354911.7168,
        "traditional_coc": 2.556636095046997,
        "airbnb_coc": 4.145689010620117
      },
      {
        "id": 3,
        "city": "Austin",
        "state": "TX",
        "country": "United States",
        "title": "Austin Investment Analysis",
        "subtitle": "Investment Properties in Austin, TX ",
        "header_image": "https://mashvisor.com/application/files/thumbnails/social_media/1014/5967/3188/austin-city-city-investment-guid-mashvisor.jpg",
        "main_image": "https://mashvisor.com/application/files/thumbnails/file_blog_thumb/6314/5967/3176/austin-city-investment-overview.jpg",
        "lat": 30.25,
        "lng": -97.75,
        "median_price": 464763.9463,
        "traditional_coc": 1.6033401489257812,
        "airbnb_coc": 6.3136210441589355
      }
    ]
  },
  "message": "City overview fetched successfully"
}
```

```json
{
  "status": "success",
  "content": {
    "city_guides": [
      {
        "id": 1,
        "city": "San Francisco",
        "state": "CA",
        "country": "United States",
        "title": "San Francisco Investment Analysis",
        "subtitle": "Investment Properties in San Francisco, CA",
        "header_image": "https://www.mashvisor.com/application/files/thumbnails/file_manager_detail_2x/7914/5967/3185/san-francisco-city-investmetn-guide-mashvisor.jpg",
        "main_image": "https://www.mashvisor.com/application/files/thumbnails/file_blog_thumb_2x/8814/5967/3178/san-francisco-city-investment-guild-overview.jpg",
        "lat": 37.77399826049805,
        "lng": -122.43099975585938,
        "airbnb_properties": 1644,
        "occupancy": 73.1136
      }
    ]
  },
  "message": "City overview fetched successfully"
}
```

```json
{
  "status": "success",
  "content": {
    "city_guides": [
      "San Francisco, CA",
      "Chicago, IL",
      "Austin, TX"
    ]
  },
  "message": "City overview fetched successfully"
}
```

This endpoint retrieves the city guides from the db under the filters applied by the parameters.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/city/guides`

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.
items | Integer | 3 | The number of items to fetch.
tab | String | coc | To fetch the guides with cash on cash or occupancy values for each city. Valid values: coc, occupancy
detailed | Boolean | true | If it's set to true, it fetch the guides with their data and coc or occupancy values, if it's set to false, it fetches just the cities have guides with their states in an array
briefly | String | off | If it's set to on, it fetched the the tab info, if it's set to off, it fetches the basic city guides info.

## Get Lender

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/lender?state=FL&city=Miami&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/lender?state=FL&city=Miami&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/lender');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'FL',
  'city' => 'Miami',
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

	url := "https://api-build.mashvisor.com/v1.1/lender?state=FL&city=Miami&_t=meowmeowmeow"

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
  "content": [
    {
      "title": "lender a",
      "logo": "http://2.bp.blogspot.com/-5Z4VfB7sDVs/T-u_Ixwx4uI/AAAAAAAAEqc/GDHoi_OjAXM/s1600/Tiger+3D+Wallpapers+3.jpg",
      "call_to_action": "mashvisor.com"
    },
    {
      "title": "lender b",
      "logo": "http://www.w3schools.com/css/img_fjords.jpg",
      "call_to_action": "google.com"
    }
  ]
}
```

This endpoint retrieves the list of lenders of given city.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/city/lender`

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String | | The city to return the content for. Valid values: Chicago, ... etc.
state | String | | The state to return the content for. Valid values: IL, ... etc.

# Contact

## Send Message

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "name=Ahmad%20Hashlamoun&message=I%20want%20to%20talk%20to%20join%20your%20team&email=ahmadh%40mashvisor.com");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/contact/send")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/contact/send",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "name": "Ahmad Hashlamoun",
    "message": "I want to talk to join your team",
    "email": "ahmadh@mashvisor.com"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/contact/send');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'name' => 'Ahmad Hashlamoun',
  'message' => 'I want to talk to join your team',
  'email' => 'ahmadh@mashvisor.com'
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

	url := "https://api-build.mashvisor.com/v1/contact/send"

	payload := strings.NewReader("name=Ahmad%20Hashlamoun&message=I%20want%20to%20talk%20to%20join%20your%20team&email=ahmadh%40mashvisor.com")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
    "status":"success",
    "content":{
        "contact":{
            "id":5,
            "name":"guest",
            "email":"guest@mail.com",
            "message":"Hello Mashvisor",
            "createdAt":"Thu Jan 29 16:29:00 IST 2015",
            "updatedAt":"Thu Jan 29 16:29:00 IST 2015"
        }
    },
    "message":"Contact succeeded"
}
```

This endpoint sends a guest message to Mashvisor team by email.

### HTTP Request

`POST http://api.mashvisor.com/v1/contact/send`

### HTTP Headers

Header | Value | Default | 
--------- | ------- | ------- |
Content-Type | application/x-www-form-urlencoded | | 

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
name | String | | Guest Name
email | String | | Guest Email address
message | String | | Guest Message

# Fousquare

## List International Airports 

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1/foursquare/airports?lat=40.7&lng=-74")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1/foursquare/airports?lat=40.7&lng=-74",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://api-build.mashvisor.com/v1/foursquare/airports');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'lat' => '40.7',
  'lng' => '-74'
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

	url := "http://api-build.mashvisor.com/v1/foursquare/airports?lat=40.7&lng=-74"

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
        "count": 1,
        "data": [
            {
                "id": "4459d2f1f964a520d7321fe3",
                "name": "Newark Liberty International Airport (EWR) (Newark Liberty International Airport)",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/59646_VOZtwbs_2W4E8etjs4EpqMjBQycVEedTnxzyhtSHRSk.jpg"
                },
                "distance": 14977,
                "latitude": 40.69461219395808,
                "longitude": -74.17732561998079,
                "address": "10 Toler Pl (at Express Rd)",
                "type": "Airport",
                "rating": 5.7
            }
        ]
    },
    "message": "International airports fetched successfully"
}
```

This endpoint retrieves the Foursquare API service for getting the international airports venues around a specific latitude and longitude. 

### HTTP Request

`GET http://api.mashvisor.com/v1/forusquare/airports` 

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
lat | Double | | The latitude to return the content for. Valid values: 40.7, ... etc.
lng | Double | | The longitude to return the content for. Valid values: -74, ... etc.

## List Attractions

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1/foursquare/attractions?lat=40.7&lng=-74")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1/foursquare/attractions?lat=40.7&lng=-74",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://api-build.mashvisor.com/v1/foursquare/attractions');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'lat' => '40.7',
  'lng' => '-74'
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

	url := "http://api-build.mashvisor.com/v1/foursquare/attractions?lat=40.7&lng=-74"

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
        "count": 43,
        "data": [
            {
                "id": "4a43bcb7f964a520bba61fe3",
                "name": "Brooklyn Bridge",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/14735285_d-88q3ImavgP0AnG7xBh-bI7EpbdBjb1pROJEwAB22U.jpg"
                },
                "distance": 720,
                "latitude": 40.70596749893083,
                "longitude": -73.99670720100403,
                "address": "Brooklyn Bridge",
                "type": "Bridge",
                "rating": 9.6
            },
            {
                "id": "3fd66200f964a520dbf11ee3",
                "name": "Vietnam Veterans Memorial Plaza",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/102559_FevPzlEYXRhkibBGV8qtnmLnFtIA2GvrVSXaHCd8_U8.jpg"
                },
                "distance": 895,
                "latitude": 40.70288495605898,
                "longitude": -74.0099036693573,
                "address": "55 Water St (Southern Tip)",
                "type": "Monument / Landmark",
                "rating": 8.9
            },
            {
                "id": "42829c80f964a5206a221fe3",
                "name": "Grand Central Terminal",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/708901_Wp8kf7WMP78cuRIsFtB7ma5FyrdNTAh27sFup40TI54.jpg"
                },
                "distance": 6180,
                "latitude": 40.752734263166026,
                "longitude": -73.97710013223526,
                "address": "87 E 42nd St (btwn Vanderbilt & Park Ave)",
                "type": "Train Station",
                "rating": 9.3
            }
        ]
    },
    "message": "Attractions venues fetched successfully"
}
```

This endpoint retrieves the Foursquare API service for getting the attraction venues (landmarks, historic sites, historic landmarks) around a specific latitude and longitude.  

### HTTP Request

`GET http://api.mashvisor.com/v1/forusquare/attractions` 

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
lat | Double | | The latitude to return the content for. Valid values: 40.7, ... etc.
lng | Double | | The longitude to return the content for. Valid values: -74, ... etc.

## List Activites

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1/foursquare/activities?lat=40.7&lng=-74")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1/foursquare/activities?lat=40.7&lng=-74",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://api-build.mashvisor.com/v1/foursquare/activities');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'lat' => '40.7',
  'lng' => '-74'
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

	url := "http://api-build.mashvisor.com/v1/foursquare/activities?lat=40.7&lng=-74"

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
        "count": 49,
        "data": [
            {
                "id": "46627c04f964a52069471fe3",
                "name": "Nelson Blue",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/wtWkha_FjIfEE5Evu12JYRK-TMG5rl4bAQVr4zQiIj0.jpg"
                },
                "distance": 868,
                "latitude": 40.7076946287674,
                "longitude": -74.00173172336243,
                "address": "233 Front St. (at Peck Slip)",
                "type": "Bar",
                "rating": 8.5
            },
            {
                "id": "576c2212498e72c8c38f1ddd",
                "name": "Liberty Park",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/13834_H9utJFY_sFnVFJuBLYLdFXZSZivXA4gFk0hW8tMa-Sw.jpg"
                },
                "distance": 1644,
                "latitude": 40.71038391621699,
                "longitude": -74.01386844682942,
                "address": "Liberty St & West St",
                "type": "Park",
                "rating": 8.4
            },
            {
                "id": "42893400f964a52054231fe3",
                "name": "Statue of Liberty",
                "image": {
                    "prefix": "https://igx.4sqi.net/img/general/",
                    "suffix": "/3650726_GuDp599O1OBbtHDRysZgLNe1mCh8rUV1u46V3kd6Y84.jpg"
                },
                "distance": 3973,
                "latitude": 40.68991099471658,
                "longitude": -74.04515640067416,
                "address": "Liberty Island",
                "type": "Monument / Landmark",
                "rating": 9.4
            }
        ]
    },
    "message": "Activities venues fetched successfully"
}
```

This endpoint retrieves the Foursquare API service for getting the activities venues around a specific latitude and longitude.  

### HTTP Request

`GET http://api.mashvisor.com/v1/forusquare/activities` 

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
lat | Double | | The latitude to return the content for. Valid values: 40.7, ... etc.
lng | Double | | The longitude to return the content for. Valid values: -74, ... etc.

# Neighborhood

## Get Neighborhood

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("http://api-build.mashvisor.com/v1.1/neighborhood/269590?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "http://api-build.mashvisor.com/v1.1/neighborhood/269590?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('http://api-build.mashvisor.com/v1.1/neighborhood/269590');
$request->setMethod(HTTP_METH_GET);

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

	url := "http://api-build.mashvisor.com/v1.1/neighborhood/269590?state=IL&_t=meowmeowmeow"

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
    "content": [
        {
            "id": 269590,
            "city": "Chicago",
            "country": "United States",
            "created_at": "2015-12-31T14:18:52.000Z",
            "latitude": 41.918651,
            "longitude": -87.638259,
            "name": "Lincoln Park",
            "state": "IL",
            "county": null,
            "is_village": 0,
            "description": "<p><a href=\"https://www.mashvisor.com/app/#!/neighborhood/lincoln-park-chicago-il/269590/demographics\">Lincoln Park</a>, as the name might indicate, is an area full of peaceful parks and trees. Lincoln Park is home to the <a href=\"http://www.lpzoo.org/\">Lincoln Park Zoo</a> and world&rsquo;s first Ferris Wheel. The park is over 1,200 acres of green space and has an annual free-access zoo in addition to a nature museum and conservatory. You can get the best of both worlds by heading to the Lakefront Trail and beaches, and enjoy the beach life with a background of skyscrapers.</p>\r\n\r\n<p>Shoppers enjoy Armitage Avenue which is full of boutiques and high-end shops. To get a taste of different cultures, Clark Street is full of ethnic restaurants, laid-back cafes, and confectionary stores. For more upbeat fun, this is definitelt the&nbsp;go-to area&nbsp;to enjoy diverse arts and entertainments with museums, the best theaters, and live music clubs. &nbsp;</p>\r\n",
            "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
            "updated_at": "2017-08-02T14:23:19.000Z",
            "single_home_value": 422500,
            "4room_value": null,
            "1room_value": 253900,
            "3room_value": 688100,
            "2room_value": 366100,
            "property_tax": 7863,
            "tax_rate": 1.861,
            "vacancy_rate": 0.08,
            "foreclosures": 0,
            "homes_for_sale_by_owner": 0,
            "homes_recently_sold": 0,
            "owners": 0.379076,
            "renters": 0.620924,
            "median_value_per_sq_ft": 340,
            "median_home_size": null,
            "mash_meter": 77.1555,
            "one_room_value": 1498.13,
            "two_room_value": 2073.32,
            "three_room_value": 2718.12,
            "four_room_value": 2978.5
        }
    ],
    "message": "Neighborhood details"
}
```

This endpoint retrieves the neighborhood's data set in Mashvisor database.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Properties

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/properties?page=1&state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/properties?page=1&state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/properties');
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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/properties?page=1&state=IL&_t=meowmeowmeow"

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
        "currentPage": "1",
        "itemsInPage": 5,
        "numberOfPages": 5,
        "totalItems": 24,
        "properties": [
            {
                "stateInterest": {
                    "state": "IL",
                    "thirtyYearFixed": 4.17,
                    "thirtyYearFixedCount": 0,
                    "fifteenYearFixed": 3.34,
                    "fifteenYearFixedCount": 0,
                    "fiveOneARM": 3.26,
                    "fiveOneARMCount": 0
                },
                "isShortSale": null,
                "source": "Jameson Real Estate LLC",
                "yearBuilt": 1886,
                "listhub_key": "3yd-MREDIL-09307121",
                "nextOpenHouseEndTime": null,
                "sqft": 1500,
                "lastSaleDate": "2004-02-09 00:00:00",
                "id": 129299,
                "state": "IL",
                "county": null,
                "originalSource": "Jameson Sotheby's Intl Realty",
                "longitude": "-87.63800048828125",
                "zip": 60614,
                "image": {
                    "image": "http://photos.listhub.net/MREDIL/09307121/1?lm=20170316T202609",
                    "url": "http://photos.listhub.net/MREDIL/09307121/1?lm=20170316T202609",
                    "width": 100,
                    "height": 100
                },
                "extra_images": [
                    "http://photos.listhub.net/MREDIL/09307121/1?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/2?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/3?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/4?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/5?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/6?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/7?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/8?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/9?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/10?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/11?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/12?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/13?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/14?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/15?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/16?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/17?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/18?lm=20170316T202609",
                    "http://photos.listhub.net/MREDIL/09307121/19?lm=20170316T202609"
                ],
                "videos": [],
                "virtual_tours": [],
                "tax": 21668.06,
                "listingId": "09307121",
                "ROI": {
                    "traditional_ROI": -1.48293,
                    "traditional_rental": 2073.32,
                    "airbnb_rental": 2219.58,
                    "airbnb_cap_rate": -1.37294,
                    "airbnb_ROI": -1.37294,
                    "traditional_cap_rate": -1.48293
                },
                "daysOnMarket": 48,
                "meta": {
                    "metaKey": "views",
                    "value": "3"
                },
                "neighborhood": {
                    "country": "United States",
                    "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
                    "city": "Chicago",
                    "singleHomeValue": 422500,
                    "mashMeter": 77.1555,
                    "latitude": "41.91865100000000",
                    "description": "<p><a href=\"https://www.mashvisor.com/app/#!/neighborhood/lincoln-park-chicago-il/269590/demographics\">Lincoln Park</a>, as the name might indicate, is an area full of peaceful parks and trees. Lincoln Park is home to the <a href=\"http://www.lpzoo.org/\">Lincoln Park Zoo</a> and world&rsquo;s first Ferris Wheel. The park is over 1,200 acres of green space and has an annual free-access zoo in addition to a nature museum and conservatory. You can get the best of both worlds by heading to the Lakefront Trail and beaches, and enjoy the beach life with a background of skyscrapers.</p>\r\n\r\n<p>Shoppers enjoy Armitage Avenue which is full of boutiques and high-end shops. To get a taste of different cultures, Clark Street is full of ethnic restaurants, laid-back cafes, and confectionary stores. For more upbeat fun, this is definitelt the&nbsp;go-to area&nbsp;to enjoy diverse arts and entertainments with museums, the best theaters, and live music clubs. &nbsp;</p>\r\n",
                    "singleHomeValue_formatted": "$422,500",
                    "is_village": false,
                    "mashMeter_formatted": 77.1555,
                    "name": "Lincoln Park",
                    "id": 269590,
                    "state": "IL",
                    "longitude": "-87.63825900000000"
                },
                "homeType": "Single Family Residential",
                "beds": 2,
                "favorite": "N",
                "status": "Active",
                "broker_number": "(312) 335-3291",
                "city": "Chicago",
                "saleType": "MLS Listing",
                "latitude": "41.91510009765625",
                "description": "This is a unique opportunity! Call Me for details.  The property is a GUT Rehab!! One of the Last Opportunities to build your DREAM HOME in Old Town!!!  Amazing and Rare, One of a Kind Old Town opportunity on one the most desirable one- way, tree-lined streets!  36x124 lot zoned RM5 (potentially up to 8000 sq ft) with Alley Access.  Due to Old Town Association guidelines and Landmark status, the  structure on the back of the lot will have to remain (possibly a 4 car garage? w/studio above?) Sanborn maps indicate there previously was a home on the front portion of the lot thus possibly establishing precedence. Buyer will have to do the due diligence.  Build your dream home in Chicago's Prestigious Old Town Triangle!   (Pictures are of the current approx. 1500sq ft 2 story cottage structure located on the back of the property)  Bring your Builder!!",
                "nextOpenHouseDate": null,
                "recentReductionDate": null,
                "title": "2 Stories - Chicago, IL",
                "rent_appreciation_rate": null,
                "originalListPrice": 3200000,
                "parkingSpots": 0,
                "parkingType": null,
                "address": "1810 North Orleans Street",
                "nextOpenHouseStartTime": null,
                "lotSize": 4500,
                "broker_name": "Jameson Real Estate LLC",
                "agent_profile": [
                    {
                        "id": 9523,
                        "first_name": "Debbie",
                        "last_name": "Maue",
                        "email": "dmaue@jameson.com",
                        "phone_number": "(312) 751-0300",
                        "office_id": 1961,
                        "website": "http://www.debbiemaue.com",
                        "address": "425 W. North Ave.",
                        "city": "Chicago",
                        "state": "IL",
                        "company": "Jameson Sotheby's Intl Realty",
                        "image": "http://brokerlogos.listhub.net/MREDIL/c5ababf02400f23401240234ace2008f/20091002115130926.pjpeg",
                        "real_estate_licence": null,
                        "years_of_experience": null,
                        "areas_served": null,
                        "agent_specialities": null,
                        "agent_experience": null,
                        "summary": null,
                        "title": null,
                        "mls_id": null,
                        "source": "Listhub",
                        "created_at": "2016-12-13T16:57:27.000Z",
                        "updated_at": "2017-07-25T01:32:04.000Z",
                        "listhub_id": "3yd-MREDIL-121897",
                        "office": "Jameson Sotheby's Intl Realty"
                    }
                ],
                "url": "http://listings.listhub.net/pages/MREDIL/09307121/?channel=mashv",
                "baths": 1,
                "address_revealing": true,
                "location": "Lincoln Park",
                "interested": "Y",
                "listPrice": 1500000,
                "lastSalePrice": 378000
            },
            {
                "stateInterest": {
                    "state": "IL",
                    "thirtyYearFixed": 4.17,
                    "thirtyYearFixedCount": 0,
                    "fifteenYearFixed": 3.34,
                    "fifteenYearFixedCount": 0,
                    "fiveOneARM": 3.26,
                    "fiveOneARMCount": 0
                },
                "isShortSale": null,
                "source": "Jameson Sotheby's International Realty",
                "yearBuilt": 1999,
                "listhub_key": "3yd-MREDIL-09344718",
                "nextOpenHouseEndTime": null,
                "sqft": 2041,
                "lastSaleDate": null,
                "id": 159341,
                "state": "IL",
                "county": null,
                "originalSource": "Jameson Sotheby's International Realty",
                "longitude": "-87.64260101318360",
                "zip": 60614,
                "image": {
                    "image": "http://photos.listhub.net/MREDIL/09344718/1?lm=20161116T000703",
                    "url": "http://photos.listhub.net/MREDIL/09344718/1?lm=20161116T000703",
                    "width": 100,
                    "height": 100
                },
                "extra_images": [
                    "http://photos.listhub.net/MREDIL/09344718/1?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/2?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/3?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/4?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/5?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/6?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/7?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/8?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/9?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/10?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/11?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/12?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/13?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/14?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/15?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/16?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/17?lm=20161116T000703",
                    "http://photos.listhub.net/MREDIL/09344718/18?lm=20161116T000703"
                ],
                "videos": [],
                "virtual_tours": [],
                "tax": 18434,
                "listingId": "09344718",
                "ROI": {
                    "traditional_ROI": -1.22786,
                    "traditional_rental": 2073.32,
                    "airbnb_rental": 2219.58,
                    "airbnb_cap_rate": -1.06272,
                    "airbnb_ROI": -1.06272,
                    "traditional_cap_rate": -1.22786
                },
                "daysOnMarket": 5,
                "meta": {
                    "metaKey": null,
                    "value": null
                },
                "neighborhood": {
                    "country": "United States",
                    "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
                    "city": "Chicago",
                    "singleHomeValue": 422500,
                    "mashMeter": 77.1555,
                    "latitude": "41.91865100000000",
                    "description": "<p><a href=\"https://www.mashvisor.com/app/#!/neighborhood/lincoln-park-chicago-il/269590/demographics\">Lincoln Park</a>, as the name might indicate, is an area full of peaceful parks and trees. Lincoln Park is home to the <a href=\"http://www.lpzoo.org/\">Lincoln Park Zoo</a> and world&rsquo;s first Ferris Wheel. The park is over 1,200 acres of green space and has an annual free-access zoo in addition to a nature museum and conservatory. You can get the best of both worlds by heading to the Lakefront Trail and beaches, and enjoy the beach life with a background of skyscrapers.</p>\r\n\r\n<p>Shoppers enjoy Armitage Avenue which is full of boutiques and high-end shops. To get a taste of different cultures, Clark Street is full of ethnic restaurants, laid-back cafes, and confectionary stores. For more upbeat fun, this is definitelt the&nbsp;go-to area&nbsp;to enjoy diverse arts and entertainments with museums, the best theaters, and live music clubs. &nbsp;</p>\r\n",
                    "singleHomeValue_formatted": "$422,500",
                    "is_village": false,
                    "mashMeter_formatted": 77.1555,
                    "name": "Lincoln Park",
                    "id": 269590,
                    "state": "IL",
                    "longitude": "-87.63825900000000"
                },
                "homeType": "Condo/Coop",
                "beds": 2,
                "favorite": "N",
                "status": "Active",
                "broker_number": "(800) 369-7300",
                "city": "Chicago",
                "saleType": "MLS Listing",
                "latitude": "41.91370010375977",
                "description": "Stunning 2-story penthouse on one of Lincoln Park's most desirable streets.  Dramatic two-story living room with gas fireplace and juliette balcony. Open kitchen features Sub-zero, Viking and Bosch appliances with granite counters and large island. Main floor bedroom and full bath plus first floor family room which opens to deck for outdoor dining. Upper level features spacious master bedroom with 2 walk-in closets, luxe bath with double sinks, separate shower and whirlpool tub. Additional loft-like bedroom or den leads to  phenomenal, private roof deck with killer city views. Freshly painted, floors refinished and ready for immediate occupancy. New front loading LG washer & dryer. Garage parking.",
                "nextOpenHouseDate": null,
                "recentReductionDate": null,
                "title": "Condo-duplex - CHICAGO, IL",
                "rent_appreciation_rate": null,
                "originalListPrice": 1195000,
                "parkingSpots": 1,
                "parkingType": "Garage",
                "address": "1726 North Mohawk Street North #3S",
                "nextOpenHouseStartTime": null,
                "lotSize": null,
                "broker_name": "Jameson Sotheby's International Realty",
                "agent_profile": [
                    {
                        "id": 7948,
                        "first_name": "Liz",
                        "last_name": "Bulf",
                        "email": "lbulf@jamesonsir.com",
                        "phone_number": "(847) 869-7300",
                        "office_id": 12980,
                        "website": "http://www.lizbulf.com",
                        "address": "2934 Central Street",
                        "city": "Evanston",
                        "state": "IL",
                        "company": "Jameson Sotheby's International Realty",
                        "image": "http://brokerlogos.listhub.net/MREDIL/c5ababc31ab6861b011ab68f72d904de/20110920132046821.png",
                        "real_estate_licence": null,
                        "years_of_experience": null,
                        "areas_served": null,
                        "agent_specialities": null,
                        "agent_experience": null,
                        "summary": null,
                        "title": null,
                        "mls_id": null,
                        "source": "Listhub",
                        "created_at": "2016-12-13T15:32:51.000Z",
                        "updated_at": "2017-07-25T01:24:05.000Z",
                        "listhub_id": "3yd-MREDIL-38874",
                        "office": "Jameson Sotheby's International Realty"
                    }
                ],
                "url": "http://listings.listhub.net/pages/MREDIL/09344718/?channel=mashv",
                "baths": 3,
                "address_revealing": true,
                "location": "Lincoln Park",
                "interested": "Y",
                "listPrice": 999000,
                "lastSalePrice": null
            },
            {
                "stateInterest": {
                    "state": "IL",
                    "thirtyYearFixed": 4.17,
                    "thirtyYearFixedCount": 0,
                    "fifteenYearFixed": 3.34,
                    "fifteenYearFixedCount": 0,
                    "fiveOneARM": 3.26,
                    "fiveOneARMCount": 0
                },
                "isShortSale": null,
                "source": "CONLON/Christie's International Real Estate",
                "yearBuilt": 2017,
                "listhub_key": "3yd-MREDIL-09708325",
                "nextOpenHouseEndTime": null,
                "sqft": 0,
                "lastSaleDate": null,
                "id": 397084,
                "state": "IL",
                "county": null,
                "originalSource": null,
                "longitude": "-87.64765167236328",
                "zip": 60614,
                "image": {
                    "image": "http://photos.listhub.net/MREDIL/09708325/1?lm=20170801T222336",
                    "url": "http://photos.listhub.net/MREDIL/09708325/1?lm=20170801T222336",
                    "width": 100,
                    "height": 100
                },
                "extra_images": [
                    "http://photos.listhub.net/MREDIL/09708325/1?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/2?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/3?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/4?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/5?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/6?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/7?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/8?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/9?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/10?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/11?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/12?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/13?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/14?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/15?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/16?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/17?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/18?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/19?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/20?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/21?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/22?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/23?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/24?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/25?lm=20170801T222336",
                    "http://photos.listhub.net/MREDIL/09708325/26?lm=20170801T222336"
                ],
                "videos": [],
                "virtual_tours": [],
                "tax": 0,
                "listingId": "09708325",
                "ROI": {
                    "traditional_ROI": -0.78298,
                    "traditional_rental": 2978.5,
                    "airbnb_rental": 4873.36,
                    "airbnb_cap_rate": 0.86244,
                    "airbnb_ROI": 0.86244,
                    "traditional_cap_rate": -0.78298
                },
                "daysOnMarket": null,
                "meta": {
                    "metaKey": "views",
                    "value": "11"
                },
                "neighborhood": {
                    "country": "United States",
                    "image": "https://9ac82074a42d61a93c2a-4910baab8d3df1a59178432e0b86512c.ssl.cf5.rackcdn.com",
                    "city": "Chicago",
                    "singleHomeValue": 422500,
                    "mashMeter": 77.1555,
                    "latitude": "41.91865100000000",
                    "description": "<p><a href=\"https://www.mashvisor.com/app/#!/neighborhood/lincoln-park-chicago-il/269590/demographics\">Lincoln Park</a>, as the name might indicate, is an area full of peaceful parks and trees. Lincoln Park is home to the <a href=\"http://www.lpzoo.org/\">Lincoln Park Zoo</a> and world&rsquo;s first Ferris Wheel. The park is over 1,200 acres of green space and has an annual free-access zoo in addition to a nature museum and conservatory. You can get the best of both worlds by heading to the Lakefront Trail and beaches, and enjoy the beach life with a background of skyscrapers.</p>\r\n\r\n<p>Shoppers enjoy Armitage Avenue which is full of boutiques and high-end shops. To get a taste of different cultures, Clark Street is full of ethnic restaurants, laid-back cafes, and confectionary stores. For more upbeat fun, this is definitelt the&nbsp;go-to area&nbsp;to enjoy diverse arts and entertainments with museums, the best theaters, and live music clubs. &nbsp;</p>\r\n",
                    "singleHomeValue_formatted": "$422,500",
                    "is_village": false,
                    "mashMeter_formatted": 77.1555,
                    "name": "Lincoln Park",
                    "id": 269590,
                    "state": "IL",
                    "longitude": "-87.63825900000000"
                },
                "homeType": "Condo/Coop",
                "beds": 4,
                "favorite": null,
                "status": "Active",
                "broker_number": "(312) 733-7201",
                "city": "Chicago",
                "saleType": "MLS Listing",
                "latitude": "41.91946411132813",
                "description": "Burling on The Park -this wonderful boutique, new construction building is situated in a fabulous location in the heart of Lincoln Park.  Overlooking Oz Park, set on a secluded side street this is the ultimate address. This stunning oversized 4 bed 2.5 bath duplex home has a wonderful and unique open floorplan, fantastic light, radiantly heated lower level and is finished with the finest quality workmanship throughout. Tasteful transitional trim, porcelain & quartz stone, a chef's kitchen (sub Zero, Wolf, Bosch), Spa like master bath with steam shower & split vanities. Featuring very generous room sizes, front terrace overlooking the park & rear deck. Top of the line finishes throughout, all with a luxurious transitional/modern feel .",
                "nextOpenHouseDate": null,
                "recentReductionDate": null,
                "title": "Condo,Condo-duplex,Low Rise (1-3 Stories) - CHICAGO, IL",
                "rent_appreciation_rate": null,
                "originalListPrice": null,
                "parkingSpots": null,
                "parkingType": null,
                "address": "2042 North BURLING Street #1",
                "nextOpenHouseStartTime": null,
                "lotSize": null,
                "broker_name": "CONLON/Christie's International Real Estate",
                "agent_profile": [
                    {
                        "id": 11074,
                        "first_name": "Sam",
                        "last_name": "Jenkins",
                        "email": "sam@conlonrealestate.com",
                        "phone_number": "(312) 733-7201",
                        "office_id": 2595,
                        "website": "http://www.conlonrealestate.com",
                        "address": "401 W Ontario St.  Ste 401",
                        "city": "Chicago",
                        "state": "IL",
                        "company": "Conlon: A Real Estate Company",
                        "image": "http://brokerlogos.listhub.net/MREDIL/e9a3b861263411dfb94800219b994c72/20140617152211459.png",
                        "real_estate_licence": null,
                        "years_of_experience": null,
                        "areas_served": null,
                        "agent_specialities": null,
                        "agent_experience": null,
                        "summary": null,
                        "title": null,
                        "mls_id": null,
                        "source": "Listhub",
                        "created_at": "2016-12-13T18:34:26.000Z",
                        "updated_at": "2017-07-25T01:40:13.000Z",
                        "listhub_id": "3yd-MREDIL-149380",
                        "office": "Conlon: A Real Estate Company"
                    }
                ],
                "url": "http://listings.listhub.net/pages/MREDIL/09708325/?channel=mashv",
                "baths": 3,
                "address_revealing": true,
                "location": "Lincoln Park",
                "interested": null,
                "listPrice": 1299000,
                "lastSalePrice": null
            }
        ]
    }
}
```

This endpoint retrieves the properties data entities for a specific neighborhood.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/properties` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page | Integer | 1 | The page of results set number
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Airbnb Info

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/details?page=1&state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/details?page=1&state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/details');
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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/details?page=1&state=IL&_t=meowmeowmeow"

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
                "occupancy": 22,
                "airbnbNeighborhoodId": 269590,
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
                "image": "https://a0.muscache.com/im/pictures/c9b83f11-4d98-4ce0-afba-5ee06b3b7d7e.jpg?aki_policy=medium",
                "rental_income": 2026.2,
                "neighborhood": {
                    "id": 269590,
                    "name": "Lincoln Park"
                },
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
                "occupancy": 22,
                "airbnbNeighborhoodId": 269590,
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
                "rental_income": 1082.4,
                "neighborhood": {
                    "id": 269590,
                    "name": "Lincoln Park"
                },
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
                "occupancy": 22,
                "airbnbNeighborhoodId": 269590,
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
                "rental_income": 844.8,
                "neighborhood": {
                    "id": 269590,
                    "name": "Lincoln Park"
                },
                "nightRate": 128,
                "property_id": "9577653",
                "airbnbZIP": "60614"
            }
        ],
        "num_of_properties": 114,
        "avg_occupancy": "44.4825",
        "avg_price": "156.5439",
        "num_page_properties": 3,
        "page": "1"
    }
}
```

This endpoint retrieves the Airbnb properties for a specific neighborhood.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/airbnb/details` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page | Integer | 1 | The page of results set number
items | Integer | 5 | The number of properties per page (max >=200)
bedrooms | Integer | | Number of bedrooms
pid | Long | | The investment property id to compare the neighborhood properties with.
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Traditional Info

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/traditional/listing?page=1&state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/traditional/listing?page=1&state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/traditional/listing');
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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/traditional/listing?page=1&state=IL&_t=meowmeowmeow"

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
        "results": [
            {
                "id": 2322208,
                "title": "Mid Rise (4-6 Stories),Vintage,Residential Rental - CHICAGO, IL",
                "lon": "-87.64175415039062",
                "lat": "41.92339324951172",
                "state": "IL",
                "city": "Chicago",
                "neighborhood": "Lincoln Park",
                "description": "Unique and large 3 bedroom, 2-bath unit on PRIME East Lincoln Park street, walk to lake, park, stores and more. This unit features a modern floor plan with large living/dining/kitchen space with high ceilings in sun-filled front of the apartment, master suite in rear, and two nice-sized bedrooms with shared hall bath. Parking available for additional $150. Tenant controlled heat with central air; washer/dryer in unit; small balcony off master suite with easy access to shared garage roof deck. Will rent fast as there's nothing like it on the market.",
                "price": 3500,
                "baths": 2,
                "beds": 3,
                "sqft": 2000,
                "year_built": 1896,
                "mls_id": "09570659",
                "image": "http://photos.listhub.net/MREDIL/09570659/1?lm=20170321T152608",
                "zipcode": "60614",
                "address": "2250 North Cleveland Avenue #2",
                "type": "single_home",
                "status": "inactive",
                "listhub_key": "3yd-MREDIL-09570659",
                "broker_name": "CONLON/Christie's International Real Estate",
                "broker_number": "(312) 733-7201",
                "source": "CONLON/Christie's International Real Estate",
                "neighborhood_id": 269590,
                "url": "http://listings.listhub.net/pages/MREDIL/09570659/?channel=mashv",
                "created_at": "2017-02-27T13:41:07.000Z",
                "updated_at": "2017-04-05T10:54:59.000Z"
            },
            {
                "id": 2322346,
                "title": "Townhouse-trilevel,Residential Rental - CHICAGO, IL",
                "lon": "-87.63965606689453",
                "lat": "41.91917800903320",
                "state": "IL",
                "city": "Chicago",
                "neighborhood": "Lincoln Park",
                "description": "Rarely available executive rental at The Pointe! End-unit Town Home that lives like a single family home. Sun drenched with windows on 3 sides, 4bdrs, 3.1 baths, formal DR, LR w/marble fireplace, family room, 2 decks, terrace & patio. Custom finishes throughout, new kitchen and baths, hardwood  floors, crown molding. Chef's kitchen has granite, white cabinets, SS apps, 6 burner stove and eat-in area. Huge master w/designer spa bath. Private 2car gar w/built-in cabinets. Lincoln School district. Close to Lincoln Park, the lake and all transportation.",
                "price": 7500,
                "baths": 4,
                "beds": 4,
                "sqft": 3633,
                "year_built": null,
                "mls_id": "09519732",
                "image": "http://photos.listhub.net/MREDIL/09519732/1?lm=20170303T203421",
                "zipcode": "60614",
                "address": "2017 North Lincoln Avenue #A",
                "type": "single_home",
                "status": "inactive",
                "listhub_key": "3yd-MREDIL-09519732",
                "broker_name": "Dream Town Realty",
                "broker_number": "312.265.8000",
                "source": "Dream Town Realty",
                "neighborhood_id": 269590,
                "url": "http://listings.listhub.net/pages/MREDIL/09519732/?channel=mashv",
                "created_at": "2017-02-27T13:44:56.000Z",
                "updated_at": "2017-03-30T11:04:54.000Z"
            },
            {
                "id": 2322687,
                "title": "Flat,Residential Rental - CHICAGO, IL",
                "lon": "-87.64434814453125",
                "lat": "41.91797637939453",
                "state": "IL",
                "city": "Chicago",
                "neighborhood": "Lincoln Park",
                "description": "Large Lincoln Park 3 bedroom features all hardwood floors and lots of original wood work.  Eat-In kitchen plus separate dining room.  Pets considered.  Parking available at extra cost.  Terrific location, bus stops at your door.  Short walk to brown line and purple lines EL stop.",
                "price": 2700,
                "baths": 1,
                "beds": 3,
                "sqft": 2000,
                "year_built": 1907,
                "mls_id": "09511949",
                "image": "http://photos.listhub.net/MREDIL/09511949/1?lm=20170223T203330",
                "zipcode": "60614",
                "address": "615 West Armitage Avenue #2",
                "type": "single_home",
                "status": "inactive",
                "listhub_key": "3yd-MREDIL-09511949",
                "broker_name": "Lakefront Realty Group, Inc.",
                "broker_number": "(312) 286-7402",
                "source": "Lakefront Realty Group, Inc.",
                "neighborhood_id": 269590,
                "url": "http://listings.listhub.net/pages/MREDIL/09511949/?channel=mashv",
                "created_at": "2017-02-27T13:54:51.000Z",
                "updated_at": "2017-05-20T02:06:49.000Z"
            }
        ],
        "total_results": 203,
        "total_pages": 68,
        "current_page": "1"
    }
}
```

This endpoint retrieves the Traditional properties for a specific neighborhood.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/traditional/listing` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page | Integer | 1 | The page of results set number
items | Integer | 3 | The number of properties per page (max >=200)
category | String | | Category type of the items
min_price | Integer | | Filter items according to price
max_price | Integer | | Filter items according to price
pid | Long | | The investment property id to compare the neighborhood properties with.
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Historical Performance

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/historical/airbnb?page=1&state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/historical/airbnb?page=1&state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/historical/airbnb');
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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/historical/airbnb?page=1&state=IL&_t=meowmeowmeow"

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
        "results": [
            {
                "year": 2016,
                "month": 10,
                "value": 59
            },
            {
                "year": 2016,
                "month": 11,
                "value": 58
            },
            {
                "year": 2016,
                "month": 12,
                "value": 13
            },
            {
                "year": 2017,
                "month": 1,
                "value": 17
            },
            {
                "year": 2017,
                "month": 2,
                "value": 33
            },
            {
                "year": 2017,
                "month": 3,
                "value": 12
            },
            {
                "year": 2017,
                "month": 4,
                "value": 4
            },
            {
                "year": 2017,
                "month": 5,
                "value": 5
            },
            {
                "year": 2017,
                "month": 6,
                "value": 23
            },
            {
                "year": 2017,
                "month": 7,
                "value": 10
            }
        ]
    },
    "message": "Historical Data fetched successfully"
}
```

This endpoint retrieves historical airbnb/traditional average values in each month for a specific neighborhood to draw the chart

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/historical/{source}` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.
source | String | | The listing source: airbnb, traditional

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
category | String | | Property type: Flat, House, Apartment, Loft
average_by | String | Get average value of: occupancy, price, revenue
percentile_rate | Float | 0.1 | Get the value of the top percentile: 0.15, 0.25, 0.50, 1.00
beds | Integer | | Filter by number of beds: 0,1,2,3,4
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Airbnb Insights

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/insights?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/insights?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/insights');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/insights?state=IL&_t=meowmeowmeow"

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
        "bedrooms": {
            "slope": -1,
            "RSquare": -1
        },
        "price": {
            "slope": -0.0006672402719272157,
            "RSquare": 0.0908631453569766
        },
        "stars_rate": {
            "slope": -1,
            "RSquare": -1
        },
        "bathrooms": {
            "slope": -1,
            "RSquare": -1
        },
        "beds": {
            "slope": -1,
            "RSquare": -1
        },
        "reviews_count": {
            "slope": 0.0011546983930962372,
            "RSquare": 0.1299686349686472
        }
    }
}
```

This endpoint retrieves regression analysis insights data for specific neighborhood.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/airbnb/insights` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Airbnb Prices

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/prices?state=IL&_t=meowmeowmeow&bedrooms=1")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/prices?state=IL&_t=meowmeowmeow&bedrooms=1",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/prices');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'IL',
  '_t' => 'meowmeowmeow',
  'bedrooms' => '1'
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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/airbnb/prices?state=IL&_t=meowmeowmeow&bedrooms=1"

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
        "bedrooms_list": [
            0,
            1,
            2,
            3,
            4
        ],
        "property_types_list": [
            "Apartment",
            "Condominium",
            "House",
            "Loft",
            "Townhouse",
            "Other"
        ],
        "low_value": 59,
        "high_value": 243,
        "upper_quartile": 143,
        "lower_quartile": 93,
        "median_price": 118,
        "count": 46,
        "prices": [
            59,
            64,
            65,
            68,
            72,
            77,
            78,
            87,
            88,
            91,
            92,
            93,
            94,
            95,
            97,
            99,
            102,
            105,
            106,
            110,
            111,
            115,
            116,
            119,
            122,
            123,
            124,
            126,
            128,
            132,
            134,
            136,
            137,
            141,
            143,
            147,
            148,
            150,
            151,
            157,
            162,
            167,
            176,
            210,
            234,
            243
        ]
    }
}
```

This endpoint retrieves regression analysis for Airbnb prices for specific neighborhood.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/airbnb/prices` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
bedrooms | Integer 0+ | | You can list properties that has 0 bedrooms and up
category | String | | Loft, House, Apartment ... etc
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Optimal Insights

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/optimal/insights?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/optimal/insights?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/optimal/insights');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/optimal/insights?state=IL&_t=meowmeowmeow"

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
        "strategy": "traditional",
        "property_type": "Townhouse",
        "bedrooms": 3
    }
}
```

This endpoint retrieves regression analysis for neighborhood optimal insights.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/optimal/insights` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Bookings

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/bookings?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/bookings?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/bookings');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/bookings?state=IL&_t=meowmeowmeow"

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
        "total_results": 114,
        "total_pages": 57,
        "current_page": 1,
        "properties": [
            {
                "name": "Charming 3BR in Lincoln Park",
                "property_id": "13280235",
                "months": [
                    {
                        "year": 2016,
                        "month": 10,
                        "occupancy": 10,
                        "rental_income": 2093
                    },
                    {
                        "year": 2016,
                        "month": 11,
                        "occupancy": 18,
                        "rental_income": 3564
                    },
                    {
                        "year": 2016,
                        "month": 12,
                        "occupancy": 5,
                        "rental_income": 1061
                    },
                    {
                        "year": 2017,
                        "month": 1,
                        "occupancy": 1,
                        "rental_income": 98
                    },
                    {
                        "year": 2017,
                        "month": 2,
                        "occupancy": 4,
                        "rental_income": 668
                    },
                    {
                        "year": 2017,
                        "month": 3,
                        "occupancy": 14,
                        "rental_income": 2957
                    },
                    {
                        "year": 2017,
                        "month": 4,
                        "occupancy": 11,
                        "rental_income": 2886
                    },
                    {
                        "year": 2017,
                        "month": 5,
                        "occupancy": 8,
                        "rental_income": 2824
                    },
                    {
                        "year": 2017,
                        "month": 6,
                        "occupancy": 16,
                        "rental_income": 6964
                    },
                    {
                        "year": 2017,
                        "month": 7,
                        "occupancy": 10,
                        "rental_income": 3734
                    }
                ],
                "nightly_price": 257
            },
            {
                "name": "Lincoln Park Luxury XLarge Studio Stunning Rooftop",
                "property_id": "13981116",
                "months": [
                    {
                        "year": 2016,
                        "month": 10,
                        "occupancy": 27,
                        "rental_income": 3321
                    },
                    {
                        "year": 2016,
                        "month": 11,
                        "occupancy": 21,
                        "rental_income": 2331
                    },
                    {
                        "year": 2016,
                        "month": 12,
                        "occupancy": 11,
                        "rental_income": 1165
                    },
                    {
                        "year": 2017,
                        "month": 1,
                        "occupancy": 28,
                        "rental_income": 3638
                    },
                    {
                        "year": 2017,
                        "month": 2,
                        "occupancy": 30,
                        "rental_income": 3270
                    },
                    {
                        "year": 2017,
                        "month": 3,
                        "occupancy": 30,
                        "rental_income": 4470
                    },
                    {
                        "year": 2017,
                        "month": 4,
                        "occupancy": 25,
                        "rental_income": 3710
                    },
                    {
                        "year": 2017,
                        "month": 5,
                        "occupancy": 23,
                        "rental_income": 3581
                    },
                    {
                        "year": 2017,
                        "month": 6,
                        "occupancy": 24,
                        "rental_income": 3576
                    },
                    {
                        "year": 2017,
                        "month": 7,
                        "occupancy": 24,
                        "rental_income": 3499
                    }
                ],
                "nightly_price": 133
            }
        ]
    },
    "message": "Neighborhood monthly bookings fetched successfully"
}
```

This endpoint retrieves the Airbnb monthly bookings per neighborhood id.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/bookings` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page | Integer | 1 | The page to return the content for. Valid values:1, ... etc.
items | Integer | 5 | The items - properties- to return the content for. Valid values: 10, ... etc.
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Marker

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/marker?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/marker?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/marker');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/marker?state=IL&_t=meowmeowmeow"

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
        "id": 269590,
        "name": "Lincoln Park",
        "city": "Chicago",
        "state": "IL",
        "latitude": 41.918651,
        "longitude": -87.638259,
        "mashMeter": 77.1555,
        "median_price": 422500,
        "airbnb_rental": {
            "roi": 0.4685075868513774,
            "cap_rate": 8.28361975897219,
            "rental_income": 2916.5244568047915
        },
        "traditional_rental": {
            "roi": -0.05762696130709215,
            "cap_rate": 6.580878106508875,
            "rental_income": 2317.0175
        }
    },
    "message": "Neighborhood markers info fetched successfully"
}
```

This endpoint retrieves detailed marker information about specific neighborhood determined by the path parameter (id).

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/marker` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Bar Info

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/bar?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/bar?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/bar');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/bar?state=IL&_t=meowmeowmeow"

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
        "id": "269590",
        "name": "Lincoln Park",
        "city": "Chicago",
        "state": "IL",
        "num_of_properties": 24,
        "num_of_airbnb_properties": 114,
        "num_of_traditional_properties": 203,
        "latitude": 41.918651,
        "longitude": -87.638259,
        "mashMeter": 77.1555,
        "strategy": "traditional",
        "avg_occupancy": "44.4825",
        "median_price": 422500,
        "airbnb_rental": {
            "roi": 0.4685075868513774,
            "cap_rate": 8.28361975897219,
            "rental_income": 2916.5244568047915
        },
        "traditional_rental": {
            "roi": -0.05762696130709215,
            "cap_rate": 6.580878106508875,
            "rental_income": 2317.0175
        }
    },
    "message": "Neighborhood bar fetched successfully"
}
```

This endpoint retrieves detailed bar info for the search information about specific neighborhood determined by the path parameter (id).

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/bar` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## Get Nearby Neighborhoods

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/269590/nearby?state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/269590/nearby?state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/269590/nearby');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/269590/nearby?state=IL&_t=meowmeowmeow"

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
        "total_results": 5,
        "page": 1,
        "state": "IL",
        "city": "Chicago",
        "neighborhoods": [
            {
                "id": 403304,
                "name": "Old Town Triangle",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.914799,
                "longitude": -87.632214,
                "occupancy": "49.2178",
                "total_listing": 225
            },
            {
                "id": 403308,
                "name": "Park West",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.92919,
                "longitude": -87.639256,
                "occupancy": "48.1878",
                "total_listing": 197
            },
            {
                "id": 403301,
                "name": "Old Town",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.907443,
                "longitude": -87.637414,
                "occupancy": "49.5758",
                "total_listing": 66
            },
            {
                "id": 403305,
                "name": "Ranch Triangle",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.914481,
                "longitude": -87.656148,
                "occupancy": "48.1982",
                "total_listing": 217
            },
            {
                "id": 403303,
                "name": "Gold  Coast",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.90595,
                "longitude": -87.629635,
                "occupancy": "47.6584",
                "total_listing": 281
            }
        ]
    }
}
```

This endpoint retrieves the nearby neighborhoods for a specific neighborhood.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/{id}/nearby` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
id | Long | | The neighborhood Id from the Mashvisor database, you can get it from the search api.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page | Integer | 1 | The page number value, ex: 1
items | Integer | 5 | The items number to be retreived per page
state | String | | The state of the neighborhood should be provided to the api or api will throw error 404.

## List City Neighborhoods

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/neighborhood/search?city=Chicago&state=IL&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/neighborhood/search?city=Chicago&state=IL&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/neighborhood/search');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'city' => 'Chicago',
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

	url := "https://api-build.mashvisor.com/v1.1/neighborhood/search?city=Chicago&state=IL&_t=meowmeowmeow"

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
        "results": [
            {
                "id": 7930,
                "name": "Wicker Park",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.906824,
                "longitude": -87.677278
            },
            {
                "id": 28173,
                "name": "Cragin",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.928408,
                "longitude": -87.756258
            },
            {
                "id": 33420,
                "name": "Pilsen",
                "city": "Chicago",
                "state": "IL",
                "latitude": 41.852318,
                "longitude": -87.655448
            }
        ],
        "total_results": 227,
        "total_pages": 76,
        "current_page": 1
    }
}
```

This endpoint retrieves the neighborhoods in a specific city or neighborhood itself.

### HTTP Request

`GET http://api.mashvisor.com/v1.1/neighborhood/search` 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
page | Integer | 1 | The page number value, ex: 1
items | Integer | 10 | The items number to be retreived per page
neighborhood | String | | The neighborhood name from the Mashvisor database, you can get it from the search api
city | String | | The city you want to search in.
state | String | | The state you want to search in.

# Notify

## Notify Team

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/notify?city=Las%20Vegas&state=NV")
  .post(null)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/json")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/notify?city=Las%20Vegas&state=NV",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/json"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/notify');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  'city' => 'Las Vegas',
  'state' => 'NV'
));

$request->setHeaders(array(
  'content-type' => 'application/json',
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

	url := "https://api-build.mashvisor.com/v1/notify?city=Las%20Vegas&state=NV"

	req, _ := http.NewRequest("POST", url, nil)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/json")

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
        "json": {
            "id": 357,
            "country": "United States",
            "state": "NV",
            "city": "Las Vegas",
            "neighborhood": null,
            "zip": null,
            "createdAt": "Tue Aug 08 10:11:51 UTC 2017",
            "updatedAt": null
        }
    },
    "message": "User has been notified successfully"
}
```

This endpoint notify Mashvisor team about location, that accepts User JWT Token & JSON string includes all the address.  

### HTTP Request

`POST http://api.mashvisor.com/v1/notify` 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | State name, ex: NV.
city | String | | City name, ex: Las Vegas.

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | Bearer JWT_TOKEN | 
Content-Type | application/json | 

# Property

# Search

# Summary

## Get City Summary

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/summary/listing/IL/Chicago?_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/summary/listing/IL/Chicago?_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/summary/listing/IL/Chicago');
$request->setMethod(HTTP_METH_GET);

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

	url := "https://api-build.mashvisor.com/v1.1/summary/listing/IL/Chicago?_t=meowmeowmeow"

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
        "airbnb_listings": 2286,
        "traditional_listings": 12930,
        "investment_properties": 3438,
        "active_neighborhoods": 222,
        "avg_occupancy": "44.9857",
        "avg_nightly_price": "150.5355",
        "avg_property_price": "423929.3589",
        "avg_airbnb_ROI": 1.3229142864480714,
        "avg_traditional_ROI": 1.97556615152836
    }
}
```

This endpoint retrieves a summary of airbnb properties, traditional properties, investment properties, and active neighborhoods available on Mashvisor.com for a specific .

### HTTP Request

`GET http://api.mashvisor.com/v.1/summary/listing` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
city | Integer | | City name, ex: Las Vegas.

# Trends

## List Cities

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/trends/cities?state=CA&items=3")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/trends/cities?state=CA&items=3",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/trends/cities');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
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

	url := "https://api-build.mashvisor.com/v1.1/trends/cities?state=CA&items=3"

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
        "state": "CA",
        "cities": [
            {
                "city": "San Francisco",
                "state": "CA",
                "occupancy": "51.23301023",
                "total_listing": "8505",
                "occ_listing": "435736.75198064"
            },
            {
                "city": "Los Angeles",
                "state": "CA",
                "occupancy": "40.68916374",
                "total_listing": "8861",
                "occ_listing": "360546.67986470"
            },
            {
                "city": "Long Beach",
                "state": "CA",
                "occupancy": "44.20128261",
                "total_listing": "1685",
                "occ_listing": "74479.16119448"
            }
        ]
    }
}
```

This endpoint retrieves the cities has the biggest occupancy in a specific state. 

### HTTP Request

`GET http://api.mashvisor.com/v.1/trends/citites` 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
page | Integer | 1 | The page to return the content for. Valid values:1, ... etc.
items | Integer | 5 | The items to return the content for. Valid values: 10, ... etc.

## List Neighborhoods

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/trends/neighborhoods?state=IL&city=Chicago&items=3")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/trends/neighborhoods?state=IL&city=Chicago&items=3",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/trends/neighborhoods');
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

	url := "https://api-build.mashvisor.com/v1.1/trends/neighborhoods?state=IL&city=Chicago&items=3"

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

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String* | | State name, ex: NV.
city | String* | | city name, ex: Las Vegas.
page | Integer | 1 | The page to return the content for. Valid values:1, ... etc.
items | Integer | 5 | The items to return the content for. Valid values: 10, ... etc.
desc | Boolean | false | If it's true, it'll fetch the neighborhood description and single home values in the request response

# User

## Login via Gmail

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/login/gmail?url=www.mashvisor.com")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/login/gmail?url=www.mashvisor.com",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/login/gmail');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'url' => 'www.mashvisor.com'
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

	url := "https://api-build.mashvisor.com/v1/user/login/gmail?url=www.mashvisor.com"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint allows to login the user with Google accounts. 
It Redirect the user to the link and the backend will handle all the login then redirect the user back to the application with the secret token

### HTTP Request

`GET http://api.mashvisor.com/v1/user/login/gmail` 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
url | String | | The redirect url that the front end needs to redirect to when the login succeeds. the api will redirect the user back to the provided url after adding the following part to the link "&user_token={{JWT_TOKEN}}"

## Login

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "email=ahmadh%40mashvisor.com&password=myComplexPassword");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/login")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/login",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "email": "ahmadh@mashvisor.com",
    "password": "myComplexPassword"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/login');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'email' => 'ahmadh@mashvisor.com',
  'password' => 'myComplexPassword'
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

	url := "https://api-build.mashvisor.com/v1/user/login"

	payload := strings.NewReader("email=ahmadh%40mashvisor.com&password=myComplexPassword")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("postman-token", "3bf4d4dd-fb63-8750-e55d-ea2721155f87")

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
      "id": 579,
      "provider": "MASHVISOR",
      "email": "ahmadh@mashvisor.com",
      "user_role": [
        "Admin",
        "Agent"
      ]
    },
    "auth_token": "{{JWT_TOKEN}}"
  },
  "message": "Login succeeded"
}
```

This endpoint allows the user to login in Mashvisor via his/her email and password. 

### HTTP Request

`POST http://api.mashvisor.com/v1/user/login` 

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
email | String | | Registered email account
password | String | | Password

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/x-www-form-urlencoded | 

## Register

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "email=ahmadh%40mashvisor.com&password=myComplexPassword&appUrl=https%3A%2F%2Fmashvisor.com%2F&gacid=someGCID");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/register")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/register",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "email": "ahmadh@mashvisor.com",
    "password": "myComplexPassword",
    "appUrl": "https://mashvisor.com/",
    "gacid": "someGCID"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/register');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'email' => 'ahmadh@mashvisor.com',
  'password' => 'myComplexPassword',
  'appUrl' => 'https://mashvisor.com/',
  'gacid' => 'someGCID'
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

	url := "https://api-build.mashvisor.com/v1/user/register"

	payload := strings.NewReader("email=ahmadh%40mashvisor.com&password=myComplexPassword&appUrl=https%3A%2F%2Fmashvisor.com%2F&gacid=someGCID")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
        "auth_token": "{JWT_TOKEN}",
        "user": {
            "id": 5756,
            "provider": "MASHVISOR",
            "email": "ahmadh@mashvisor.com",
            "user_role": []
        },
        "login": 0
    },
    "message": "User registration succeeded, Please check your email to confirm your registration"
}
```

This endpoint allows the user to signup in Mashvisor via his/her email and password. 

### HTTP Request

`POST http://api.mashvisor.com/v1/user/register` 

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
email | String | | Unique & Valid email Address
password | String | | Password that includes at least (1digit, 1 capital + 1 small letter, 1 special "!@#$%" character
gacid | String | | Google analytics client id
password | String | | encodeURI: The page url you want to redirect the user back to it to activate the account, the activation appUrl will be combined with the following pattern "user/{userId}/activate/{activation-token}"

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/x-www-form-urlencoded | 

## Get Profile

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/profile")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/profile",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/profile');
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
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1/user/579/profile"

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
        "id": 579,
        "provider": "MASHVISOR",
        "email": "ahmadh@mashvisor.com",
        "user_profile": {
            "first_name": "Ahmed",
            "last_name": "Hashlamon",
            "city": "San Diego",
            "state": "CA",
            "address": null,
            "mobile_number": "",
            "zip_code": null,
            "user_profile_meta": [
                {
                    "city_searched_for": "Chicago, IL",
                    "created_at": "2016-04-28 12:24:49.0",
                    "updated_at": null
                },
                {
                    "Budget": "$500,000 - $780,000",
                    "created_at": "2016-08-07 20:10:44.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "financing": "cash",
                    "created_at": "2016-08-07 20:10:44.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "real_estate_background": "Firm/Group Investors",
                    "created_at": "2016-08-07 20:10:44.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "interested_in": "Analyzing an Airbnb and a traditional investment",
                    "created_at": "2016-08-07 20:10:44.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "google_email": "ahmadh@mashvisor.com",
                    "created_at": "2016-08-07 20:10:44.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "blog_email": "true",
                    "created_at": "2016-08-07 20:11:15.0",
                    "updated_at": "2016-08-07 20:11:34.0"
                },
                {
                    "marketing_information": "true",
                    "created_at": "2016-08-07 20:11:15.0",
                    "updated_at": "2016-08-07 20:11:34.0"
                },
                {
                    "monthly_news_letter": "true",
                    "created_at": "2016-08-07 20:11:15.0",
                    "updated_at": "2016-08-07 20:11:34.0"
                },
                {
                    "product_feature_update": "true",
                    "created_at": "2016-08-07 20:11:15.0",
                    "updated_at": "2016-08-07 20:11:34.0"
                },
                {
                    "city_alerts": "true",
                    "created_at": "2016-08-07 20:11:15.0",
                    "updated_at": "2016-08-07 20:11:34.0"
                },
                {
                    "profile_image_link": "https://bc9f40b414b80f1ce90f-212b46b1c531b50ebb00763170d70160.ssl.cf5.rackcdn.com/UserImages/16296/16296_profile.png",
                    "created_at": "2017-04-10 13:41:55.0",
                    "updated_at": "2017-04-26 08:01:39.0"
                },
                {
                    "pre_approved_for_a_mortgage": "Yes",
                    "created_at": "2017-04-14 11:09:07.0",
                    "updated_at": "2017-04-14 11:09:07.0"
                },
                {
                    "looking_to_buy_duration": "1-2 Months",
                    "created_at": "2017-04-14 11:09:07.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "property_type": "Best investment opportunity",
                    "created_at": "2017-04-14 11:09:08.0",
                    "updated_at": "2017-04-14 11:09:08.0"
                },
                {
                    "comments": "Min 8% CoC, target 15% CoC",
                    "created_at": "2017-04-14 11:09:09.0",
                    "updated_at": "2017-04-14 11:09:09.0"
                },
                {
                    "featured_agent_zip_code": "32097",
                    "created_at": "2017-05-07 08:12:32.0",
                    "updated_at": null
                },
                {
                    "purchasing_property": "I am an agent",
                    "created_at": "2017-05-07 14:27:30.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "agency_name": "REALHome Services and Solutions",
                    "created_at": "2017-05-07 14:27:30.0",
                    "updated_at": "2017-06-19 08:03:33.0"
                },
                {
                    "agency_image_link": "https://bc9f40b414b80f1ce90f-212b46b1c531b50ebb00763170d70160.ssl.cf5.rackcdn.com/UserImages/16296/16296_agency.png",
                    "created_at": "2017-05-09 00:43:44.0",
                    "updated_at": "2017-05-12 22:33:50.0"
                },
                {
                    "credit_card_expiration": "2/2022",
                    "created_at": "2017-05-24 12:35:26.0",
                    "updated_at": "2017-06-19 08:04:34.0"
                },
                {
                    "sessions_count": "24",
                    "created_at": "2017-07-11 12:51:11.0",
                    "updated_at": null
                },
                {
                    "company": "Mashvisor Inc",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "position": "Software Enginner",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "gender": "Male",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "Facebook": "https://www.facebook.com/ahmad.hashlamoun21",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "GooglePlus": "https://plus.google.com/u/1/105012620630354484044",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "LinkedIn": "https://www.linkedin.com/in/peterabu",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "age": "25",
                    "created_at": "2017-07-12 12:09:14.0",
                    "updated_at": "2017-07-12 12:09:14.0"
                },
                {
                    "financing_approach": "Paying Cash",
                    "created_at": "2017-06-08 19:24:19.0",
                    "updated_at": null
                },
                {
                    "comments": "Frisco, TX",
                    "created_at": "2017-06-19 08:03:33.0",
                    "updated_at": null
                },
                {
                    "schedule_time": "22-11-2017",
                    "created_at": "2017-07-02 14:30:17.0",
                    "updated_at": null
                },
                {
                    "last_activity": "2017-08-08 12:44:10",
                    "created_at": "2017-07-02 14:30:25.0",
                    "updated_at": "Tue Aug 08 12:44:10 UTC 2017"
                },
                {
                    "Hubspot_id": "363",
                    "created_at": "2017-07-13 07:50:16.0",
                    "updated_at": null
                },
                {
                    "agent_feedback_popup_lastseen": "2017-08-07 12:01:38",
                    "created_at": "2017-07-17 15:09:05.0",
                    "updated_at": "2017-08-07 12:01:39.0"
                },
                {
                    "agent_popup_views_count": "2",
                    "created_at": "2017-07-17 15:09:05.0",
                    "updated_at": "2017-08-07 12:01:39.0"
                },
                {
                    "5feedback_pop_up_closed": "true",
                    "created_at": "2017-07-23 08:35:08.0",
                    "updated_at": null
                },
                {
                    "10feedback_pop_up_closed": "true",
                    "created_at": "2017-07-23 08:36:18.0",
                    "updated_at": null
                },
                {
                    "20feedback_pop_up_closed": "true",
                    "created_at": "2017-07-23 08:37:03.0",
                    "updated_at": null
                },
                {
                    "cities_interested_in": [
                        "Sunnyvale, CA",
                        "Boulder, CA",
                        "Boulder, NY",
                        "Boulder, KY",
                        "San Jose, CA",
                        "Las Vegas, NV"
                    ]
                }
            ],
            "user_role": [
                "Agent"
            ],
            "agent_featured_location": [
                {
                    "id": 2,
                    "agent_id": 579,
                    "city": "San Diego",
                    "state": "CA",
                    "zipcode": null
                }
            ],
            "created_at": "2015-11-15 13:34:05.0"
        },
        "user_saved_properties": 64
    },
    "message": "Fetched user profile data successfully"
}
```

This endpoint retrieves the user profile info. 

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/profile` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

## Update Profile

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "first_name=Ahmad");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/profile")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/profile",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "first_name": "Ahmad"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/profile');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'first_name' => 'Ahmad'
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

	url := "https://api-build.mashvisor.com/v1/user/579/profile"

	payload := strings.NewReader("first_name=Ahmad")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
    "content": null,
    "message": "User profile saved successfully"
}
```

This endpoint updates the user profile info. 

### HTTP Request

`POST http://api.mashvisor.com/v1/user/{user_id}/profile` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} |
Content-Type | application/x-www-form-urlencoded |

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
first_name | String | | User's first name
last_name | String | | User's last name
mobile_number | String | | User's mobile number
address | String | | The address of the user
zip_code | String | | Zip Code
city | String | | User's city
state | String | | User's state

## Update Profile Meta

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "mkeys=user_feedback_rate&mkeys=user_feedback_question&mvalues=3&mvalues=my%20first%20question");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/profile/meta")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/profile/meta",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "mkeys": [
      "user_feedback_rate",
      "user_feedback_question"
    ],
    "mvalues": [
      "3",
      "my first question"
    ]
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/profile/meta');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'mkeys' => array(
    'user_feedback_rate',
    'user_feedback_question'
  ),
  'mvalues' => array(
    '3',
    'my first question'
  )
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

	url := "https://api-build.mashvisor.com/v1/user/579/profile/meta"

	payload := strings.NewReader("mkeys=user_feedback_rate&mkeys=user_feedback_question&mvalues=3&mvalues=my%20first%20question")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
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
  "content": null,
  "message": "User profile saved successfully"
}
```

This endpoint updates the user profile info. 

### HTTP Request

`POST http://api.mashvisor.com/v1/user/{user_id}/profile/meta` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} |
Content-Type | application/x-www-form-urlencoded |

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
mkeys | String[] | | meta keys
mvalues | String[] | | meta values

### Available Metas

Key | Value 
--------- | ------- 
blog_email | true / false | 
marketing_information | true / false 
monthly_news_letter | true / false 
product_feature_update | true / false 
cities_interested_in | 	Santa Clara, CA: city name followed with comma and state name. For multiple cities, split them by ";" semicolon For example: Boulder, CO;Chicago, IL;Santa Clara,CA 
city_alerts | true / false
Budget | true / false
marketing_information | Under $100,000, $100,000 - $200,000, $200,000 - $300,000, $300,000 - $400,000, $400,000 - $500,000, $500,000 - $750,000, $750,000 - $1,000,000, Over $1,000,000
financing | Mortgage / Cash 
interested_in | Finding investment properties, Analyzing an Airbnb investment, Analyzing a traditional investment, Analyzing an Airbnb and a traditional investment, Still trying to figure it out 
real_estate_background | First-TimeInvestor, Part-TimeInvestor, Full-TimeInvestor, Agent/Broker, Firm/GroupInvestors, Wholesaler, Other 
looking_to_buy_duration | Less than a Month, 1-2 Months, 3-5 Months, 6-12 Months, When I find the right property 
purchasing_property | I currently have an agent, I'm looking for an agent, I would consider replacing my agent, I am an agent 
agency_name | 
agency_image_link | 
profile_image_link | 
match_with_agent | true / false 
connect_with_agent | true / false 
agent_feedback_rate | 
agent_feedback_comment | 

## Logout

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/logout")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/logout",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/logout');
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
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1/user/logout"

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
    "content": null,
    "message": "Logout succeeded"
}
```

This endpoint logouts the user from Mashvisor.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/logout` 

## Activate Registeration

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/%7Buser_id%7D/activate/%7Btoken%7D")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/%7Buser_id%7D/activate/%7Btoken%7D",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/%7Buser_id%7D/activate/%7Btoken%7D');
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
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1/user/%7Buser_id%7D/activate/%7Btoken%7D"

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
    "content": null,
    "message": "User account activated successfully"
}
```

This endpoint logouts the user from Mashvisor.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/activate/{token}` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.
token | String | | The Mashvisor generated token to confirm user subscription.

## Update Password

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "password=newPassword&oldPassword=myComplexPassword");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/password/update")
  .post(body)
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/password/update",
  "method": "POST",
  "headers": {
    "authorization": "Bearer {JWT_TOKEN}",
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "password": "newPassword",
    "oldPassword": "myComplexPassword"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/password/update');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded',
  'authorization' => 'Bearer {JWT_TOKEN}'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'password' => 'newPassword',
  'oldPassword' => 'myComplexPassword'
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

	url := "https://api-build.mashvisor.com/v1/user/password/update"

	payload := strings.NewReader("password=newPassword&oldPassword=myComplexPassword")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
    "content": null,
    "message": "Your password updated successfully."
}
```

This endpoint logouts the user from Mashvisor.

### HTTP Request

`POST https://api.mashvisor.com/v1/user/password/update` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} |
Content-Type | application/x-www-form-urlencoded |

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
password | String | | new password
oldPassword | String | | old password

## Reset Password

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "token=%7BRESET_TOKEN%7D&password=newPassword");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/password/reset")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/password/reset",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "token": "{RESET_TOKEN}",
    "password": "newPassword"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/password/reset');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'token' => '{RESET_TOKEN}',
  'password' => 'newPassword'
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

	url := "https://api-build.mashvisor.com/v1/user/password/reset"

	payload := strings.NewReader("token=%7BRESET_TOKEN%7D&password=newPassword")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
    "content": null,
    "message": "User Reset Password succeeded"
}
```

This endpoint allows the user who forget his password to reset his/her password.

### HTTP Request

`POST https://api.mashvisor.com/v1/user/password/reset` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/x-www-form-urlencoded |

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
token | String | | User Password reset token
password | String | | Password that includes at least (1digit, 1 capital + 1 small letter, 1 special "!@#$%" character

## Reset Password Request

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "email=ahmadh%40mashvisor.com&appUrl=https%3A%2F%2Fwww.mashvisor.com%2Fpassword-reset");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/password/reset/request")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/password/reset/request",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded"
  },
  "data": {
    "email": "ahmadh@mashvisor.com",
    "appUrl": "https://www.mashvisor.com/password-reset"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/password/reset/request');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'email' => 'ahmadh@mashvisor.com',
  'appUrl' => 'https://www.mashvisor.com/password-reset'
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

	url := "https://api-build.mashvisor.com/v1/user/password/reset/request"

	payload := strings.NewReader("email=ahmadh%40mashvisor.com&appUrl=https%3A%2F%2Fwww.mashvisor.com%2Fpassword-reset")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")

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
    "content": null,
    "message": "Reset password request succeeded, check your email for reset password link"
}
```

This endpoint allows the user who forget his password to reset it by sending him/her a link to his email for the password reset page along with a password reset token.

### HTTP Request

`POST https://api.mashvisor.com/v1/user/password/reset/request` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/x-www-form-urlencoded |

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
email | String | | The Mashvisor registereation email
appUrl | String | | Password reset page, ex: https://www.mashvisor.com/password-reset

## Check Subscription

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/check/subscription?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/check/subscription?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/check/subscription');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
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

	url := "https://api-build.mashvisor.com/v1/user/579/check/subscription?_t=meowmeowmeow"

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
        "results": [
            {
                "start_date_formatted": "06/07/2017",
                "start_date": "2017-06-07 12:26:48.0",
                "end_date_formatted": "06/07/2018",
                "end_date": "2018-06-07 12:26:48.0",
                "valid": true,
                "plan": "MASHVISOR_TOP_AGENT",
                "plan_recurring": "ANNUAL",
                "customer_id": "cus_AneYgmrIO3ia2I",
                "subscription_amount": 4500,
                "payment_method": "stripe",
                "transition_id": null
            }
        ]
    },
    "message": "Fetched user subscription profile successfully"
}
```

This endpoint retrieves the current user subscription.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/check/subscription` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

## Save Favorite Proeprty

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "property=1&type=Investment");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/favorite/property/save")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("cache-control", "no-cache")
  .addHeader("postman-token", "13f3d6b2-42a2-9759-dac2-1eb364b71547")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/favorite/property/save",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "property": "1",
    "type": "Investment"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/favorite/property/save');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'property' => '1',
  'type' => 'Investment'
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

	url := "https://api-build.mashvisor.com/v1/user/favorite/property/save"

	payload := strings.NewReader("property=1&type=Investment")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
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
  "content": null,
  "message": "User fav property saved successfully."
}

{
  "status": "success",
  "content": null,
  "message": "User fav property unsaved successfully."
}
```

This endpoint saves/deletes the user favorite property in the database.

### HTTP Request

`POST http://api.mashvisor.com/v1/user/favorite/property/save` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state belongs to the property.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
property | Long | | The Mashvisor property id..
type | String | | Airbnb, Traditional, or Investment.

## Get User Permissions

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/permissions?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/permissions?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/permissions');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
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

	url := "https://api-build.mashvisor.com/v1/user/579/permissions?_t=meowmeowmeow"

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
    "user_id": 113,
    "subscription_plan": "MASHVISOR_BASIC",
    "valid_plan": true,
    "results": [
      {
        "resource": "SEARCH::Investment_Property",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "SEARCH::Airbnb_Property",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "SEARCH::Traditional_Property",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "EXPORT::Investment_Property",
        "access": "true",
        "resource_limit": 5
      },
      {
        "resource": "EXPORT::Airbnb_Property",
        "access": "true",
        "resource_limit": 5
      },
      {
        "resource": "EXPORT::Traditional_Property",
        "access": "true",
        "resource_limit": 5
      },
      {
        "resource": "HEATMAP::Listing_Price",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Airbnb_CoC",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Traditional_Coc",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Occupancy_Rate",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Airbnb_Rental",
        "access": "true",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Traditional_Rental",
        "access": "true",
        "resource_limit": 0
      }
    ]
  },
  "message": "Fetched user permissions successfully"
}
```

> The above command returns JSON structured like this if the token is invalid or fake:

```json
{
  "status": "success",
  "content": {
    "results": [
      {
        "resource": "SEARCH::Investment_Property",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "SEARCH::Airbnb_Property",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "SEARCH::Traditional_Property",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "EXPORT::Investment_Property",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "EXPORT::Airbnb_Property",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "EXPORT::Traditional_Property",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Listing_Price",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Airbnb_CoC",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Traditional_Coc",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Occupancy_Rate",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Airbnb_Rental",
        "access": "false",
        "resource_limit": 0
      },
      {
        "resource": "HEATMAP::Traditional_Rental",
        "access": "false",
        "resource_limit": 0
      }
    ]
  },
  "message": "Fetched user permissions successfully"
}
```

This endpoint retrieves the users permissions.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/permissions` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

## Get Transactions

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/transactions?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/transactions?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/transactions');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
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

	url := "https://api-build.mashvisor.com/v1/user/579/transactions?_t=meowmeowmeow"

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
    "user_id": 113,
    "total_results": 3,
    "charges": [
      {
        "id": "ch_17QEmGGYREWu4WN3CprsK75i",
        "user_subscription_id": 102,
        "created_at": "Jan 06,2016",
        "amount": 44.99,
        "amount_refunded": 0,
        "refunded": false,
        "currency": "usd",
        "customer": null,
        "invoice": null,
        "paid": true,
        "plan": "BASIC / ONCE",
        "method": "MasterCard FINISHED IN 4444"
      },
      {
        "id": "ch_17QEybGYREWu4WN3DRJSJjEf",
        "user_subscription_id": 103,
        "created_at": "Jan 06,2016",
        "amount": 44.99,
        "amount_refunded": 0,
        "refunded": false,
        "currency": "usd",
        "customer": null,
        "invoice": null,
        "paid": true,
        "plan": "BASIC / ONCE",
        "method": "MasterCard FINISHED IN 4444"
      },
      {
        "id": "ch_17QFEjGYREWu4WN3g5x3yIL4",
        "user_subscription_id": 104,
        "created_at": "Jan 06,2016",
        "amount": 44.99,
        "amount_refunded": 0,
        "refunded": false,
        "currency": "usd",
        "customer": null,
        "invoice": null,
        "paid": true,
        "plan": "BASIC / ONCE",
        "method": "Visa FINISHED IN 4242"
      }
    ]
  },
  "message": "Fetched user charges successfully"
}
```

This endpoint retrieves the users transactions made on Stripe.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/transactions` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
year | Integer | | Filter to fetch the transctions since. e.g: 2017

## Save Proeprty Notes

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "property=1&tags=Bookings&state=CA");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/favorite/property/notes")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/favorite/property/notes",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "property": "1",
    "tags": "Bookings",
    "state": "CA"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/favorite/property/notes');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'property' => '1',
  'tags' => 'Bookings',
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1/user/favorite/property/notes"

	payload := strings.NewReader("property=1&tags=Bookings&state=CA")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
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
    "id": 3,
    "user_id": 351,
    "property_id": 13837,
    "rating": 1,
    "tenant_occupied": true,
    "property_status": "No Longer Interested",
    "tags": "Invetsment, Airbnb",
    "notes": null
  },
  "message": "User property's notes saved successfully."
}
```

This endpoint saves the user property notes for a specific property.

### HTTP Request

`POST http://api.mashvisor.com/v1/user/property/notes` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 
Content-Type | application/x-www-form-urlencoded | 

### FORM Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
property | Long | | 	Mashvisor Investment property id, e.g: 34804
rating | Integer | | 1 to 5, 5 is the best rating
tenant | Boolean | | is the tenant occupied or not
status | String | | 
tags | String | | Any tags from the user
notes | String | | 	Any string from the user
state | String | | The state that the property belongs to.

## Get Payment Details

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/payment/details?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/payment/details?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/payment/details');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
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

	url := "https://api-build.mashvisor.com/v1/user/579/payment/details?_t=meowmeowmeow"

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
    "card_info": [
      {
        "name": "Ahmad Hashlamoun",
        "plan_recurring": "MONTHLY",
        "last_four": "4444",
        "brand": "MasterCard",
        "expires_at": "12/2030"
      }
    ]
  },
  "message": "User payment details fetched successfully."
}
```

This endpoint retrieves the user's payment info (Card info).

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/payment/details` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

## Update Payment Details

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "name=Ahmad%20Hashlamoun&credit_card=5555555555554444&exp_month=3&exp_year=2030&cvc=2222");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/payment/details")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/payment/details",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "name": "Ahmad Hashlamoun",
    "credit_card": "5555555555554444",
    "exp_month": "3",
    "exp_year": "2030",
    "cvc": "2222"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/payment/details');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'name' => 'Ahmad Hashlamoun',
  'credit_card' => '5555555555554444',
  'exp_month' => '3',
  'exp_year' => '2030',
  'cvc' => '2222'
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

	url := "https://api-build.mashvisor.com/v1/user/579/payment/details"

	payload := strings.NewReader("name=Ahmad%20Hashlamoun&credit_card=5555555555554444&exp_month=3&exp_year=2030&cvc=2222")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
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
    "card_info": [
      {
        "name": "Ahmad Hashlamoun",
        "plan_recurring": "MONTHLY",
        "last_four": "4444",
        "brand": "MasterCard",
        "expires_at": "12/2030"
      }
    ]
  },
  "message": "User credit card updated successfully."
}
```

This endpoint updates the user's credit card info based on params you send.

### HTTP Request

`POST http://api.mashvisor.com/v1/user/{user_id}/payment/details` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
name | String | | Credit card holder name
credit_card | Integer | | Credit card number, e.g: 5555555555554444
exp_month | String | | Credit card expires on month, e.g: 3
exp_year | Integer | | Credit card expires on year, e.g: 2030
cvc | Integer | | Credit card CVC number, e.g: 2222

## Export Invoice

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/invoice/export?_xt=%7Bbase64%20JWT_TOKEN%7D&plan_id=1058&charge_id=ch_188tXXGYREWu4XN3ESfXXXX&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/invoice/export?_xt=%7Bbase64%20JWT_TOKEN%7D&plan_id=1058&charge_id=ch_188tXXGYREWu4XN3ESfXXXX&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/invoice/export');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  '_xt' => '{base64 JWT_TOKEN}',
  'plan_id' => '1058',
  'charge_id' => 'ch_188tXXGYREWu4XN3ESfXXXX',
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

	url := "https://api-build.mashvisor.com/v1/user/579/invoice/export?_xt=%7Bbase64%20JWT_TOKEN%7D&plan_id=1058&charge_id=ch_188tXXGYREWu4XN3ESfXXXX&_t=meowmeowmeow"

	req, _ := http.NewRequest("GET", url, nil)

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```

This endpoint exports a pdf file of the transaction (Stripe's charge) specified.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/invoice/export` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
charge_id | Integer | | Stripe's charge id card number, e.g: ch_188tXXGYREWu4XN3ESfXXXX
plan_id | String | | The User subscription plan id, e.g: 1050
_xt | String | | Base64 encoded value of the user JWT_TOKEN

## Print Invoice

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/invoice/print?_xt=%7Bbase64%20JWT_TOKEN%7D&plan_id=1058&charge_id=ch_188tXXGYREWu4XN3ESfXXXX&_t=meowmeowmeow")
  .get()
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/invoice/print?_xt=%7Bbase64%20JWT_TOKEN%7D&plan_id=1058&charge_id=ch_188tXXGYREWu4XN3ESfXXXX&_t=meowmeowmeow",
  "method": "GET"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/invoice/print');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  '_xt' => '{base64 JWT_TOKEN}',
  'plan_id' => '1058',
  'charge_id' => 'ch_188tXXGYREWu4XN3ESfXXXX',
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

	url := "https://api-build.mashvisor.com/v1/user/579/invoice/print?_xt=%7Bbase64%20JWT_TOKEN%7D&plan_id=1058&charge_id=ch_188tXXGYREWu4XN3ESfXXXX&_t=meowmeowmeow"

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
      "invoice_html":
        "raw html data"
    },
    "message": "Fetched user invoice successfully"
}
```

This endpoint prints a pdf file of the transaction (Stripe's charge) specified.

### HTTP Request

`GET http://api.mashvisor.com/v1/user/{user_id}/invoice/print` 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
charge_id | Integer | | Stripe's charge id card number, e.g: ch_188tXXGYREWu4XN3ESfXXXX
plan_id | String | | The User subscription plan id, e.g: 1050
_xt | String | | Base64 encoded value of the user JWT_TOKEN

## Save Cancellation Feedback

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "option=my%20first%20option&notes=my%20notes");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/account/feedback")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/account/feedback",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "option": "my first option",
    "notes": "my notes"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/account/feedback');
$request->setMethod(HTTP_METH_POST);

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'option' => 'my first option',
  'notes' => 'my notes'
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

	url := "https://api-build.mashvisor.com/v1/user/account/feedback"

	payload := strings.NewReader("option=my%20first%20option&notes=my%20notes")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
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
    "status":"success",
    "content":null,
    "message":"Cancellation FeedBack is registered"
}
```

This endpoint saves the user's cancellation feedback.

### HTTP Request

`POST http://api.mashvisor.com/v1/user/account/feedback` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 
Content-Type | application/x-www-form-urlencoded | 

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
option | String | | User cancellation feedback option
notes | String | | User Cancellation feedback notes

## Check Favorite Properties

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/favorite/properties?state=CA&properties=2901%2C%20263817%2C%20263995%2C%20265546%2C%20263852&type=Investment")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/favorite/properties?state=CA&properties=2901%2C%20263817%2C%20263995%2C%20265546%2C%20263852&type=Investment",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/favorite/properties');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  'state' => 'CA',
  'properties' => '2901, 263817, 263995, 265546, 263852',
  'type' => 'Investment'
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

	url := "https://api-build.mashvisor.com/v1/user/favorite/properties?state=CA&properties=2901%2C%20263817%2C%20263995%2C%20265546%2C%20263852&type=Investment"

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
    "2901": true,
    "263817": true,
    "263852": false,
    "263995": false,
    "265546": false
  },
  "message": "User fav property fetched successfully."
}
```

This endpoint retrieves the received properties status weather the user saved them or not

### HTTP Request

`GET https://api.mashvisor.com/v1/user/favorite/properties` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
state | String | | The state the properties belongs to
properties | String | | properties=2901, 263817, 263995, 265546, 263852
type | String | | Investment, Airbnb, Traditional

## Validate Phone Number

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/validate/phoneNumber?_t=meowmeowmeow&phone_number=%2016502520530")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/validate/phoneNumber?_t=meowmeowmeow&phone_number=%2016502520530",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/validate/phoneNumber');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow',
  'phone_number' => ' 16502520530'
));

$request->setHeaders(array(
  'postman-token' => '7fe7dd35-87fc-a703-18c0-df379d348dad'
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

	url := "https://api-build.mashvisor.com/v1/user/validate/phoneNumber?_t=meowmeowmeow&phone_number=%2016502520530"

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
    "caller_name": "YOU TUBE",
    "phone_number": "+16502530000",
    "national_format": "(650) 253-0000",
    "carrier": null,
    "url": "https://lookups.twilio.com/v1/PhoneNumbers/+16502530000?Type=caller-name",
    "caller_type": "BUSINESS",
    "error_code": null
  },
  "message": "The requested PhoneNumbers 6502530000 was found"
}
```

This endpoint validates the user phone number provided by him from Twilio service and returns the user phone info.

### HTTP Request

`GET https://api.mashvisor.com/v1/user/validate/phoneNumber` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Query Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
phone_number | String | | The user's phone number, ex: 6502530000

## Save Image

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"image\":\"{Base64 image's payload}\",\n\t\"suffix\":\"profile\"\n}");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/user/579/images?_t=meowmeowmeow")
  .post(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/user/579/images?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "content-type": "application/json",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "processData": false,
  "data": "{\n\t\"image\":\"{Base64 image's payload}\",\n\t\"suffix\":\"profile\"\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/user/579/images');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/json'
));

$request->setBody('{
	"image":"{Base64 image's payload}",
	"suffix":"profile"
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

	url := "https://api-build.mashvisor.com/v1.1/user/579/images?_t=meowmeowmeow"

	payload := strings.NewReader("{\n\t\"image\":\"{Base64 image's payload}\",\n\t\"suffix\":\"profile\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")
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
  "content": "https://bc9f40b414b80XXXXXXX-212b46bXX31b50ebb00763XXXX70160.ssl.cf5.rackcdn.com/UserImages/579/579_profile.png"
}
```

This endpoint saves the user headshot or agency images in Mashvisor's Rackspace storage space.

### HTTP Request

`POST https://api.mashvisor.com/v1.1/user/{user_id}/images` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/json | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
image | String | | Base64 image's payload
suffix | String | profile | "profile" or "agency"

## Delete Image

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\t\"suffix\":\"profile\"\n}");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1.1/user/579/images/delete?_t=meowmeowmeow")
  .post(body)
  .addHeader("content-type", "application/json")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1.1/user/579/images/delete?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "content-type": "application/json",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "processData": false,
  "data": "{\n\t\"suffix\":\"profile\"\n}"
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1.1/user/579/images/delete');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/json'
));

$request->setBody('{
	"suffix":"profile"
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

	url := "https://api-build.mashvisor.com/v1.1/user/579/images/delete?_t=meowmeowmeow"

	payload := strings.NewReader("{\n\t\"suffix\":\"profile\"\n}")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/json")
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
  "content": "The file 579_agency.png have been deleted successfully."
}
```

This endpoint deletes the user headshot or agency images in Mashvisor's Rackspace storage space.

### HTTP Request

`POST https://api.mashvisor.com/v1.1/user/{user_id}/images/delete` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/json | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Body Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
suffix | String | profile | "profile" or "agency"

## Save Agent Featured Location

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "city=San%20Francisco&state=CA");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/agent/area?_t=meowmeowmeow")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .addHeader("cache-control", "no-cache")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/agent/area?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "city": "San Francisco",
    "state": "CA"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/agent/area');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'city' => 'San Francisco',
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1/user/579/agent/area?_t=meowmeowmeow"

	payload := strings.NewReader("city=San%20Francisco&state=CA")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
	req.Header.Add("authorization", "Bearer {JWT_TOKEN}")
	req.Header.Add("cache-control", "no-cache")
	req.Header.Add("postman-token", "0b662f75-510b-43ed-8c2d-007945e442b7")

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
    "id": 3,
    "agent_id": 579,
    "city": null,
    "state": null,
    "zipcode": 60026
  },
  "message": "Agent featured location saved successfully."
}
```

This endpoint saves the AGENT featured zip code or city, state in the AgentCity table.

### HTTP Request

`POST https://api.mashvisor.com/v1/user/{user_id}/agent/area` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/x-www-form-urlencoded | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String |  | The agent's city to be shown on the properties agents card along with the state
state | String |  | The agent's state to be shown on the properties agents card along with the city
zip_code | String |  | The agent's zip code to be shown on the properties agents card

## Delete Agent Featured Location

```java
OkHttpClient client = new OkHttpClient();

MediaType mediaType = MediaType.parse("application/x-www-form-urlencoded");
RequestBody body = RequestBody.create(mediaType, "city=San%20Francisco&state=CA");
Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/agent/area/delete?_t=meowmeowmeow")
  .post(body)
  .addHeader("content-type", "application/x-www-form-urlencoded")
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/agent/area/delete?_t=meowmeowmeow",
  "method": "POST",
  "headers": {
    "content-type": "application/x-www-form-urlencoded",
    "authorization": "Bearer {JWT_TOKEN}"
  },
  "data": {
    "city": "San Francisco",
    "state": "CA"
  }
}

$.ajax(settings).done(function (response) {
  console.log(response);
});
```

```php
<?php

$request = new HttpRequest();
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/agent/area/delete');
$request->setMethod(HTTP_METH_POST);

$request->setQueryData(array(
  '_t' => 'meowmeowmeow'
));

$request->setHeaders(array(
  'authorization' => 'Bearer {JWT_TOKEN}',
  'content-type' => 'application/x-www-form-urlencoded'
));

$request->setContentType('application/x-www-form-urlencoded');
$request->setPostFields(array(
  'city' => 'San Francisco',
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
	"strings"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-build.mashvisor.com/v1/user/579/agent/area/delete?_t=meowmeowmeow"

	payload := strings.NewReader("city=San%20Francisco&state=CA")

	req, _ := http.NewRequest("POST", url, payload)

	req.Header.Add("content-type", "application/x-www-form-urlencoded")
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
  "content": null,
  "message": "Agent featured location deleted successfully."
}
```

This endpoint deletes the AGENT featured zip code or city, state in the AgentCity table.

### HTTP Request

`POST https://api.mashvisor.com/v1/user/{user_id}/agent/area/delete` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Content-Type | application/x-www-form-urlencoded | 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.

### Form Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
city | String |  | The agent's city to be deleted on the properties agents card along with the state
state | String |  | The agent's state to be deleted on the properties agents card along with the city
zip_code | String |  | The agent's zip code to be deleted on the properties agents card

## Refresh JWT Token

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/refresh/token?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/refresh/token?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/refresh/token');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
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

	url := "https://api-build.mashvisor.com/v1/user/579/refresh/token?_t=meowmeowmeow"

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
    "auth_token": "{{JWT_TOKEN}}",
    "token_expires_at": 1496672539000
  },
  "message": "Refresh token succeeded"
}
```

This endpoint refreshs the user's JWT token and its info.

### HTTP Request

`GET https://api.mashvisor.com/v1/user/{user_id}/refresh/token` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.


## Verify Feedback Pop-up

```java
OkHttpClient client = new OkHttpClient();

Request request = new Request.Builder()
  .url("https://api-build.mashvisor.com/v1/user/579/verify/feedback?_t=meowmeowmeow")
  .get()
  .addHeader("authorization", "Bearer {JWT_TOKEN}")
  .build();

Response response = client.newCall(request).execute();
```

```javascript
var settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-build.mashvisor.com/v1/user/579/verify/feedback?_t=meowmeowmeow",
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
$request->setUrl('https://api-build.mashvisor.com/v1/user/579/verify/feedback');
$request->setMethod(HTTP_METH_GET);

$request->setQueryData(array(
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

	url := "https://api-build.mashvisor.com/v1/user/579/verify/feedback?_t=meowmeowmeow"

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
        "show_popup": true
    },
    "message": "User has no previous sessions."
}
//
{
    "status": "success",
    "content": {
        "show_popup": false
    },
    "message": "User has already filled the agent feedback survey"
}
//
{
    "status": "success",
    "content": {
        "show_popup": true
    },
    "message": "User has previous sessions."
}
//
{
    "status": "success",
    "content": {
        "show_popup": false
    },
    "message": "User has already filled the feedback survey"
}
```

This endpoint verifies to show the user feedback pop up or not.

### HTTP Request

`GET https://api.mashvisor.com/v1/user/{user_id}/verify/feedback` 

### Request Headers

Parameter | Value | Default 
--------- | ------- | ------- 
Authorization | User Authentication JWT Token, ex:Bearer {JWT_TOKEN} | 

### Path Parameters

Parameter | Value | Default | Description
--------- | ------- | ------- | -----------
user_id | Long | | The Mashvisor id of the registered user.
