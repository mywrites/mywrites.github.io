---
layout: default
title: "A Closer Look . . ."
category: "APIs"
---
Below is an image that contains Python code (as opposed to cURL), which depicts API key use:

![API Key](/img/sample1.png)

**EXPLANATION**

* **import requests** <br/>
  * You must use this Python statement when you want to interact with websites. By importing requests, you have access to all the tools you need to perform website interactions. In this context, **import requests** involves importing the Requests library that helps you manage API requests and responses. <br/>

* **/product** <br/>
  * Use product ID 54321 <br/>
  
* **api_key** = “12345678901111”
  * Use the API Key generated from, for example:

    ```
    https://myretailsite.com
    ```
  
* **api_url** = 

  ```
  "https://myretailsite.com/api/v1/product/54321?api_key=12345678901111"
  ```

  The API key is passed directly in the URL as a query parameter. The URL tells the API **where** to access this information and **what data** to return to the API.

* **response = requests.get(url)** 
  * This line sends a GET via the URL to retrieve the product information. <br/>

* **data = response.json()** 
  * This statement converts the API response into the JSON name/value pair format. <br/>
  * If the API request is successful (response code 200) and response received, <br/>
  print **product name and price** <br/> 
  else <br/>
  print **“Error: Unable to retrieve product info.”**

## Basic API Reference Example
Below is a short, basic example of how to structure a general API reference.

**Scenario**: Developers at your company built an API to check to ensure the company website is online. A developer can execute this API check in a command-line interface (CLI) terminal and unbeknownst to front-end website users.

**Basic references to include:** 
1. **Endpoint**: URL path of the API.
1. **Method**: HTTP method used (GET, POST, for example).
1. **Description**: Explanation of endpoint.
1. **Parameters**: Input information required by the developer, for example, along with the datatype of each (string, integer, Boolean), required or optional, and a brief description.
1. **Response**: Name/value pair (usually in JSON).
1. **Response Codes**: HTTP status codes the API can return along with their definitions.

**Example API Reference**

**Endpoint**: /api/website/status

**api** suggests you are interacting with the API. From this API, you are seeking the status of the website. You know to use the words **website** and **status** because they were included in the **schemas** the developer provided. Schemas help you know the exact words to use in your request and the exact words to expect in the response. For example, based on the response below, status is **online** or **offline** as opposed to **active** or **inactive**.

**Method**: GET <br/>
GET means you are retrieving information.

**Description**: This API checks if the website is active by providing a status: online or offline.

**Parameters**: <br/>
url (required) – The URL of the company website.

```
www.mycompany.com
```

This is the input parameter that the developer must provide when executing the API in the CLI as noted in the images below.

**Python Request**

![Python Request](/img/sample2.png)

**cURL Request**

![cURL Request](/img/sample3.png)

**Response:** <br/>

```json
{
  "url": "https://mycompany.com",
  "status": "online",
  "last_checked": "March 25, 2025 at 11:00AM PST"
}
```

The response indicates that our website is online. If uncertain about the exact meaning of any words or phrases, such as **last_checked**, you can access the schemas provided by the developer who built the API.

**Response Codes**: 

**200 OK** – Website online, status returned

**400 Bad Request** – Missing or invalid URL parameter

**404 Not Found** – URL invalid

The Python and cURL requests (in the images above) could have been written to request the response code, which would have been **200**, in this case, since the response above indicates that the site is **online**.

