---
layout: default
title: "Overview"
category: "APIs"
---
Application Programming Interfaces (APIs) allow computers to talk to one another – sending messages (**requests**) from one device and receiving replies (**responses**) from the other.

APIs work behind the scenes or as backend processes to accept requests and retrieve responses. As users navigate apps and websites to shop, perform various searches, and send social media messages, for example, APIs accept these requests, interact with databases and other systems to retrieve data, and return responses.

Think of APIs as invisible, 24-hour security guards protecting data, which might be housed in a range of data storage locations. APIs are on watch/standby, waiting for API requests. Some computer systems (apps and websites, for example) that request information must, first, be authenticated to determine if they are, in fact, allowed to make these requests; alternatively, other apps and websites can request data without authentication. Contingent upon how developers build the API, this authentication may or may not be required. Once the API receives the request, the API accesses the data storage location, retrieves the data, and returns a response to the requesting app or website.

The power of APIs is unlimited:

* **Using Google Maps to search for a location**? An API sends your request to a map service then returns the directions to your computer or phone screen. 
* **Accessing a retail site, browsing items, and adding clothing to your shopping cart**? APIs provide shopping cart updates by, first, sending the request to the server after you have added an item then responding by increasing the total number of items in the shopping cart. 
* **Entering required login credentials to access your online banking information**? APIs send your login credentials to an authentication server for verification. The server, for example, might check a database that contains a table with customer IDs along with the associated customer names, usernames, and passwords. The authentication server checks the login credentials against the database table information, providing this verification outcome to the API. This response, which the API returns to the banking app, results in bank app access (if login credentials are valid) or access denial (if login credentials are invalid).

APIs not only function as 24-hour security guards but also serve as highways to the actual data. Lots of companies have built APIs to allow this data access. For example, Twitter, Google Maps, NASA, and so many other companies have APIs. Each API accepts a request, retrieves data, and provides a response.

Although there is a great deal of logic built into an API, for users, their interactions with APIs via apps and websites are seamless. More specifically, users are unaware of the programming code and raw data produced by APIs because the responses can appear on users’ computer or mobile device screens in a range of readable formats to include map directions, shopping cart updates, charts, graphs, and reports. The API response format might depend on the request by the app or website as well as built-in app tools, leveraged to provide visual depictions of data.

**Example 1**: MS Excel contains built-in chart tools. When you add numbers and figures to an MS Excel spreadsheet, you can select this data, insert a chart or graph, and display this graphic based on the numbers/figures you added. Regarding APIs, you can send sales data to an MS Excel spreadsheet in JSON (a **name/value pair** format, discussed further below), and MS Excel can process this data and display this information as a chart or graph. **So, the visual display of a chart or graph is a result of the application’s built-in chart tools, not the API**.

**Example 2**: Within an observability platform, users can view visual displays of data via charts and graphs. In this case, the app requests data from the API, for example, and the API retrieves data from a server. The API then returns the data (response) to the app. The app, perhaps, has a chart library that can convert JSON, for example, into charts or graphs. The app, therefore, takes the response data, puts this data into the chart tool, and displays a chart on the computer screen. **So, the visual display of a chart or graph is a result of the application’s chart library, not the API**.

APIs accept requests, retrieve data, and return responses. The format of the readable data returned, however, might be contingent upon the actual request (shopping cart, search, online banking for example) or the app’s chart or graph tools. 

APIs are not only useful because they help automate and streamline processes but also allow computer systems and services to communicate with one another (as opposed to developers having to manually code these programs).

**NOTE**: <br/>
To develop or document APIs, it is imperative that you understand at least one programming language (such as Go or Python, for example) along with JavaScript Object Notation (JSON). This knowledge facilitates your ability to learn and understand exactly how APIs work.

## Data Storage Locations
When developers build APIs, they commonly establish where the API retrieves data. They also commonly ensure proper connection and configuration to this storage location to make certain the API can retrieve the requested data without issue. API data retrieval locations include:
* **Databases**
  * Databases can contain information specific to customers, users, products, orders and    transactions, inventory, emails/chat messages/notifications, and a range of other data.
* **File Storage**
  * File storage can include text, MS Word files, PDFs, or photos stored on a server. For example, if you are attaching a photo from Google Drive to your Gmail message, Gmail uses the Google Drive API, retrieves the photo, and returns the photo to Gmail where you can attach this photo to your message. Since Gmail and Google Drive are a subset of Google Workspace, no developer configuration is required; Gmail uses built-in integration with the Google Drive API to make the request and retrieve the photo.
* **External Services (Third-party APIs)**
  * You might access a news app for sports information, but the news app might not have that information directly. It might send a request to an external API (ESPN’s API, for example) asking, “Can you provide all sports updates?” ESPN’s API checks its system for sports news and returns this information to the news app, where it displays on your computer or mobile device screen.
* **Cache**
  * If you access [CNN](https://www.cnn.com) throughout the day for news updates, your browser accesses CNN’s server, retrieves content, and stores this data in your browser’s cache. During subsequent visits to the site that day, the browser checks the cache first. If the website content is still there, the site will load this content to your computer screen or mobile device – making access much faster since the browser does not have to re-access the CNN server.
* **Cloud Storage**
  * The File Storage example above (Gmail using the Google Drive API for photo retrieval) also applies to cloud storage since Google Drive stores data in the cloud. Microsoft’s OneDrive, Apple’s iCloud, and Amazon Drive function similarly.

## REST vs SOAP
There are two primary API types: REST and SOAP

Representational State Transfer (REST) APIs use certain action words known as **methods** (GET/POST/PUT/DELETE) in the communication syntax. If you are not using REST (also known as RESTful) APIs, you might be using Simple Object Access Protocol (SOAP) APIs.

SOAP APIs use eXtensible Markup Language (XML) to communicate and use POST almost exclusively; they do not commonly use GET/PUT/DELETE. SOAP APIs are rule-specific and more formal and complex than REST APIs.

Because REST APIs are more common and, generally, easier to use than SOAP APIs, this content focuses on REST APIs hereafter referred to as simply APIs.

## Payment
Relative to payment for APIs, there are three common scenarios:
* Free API access with no account sign-up/creation required
* Free API access but account sign-up/creation required
* Charge for API access, perhaps pay-as-you-go pricing or use of a subscription model

When you access API sites, you will know which scenario is at play. 

**Rate Limiting** (explained in the **Reference/Tutorial** section) can also impact API use. With rate limiting, there might be a restriction specific to the number of times you can make an API request per day or even per minute. Exceeding limits might result in a warning message, a statement that restricts further usage for a designated time period, or an additional charge for this excess usage.
