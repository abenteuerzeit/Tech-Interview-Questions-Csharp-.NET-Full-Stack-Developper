# Networking, HTTP, Web technologies

## What is the difference between HTML and XML?

HTML (Hypertext Markup Language) and XML (eXtensible Markup Language) are both markup languages that are used to structure data for display in a web browser or other application. However, they are used for different purposes and have some key differences.

HTML is a markup language that is used to create the structure and layout of web pages. It uses a set of predefined tags, such as `<p>` for paragraphs, `<h1>` for headings, and `<img>` for images, to describe the content and layout of the page. HTML is designed for the display of data in a web browser and is optimized for visual presentation.

XML, on the other hand, is a markup language that is used to describe the structure of data. It uses a set of user-defined tags, such as `<book>` or `<author>`, to describe the elements and attributes of the data. XML is designed to be a flexible, self-describing format that can be used to represent data in a wide variety of applications, not just web pages.

In summary, the main difference between HTML and XML is that HTML is designed for the display of data in a web browser and is optimized for visual presentation, while XML is designed to be a flexible, self-describing format that can be used to represent data in a wide variety of applications.

HTML has a predefined set of tags and is used to create web pages and is also limited to certain set of elements and attributes. XML is user-defined, allows for custom tags and elements, it is a data representation language, it can be used to transfer data between different systems and allows for more flexibility in the data representation.

## What is a schema in XML? How is a schema validated?

A schema in XML is a document that defines the structure of an XML document. It defines the elements, attributes, and their relationships that can be used in an XML document. Schemas are used to validate the structure of an XML document and ensure that it conforms to the rules defined in the schema.

An XML schema can be written in different languages, such as XML Schema Definition (XSD) or Relax NG. These languages define the rules for the structure and content of an XML document. For example, an XSD schema can define the data types of elements and attributes, as well as their constraints, such as minimum and maximum values, and the number of occurrences of an element.

There are different ways to validate an XML document against a schema, some of them are:

Using a parser: most XML parsers have the capability to validate an XML document against a schema. The schema can be specified as a parameter when parsing the XML document.

Using a validation tool: there are various tools available that can validate an XML document against a schema, such as xmllint or xsd.exe.

Programmatically: you can validate XML document using programming languages such as Java or C# using libraries such as JAXP or XmlSchemaSet.

Validation is an important step in the processing of an XML document, as it ensures that the document conforms to the rules defined in the schema and that the data is accurate and consistent. It also helps to identify and correct errors early in the process, which can save time and resources in the long run.

## What is XSLT? 

XSLT stands for "Extensible Stylesheet Language Transformations". It is a language used to transform XML documents from one format to another. XSLT is used to convert an XML document into a format that can be displayed in a web browser, such as HTML, or into another XML document with a different structure.

An XSLT document, also known as an XSLT stylesheet, contains a set of templates that are used to match elements in the source XML document. These templates define the transformation rules for the matched elements, such as how the element should be displayed in the resulting document.

XSLT stylesheets can also include XSLT functions and variables that can be used to perform calculations and manipulate data. This allows for more complex transformations, such as sorting or filtering elements based on certain criteria.

XSLT is widely used in web development as a way to separate the presentation of data from the data itself. It can be used to display the same data in different formats, such as HTML, PDF, or text. It also enables data transformation between different systems, allowing for data interoperability.

One of the most common use of XSLT is to transform XML data into HTML pages, this is used by many websites to separate the data from the presentation and make it easier to maintain and update the website.

It's worth noting that XSLT 3.0 is the latest version of XSLT and it adds new features such as improved support for streaming and function calls, as well as new functions and operators.

## When is AJAX used? Provide examples

AJAX stands for Asynchronous JavaScript and XML. It is a technique used to create dynamic, fast and responsive web applications. AJAX is used to update parts of a web page without having to refresh the entire page. This allows for a more seamless and efficient user experience, as the user can interact with the page without having to wait for a full page refresh.

AJAX is typically used in web applications that require real-time updates, such as chat applications, social media platforms, and e-commerce sites. Here are a few examples of when AJAX is used:

Auto-suggest search: A search box that suggests search results as the user types, this feature is commonly used in e-commerce websites, news websites, and social media platforms, the search results are fetched via AJAX requests in the background, this allows for a faster search experience, as the user doesn't have to wait for the page to refresh to see the results.

Infinite scrolling: A feature that allows users to scroll through a long list of items, such as news articles or products, without having to load a new page, the new items are fetched via AJAX requests as the user scrolls down the page, this allows for a faster and smoother browsing experience.

Live notifications: A feature that allows users to receive notifications in real-time, such as new messages, friend requests, and updates, without having to refresh the page, this feature is commonly used in social media platforms and chat applications, the notifications are fetched via AJAX requests in the background.

Form validation: A feature that allows for real-time form validation, such as checking for errors or duplicates, without having to submit the form, the form data is sent via an AJAX request and the server responds with the validation results, this allows for a faster and more seamless form-filling experience.

AJAX is a powerful tool for creating dynamic and responsive web applications, it allows for a more seamless and efficient user experience, by reducing the need for full page refreshes and allowing for real-time updates.

## What kind of HTTP status codes do you know?

HTTP status codes are three-digit numbers that are returned by a web server in response to a client's request. They indicate the outcome of the request and provide information about the status of the requested resource.

Here are some examples of common HTTP status codes:

200 OK: The request was successful and the requested resource was returned.

201 Created: The request was successful and a new resource was created as a result.

204 No Content: The request was successful but there is no content to return.

400 Bad Request: The request was malformed or invalid.

401 Unauthorized: The request requires authentication.

403 Forbidden: The server refuses to fulfill the request.

404 Not Found: The requested resource could not be found.

500 Internal Server Error: An error occurred on the server.

503 Service Unavailable: The server is currently unable to handle the request.

504 Gateway Timeout: The server did not receive a timely response from an upstream server.

These are some common HTTP status codes that are widely used, there are many more status codes that are defined by the HTTP protocol, each one indicating a specific state of the request or the resource.

It's worth noting that each status code provides a specific meaning and it's important to handle them correctly in the client-side and server-side to ensure a consistent behavior of the application.

## What is a REST API?

REST, or Representational State Transfer, is an architectural style for building web services. A REST API is a web service that adheres to the constraints of REST.

A REST API defines a set of operations (often called endpoints) that can be performed on resources. Resources are identified by URIs and are accessed using standard HTTP methods such as GET, POST, PUT, and DELETE. The data exchanged between the client and the server is typically in the form of JSON or XML.

Each endpoint in a REST API is designed to perform a specific operation on a specific resource. For example, a REST API for a blog might have the following endpoints:

GET /posts - Retrieves a list of all blog posts
GET /posts/{id} - Retrieves a specific blog post by its ID
POST /posts - Creates a new blog post
PUT /posts/{id} - Updates a specific blog post by its ID
DELETE /posts/{id} - Deletes a specific blog post by its ID
REST APIs are stateless, meaning that the server does not maintain any information about the client between requests. This allows for scalability and makes it easy to cache responses.

REST APIs are widely used in web development to build web services, mobile applications, and other client-server applications that need to communicate over the internet. They provide a simple, consistent and easy to use interface to access and manipulate the resources, this allows for a separation of concerns and a decoupling of the client and the server.

## What is JSON? When is it used?

JSON, which stands for JavaScript Object Notation, is a lightweight data interchange format that is easy for humans to read and write and easy for machines to parse and generate. It is based on a subset of the JavaScript Programming Language, Standard ECMA-262 3rd Edition - December 1999. JSON is a text format that is completely language-independent but uses conventions that are familiar to programmers of the C family of languages, including C, C++, C#, Java, JavaScript, Perl, Python, and many others.

JSON is typically used for:

- Serializing and deserializing data between a web server and a web application
- Sending data between a web application and a server in a format that can be easily parsed
- Storing data in a format that can be easily read and understood by humans.

JSON is a very popular data format, it's lightweight, easy to parse and generate, and it's supported by almost all programming languages, this makes it a perfect choice for web development, mobile development, and other client-server applications that need to exchange data over the internet.

JSON has a simple syntax and it's based on key-value pairs, it's easy to understand and it's human-readable. JSON data is represented as a collection of key-value pairs, where the key is a string, and the value can be a string, a number, a boolean, an array, or another JSON object. JSON objects can be nested, which allows for a more complex data structure.

It's worth noting that JSON is a data-interchange format, it doesn't include any built-in support for data types, such as dates or binary data, it's also not optimized for performance, it's more focused on providing a simple and easy to use data format.
