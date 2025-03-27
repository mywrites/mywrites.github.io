---
layout: default
title: "Tutorial"
category: "APIs"
---
An API Reference Guide explains how an API works, which enables developers to properly use the API. The guide provides an example format of requests, responses, and response codes. This guide might also include an explanation of parameters, error handling, rate limiting, versioning, and schemas.

**NOTE**
There is the **Company** database that includes the **Users**, **Workstations**, **Managers**, and **Human Resources** tables. In this **Reference (Tutorial)**, you will primarily use the API to interact with the **Users** table in the **Company** database. For example purposes, there are also several "pseudo" websites. These sites, such as **www.mycompany.com**, do not appear as clickable links.

## Authentication
There are common authentication methods or ways to ensure the app or website, for example, is allowed to request data:

* API Key
  * You typically get the API key, itself, from the API site you are attempting to access. As a prerequisite, you might have to access the site and create an account before you can generate this key. The API key might be an alphanumeric string of approximately 40 characters, is commonly included in the **Authorization Header** of an API request (discussed further below), and can be used to authenticate and gain access to an API. API keys commonly are permanent. Read **Samples** for a detailed example and explanation of API key use.
* Bearer Token
  * You typically get the bearer token, itself, from the API site you are attempting to access. As a prerequisite, you might have to access the site and create an account before you can generate this token. The token might be an alphanumeric string of approximately 40 characters, is commonly included in the **Authorization Header** of an API request (discussed further below), and can be used to authenticate and gain access to an API. Bearer tokens are considered more secure than API keys but are usually temporary.
* Auth/OAuth2
  * Open Authorization (OAuth) provides permission for one app to access another app without providing login credentials; instead, the destination app might display a message indicating, for example, *Sign in with Google*. OAuth enables permission for access without, in this case, sharing your Google login credentials.

## Endpoints
The data you request represents the endpoint. For example, if you are requesting the names of computer users within your organization, names represent endpoints. If you are requesting a specific user, such as user ID 00001, then user ID 00001 represents the endpoint.

## Methods
When you send a request, you are asking the destination computer system or service to **do** something. These requests include methods, which are specific verbs or action words. There are four common API methods:

* **GET** – **Retrieves** information.
* **POST** – **Sends** or **Creates** new information.
* **PUT** – **Updates** existing information.
* **DELETE** – **Removes** information.

## JSON
While API requests include methods, API responses commonly display in JavaScript Object Notation (JSON). This format presents data as a **name/value pair**. JSON is not a programming language but rather a vehicle used to store and transfer data from one computer system or service to another. This format (name/value pair) is also one that computers can easily understand.

Here is a basic request:

GET /**presidents**/00001

This request accesses the **Presidents table**, for example, to GET or retrieve all information about the president associated with unique ID 00001.

**Table = Presidents**

![Presidents' Table](/img/table_prez.png)

Here is a basic JSON (name/value pair) response:

```json
{
  "id": 00001,
  "name": "George Washington"
}
```

The JSON response provides raw data rarely visible to users. This is backend data that an app or website needs, and it is also a format that other computer systems can easily understand. On the frontend, however, this data is presented in a user-friendly format. Regarding the name/value pair, the **name** appears to the left of the colon and the **value** appears to the right. Names are commonly in lowercase. Camel case is also common. **studentID**  is an example of camel case. Again, raw data rarely appears on users’ screens; instead, the response data can appear in a range of formats.

## Request, Response
The syntax and format for requests and responses vary, and they can range from simple to complex.

**Example 1: Users table in Company database**

**Table = Users**

![Users' Table](/img/tables_users.png)

Below is a basic, high-level request for information about a specific user.

**Request**:

GET /users/100

This request retrieves information about ID 100 from the **Users** table. The API receives this request then accesses the Users table to retrieve all available information about the user with unique ID 100. 

**Response**: <br/>

```json
{
  "id": 100,
  "name": "John Doe",
  "email": "john.doe@email.com"
}
```

In this example, the API retrieves **all** information from the Users table about ID 100 and provides a JSON response.

**Example 2 : Users table in Company database**

**Table = Users** (modified to include the **Title**, **Department**, and **Home Address** columns):

![Users' Table](/img/table_users_updated.png)

**Request**:

GET /users/100

**Response:** <br/>

```json
{
  "id": 100,
  "name": "John Doe",
  "email": "john.doe@email.com",
  "title": "Software Engineer",
  "department": "Engineering",
  "homeAddress": "123 Main Street, Miami, FL"
}
```

In this example, the API retrieves **all** information from the Users table about the user with unique ID 100 and provides a JSON response. 

**Example 3 : Users table in Company database**

**Table = Users**

![Users' Table](/img/table_users_putA.png)

In this example, PUT will be used to update the Users table.

**Request**:

PUT /users/102

**Response**: <br/>

```json
{
  "id": 102,
  "name": "Angela Doe",
  "email": "angela.doe@email.com",
  "title": "Customer Representative",
  "department": "Customer Success",
  "homeAddress": "789 Paper Street, Dallas, TX"
}
```

The Users table now appears as follows:

![Users' Table](/img/table_users_putB.png)

The API received the request to **update** the table (PUT method) yet **added** a new entry. If you recall from the **Methods** section above, you use PUT to update information and POST to add or create new information. While the PUT method works, technically, the best method/syntax for adding a new entry relative to this example is **POST/users**. This syntax (POST) will add the entry and auto-generate an ID, which is more efficient. The PUT method, however, treated the request like an update to an existing entry because we provided ID 102 – signaling that the entry was already available, thereby making this an update. Again, PUT is acceptable and enables you to specify an ID. Typically, the system auto-generates IDs. (Just keeping you on your toes!)

## Response Codes
An API response code (also known as an HTTP response code) is the result or status of an API request. There are seven common response codes:

1. **200** – Request successful
1. **201** – New content created (a new user, for example); commonly, a result of a POST request
1. **400** – Bad request; website not found or parameters missing, for example
1. **401** – Unauthorized; login credentials failed or login credentials required
1. **403** – Forbidden; website access denied
1. **404** – Not found; webpage, for example, does not exist
1. **500** – Server error or website/app issue

Developers are the primary group who actually sees or views response codes; however, users might see codes such as 404 or 500, signaling **Webpage Not Found** or **Server Error**, respectively. In daily website use or navigation, you might have encountered a response code if, for example, you typed the website name incorrectly or if the website is temporarily down or inactive.

## Base URL
You can also access data via URLs. The base URL is the main address for a website or API. You can use URLs to access sites and retrieve information. The base URL for a website launches you to the main page of the website, and you can add a path to access additional information.

**Base URL for websites**:

```
www.mycompany.com
```

**add path**: 

```
www.mycompany.com/about
www.mycompany.com/users
```

The base URL for an API is the starting point for certain requests. Some sites structure the base URL for APIs such that they begin with **https://api**, while others do not use this format. You can add paths and parameters to URLs for APIs to promotes specificity and access to details.

**Base URL for APIs**: <br/>

```
https://api.github.com 
https://myretailsite/api/v1.com
```

**api** does not have to be part of the base URL for an API name.

**add path**: <br/>

```
https://myretailsite/api/v1/product
```

**add parameter**:

```
https://myretailsite/api/v1/product/{product_id}
```

**add API version and actual product ID:**

```
https://myretailsite.com/api/v1/product/54321
```

For this retail site, myretailsite/api/v1/product alludes to product information. Adding a parameter, such as product ID **54321**, provide specificity which ensures that the request is for a specific product. The **v1** represents the API version. Although this URL does not actually host product data, it serves as the highway leading to this information. The product data, itself, might be housed in a data storage location such as a database.

Adding paths, such as **/users** and **/posts** for example, provides specificity relative to endpoints for data retrieval. Parameters, such as **54321**, provide additional and more precise information. Paths point to the resource or endpoint, and parameters refine or narrow the request by adding details.

## Authorization Header
One of the easiest and most efficient ways to access an API site that requires authentication, such as an **API Key** or **Bearer Token**, is to create an Authorization Header using cURL, which is a tool/library that allows you to interact with APIs and websites. You can execute this code in various command-line interfaces (CLIs), such as the MS Windows command prompt, Mac/Linux terminal, and in a VS Code terminal or similar Integrated Development Environment (IDE).

**Example Authorization Header (API Key)**:

```
curl -H “Authorization: APIKey 12345678901111” https://api.mycompany.com/data 
```

**-H** Informs the request to include a header.

**“Authorization: APIKey 12345678901111”** – Actual authorization header that contains the API key, which indicates you have permission to access the API. Quotes are required. You typically get the API key, itself, from the API site you are attempting to access. As a prerequisite, you might have to access the site and create an account before you can generate this key.

```
https://api.mycompany.com/data 
```

This is the API endpoint you are requesting. 

**Example Authorization Header (Bearer Token)**:

```
curl -H “Authorization: Bearer 12345678901111” https://api.mycompany.com/data 
```

**-H** Informs the request to include a header.

**“Authorization: Bearer 12345678901111”**– Actual authorization header that contains the bearer token, which indicates you have permission to access the API. Quotes are required. You typically get the bearer token, itself, from the API site you are attempting to access. As a prerequisite, you might have to access the site and create an account before you can generate this token.

```
https://api.mycompany.com/data
```

This is the API endpoint you are requesting.

## Parameters
Parameters are details, which help you narrow your search or request to ensure you retrieve the exact information you require. Though similar, there is a difference between a path and a parameter.

**Path**:

```
https://myretailsite.com/api/v1/product
```

This path points to the product endpoint. This request will not yield results because there is no detail or specificity regarding this product request.

**Parameter**: 

```
https://myretailsite.com/api/v1/product/54321
```

This request is for product ID 54321. Adding this parameter provides the required detail because, in this example, it points to a specific product.

## Error Handling
Error handling helps you report and manage errors. Different error types might be triggered when using an API, and you must know how to recognize them and how to fix or manage them. This insight proactively prepares developers, enabling them to identify, address, and resolve errors more efficiently.

As discussed previously, there are seven common response codes:
1. **200** – Request successful
1. **201** – New content created (a new user, for example); commonly, a result of a POST request
1. **400** – Bad request; website not found or parameters missing, for example
1. **401** – Unauthorized; login credentials failed or login credentials required
1. **403** – Forbidden; website access denied
1. **404** – Not found; webpage, for example, does not exist
1. **500** – Server error or website/app issue

Codes **400**, **401**, **403**, **404**, and **500** might be considered response code errors. There is a range of other error types as well.

Developers who build the API commonly provide error handling insight.

## Rate Limiting
Rate limiting is specific to the number of API requests that can be made during a designated time period. Rate limiting, therefore, can impact API usage. With rate limiting, there might be a restriction specific to the number of times you can make an API request per day or even per minute. Exceeding limits can result in a warning message, a statement or error message that restricts further usage for a designated time period, the amount of wait time required before API reuse, or an additional charge for this excess usage. Other factors might also be involved in exceeding specified rate limits. Understanding API rate limits can prevent exceeding its use.

Developers who build the API commonly share the rate limiting insight.

## Versioning
Similar to software versions, API versions (or versioning) tracks the evolution of the API. A newer version, v2 for example, might have additional features, bug fixes, and performance optimizations; updates not available in v1. Both versions might be available simultaneously, and developers can determine which version to use in their apps.

Developers who build the API commonly provide insight into the available versions and the distinctions between each.

## Schemas
Schemas include the field names, datatypes (string, integer, Boolean, for example), and structures specific to the API, enabling developers to request the appropriate information and understand the response. Schemas help you know the exact words to use in your request and the exact words to expect in the response. For example, you might send a request that references the “id”; however, the schema indicates that the request should be for “userID”. Schemas also indicate which fields are required or optional.

Developers who build the API commonly provide the schemas for requests and responses. 


