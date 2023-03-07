# REST API (Representational state transfer)

## [Beginner](https://www.youtube.com/watch?v=faMdrSCVDzc&t=133s)
## Why is REST APIs stateless
- An application is stateful if it stores data on the server from the client. The server is now storing data.
- REST API's are stateless as they do not store data, and they expect to be already given the necessary info in the relevant HTTP method request

## HTTP methods
- GET, POST, PUT, DELETE (CRUD)

## HTTP status code
- 200
	- represents successful request and response
- 400
	- client side error
- 404
	- the resource requested cant be found
- 500
	- server side error

## URI (uniform resource identifier)
- Identifies every resource in the REST architecture
- Can be of two types, URN (identify resouce through a unique name, like a book's ISBN) or URL (web address)
- On web, URLs would be used to design REST APIs

## Best practices in URI for making RESTful web services
- URIs should be standardized when developing a RESTful web service
	- Forward slashes indicate hiearchy
	- Plural nouns for branches
	- Hiphens for multiple words
	- Use lowercase
	- Avoid file extensions

## Differences between REST and SOAP (Simple Object Access Protocol)
- REST is an architecture used to develop web services, SOAP serves as a protocol to exchange structured information
- REST has flexible standards, SOAP has more strict standards and that the implementation and statefulness means that the client and server are closer connected
- REST allows for data transfer in JSON, XML etc, SOAP only supports XML
- SOAP is a stricter and more niche alternative to REST, used where more regulated and stateful data has to be transferred

## Differences between REST and AJAX (Asynchronous JavaScript and XML)
- AJAX is a collection of web technolgoies that allow for asynchronous web applications using the built in XML, HTTP request object.
- REST represents the architecture to handling HTTP requests, AJAX refers to a collection of web technologies for making asynchronous web requests.
- REST API may handle AJAX clients, AJAX may be used to send RESTful requests, but a REST API could never be implemented or replaced by AJAX

## Tools to develop and test REST APIs
- Develop
	- NodeJS: Express, Java: Spring Boot
- Test
	- Postman 

## Real world examples of API
- Enter a website, a GET request would be sent to a certain endpoint to retrieve the HTML contents of the page
- REST APIs are used to manipulate data in the database using the four main http methods (GET, POST, PUT, DELETE)

## Pros and Cons for RESTful APIS
- Pros
	- Easy to learn
	- Wide range of data transfers, e.g. JSON, XML
	- Statelessness, allowing for simpler client experience
	- Scalability, independent nature of client and server being separated as there not connected (stateless)
- Cons
	- Lack of built-in security measures
	- Need to be versioned for backward compatibility when updated
	- Consistency in URIs make it difficult to maintain for complex projects


## [Advanced](https://www.youtube.com/watch?v=n2JQFFFEd0M)

## Difference between PUT, POST, PATCH
- PUT updates the whole existing resource
- POST creates a new resource
- PATCH alters only specified data of an existing resource

## What is the payload in the context of REST API?
- Paylod refers to data that has been transferred through the REST API
- If client makes GET request to server, server will provide a response with the paylod
- A client may also provide payload in a POST request, where the client is giving data to the server

## What is a REST message?
- Whenever a response is provided, a message is always given along the with the associated HTTP code
- This is essential for debugging, such as completion of a certain action or even raising exceptions for errors


## What are the core components of an HTTP request?
- Method
	- GET,POST,DELETE etc
- URI
	- Used to identify the resource, e.g. the URL
- HTTP version
	- HTTP version used, HTTP/1.0 or HTTP/3.0
- Request Header
	- Contains the metadata, which can be the message format, cache settings, content type etc
- Request Body
	- Contains the content data being sent

## What are the core components of an HTTP request?
- Status Code
	- Provides information about success or failure of request
	- 200 codes indicate success
	- 400 codes indicate client side error
	- 500 codes indicate server side error
- HTTP version
	- Indicates version being used
- Response Header
	- Contains response metadata: content length, content type, date etc
- Response Body
	- Contains the request data
	- Response body not necessary for request, but is necessary for response

## What is an idempotent method and why are they important?
- When working with RESTful APIs, a client may send numerous HTTP requests to a server at a time
- An idempotent method yields the same response, regardless of how many times a request is sent
- Imagine pressing a button which sends a GET request for certain resource, the response would be the same as the first time we pressed the button
- REST APIs are designed to not depend on previous API calls, thus stateless

## What is the difference between idempotent and safe HTTP methods