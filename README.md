# <b> [DEVELOPMENT BRANCH]</b>
# CMPG323 Project 2 - 33705119
## CMPG323 Module - Project 2 | <img src="https://badgen.net/badge/ASP.NET/API/?icon=visualstudio"></img>


# Table of Contents
1. [Introduction](#introduction)
2. [Authentication](#authentication)
3. [HTTP Methods](#http-methods)
4. [Endpoints](#endpoints)
   - [Customer](#customer)
   - [Orders](#orders)
   - [Order Details](#orderdetails)
   - [Products](#products)
5. [Using the API](#api-use)
6. [Rate Limiting](#rate-limiting)



# Introduction

This API is designed to manage various aspects of the EcoPower Logistics company, including customers, products, orders, and order details. It follows a CRUD (Create, Read, Update, Delete) approach and is built using C# and Entity Framework. This project involves the creation of a .NET Core Web API using Visual Studio, which will be accompanied by Azure SQL Server and hosted on the cloud using Azure's API Management service.

# Authentication
Authentication is required to access the API endpoints. I've integrated JWT (JSON Web Tokens) authentication to ensure secure access to my endpoints. JWT tokens must be included within the request headers to allow access, more details to follow.
</br>

<b>[Reiteration]</b> Gitignore file has been updated to ensure that files that contain sensitive data, such as appsettings.json, will not be uploaded to the repository when committing changes in Visual Studio


## HTTP Methods 
The API supports the following HTTP methods: </br>
```GET     ›   Retrieve data``` </br>
```POST    ›   Create new records``` </br>
```PUT     ›   Update existing records``` </br>
```DELETE  ›   Delete records``` </br>

# Endpoints
## Customer

Manage customer data, including creating, updating, retrieving, and deleting customer records.

|        Function          |                              Features                                         |
|--------------------------|-------------------------------------------------------------------------------|
|```GET /api/customers```  | Retrieve a list of all customers                                              |
|```GET /api/customers/{id}```  | Retrieve details of a specific customer by ID                                 |
|```POST /api/customers```       | Create a new customer. Payload should contain customer information            |
|```PUT /api/customers/{id}```   | Update an existing customer by ID. Payload should contain updated information | 
|```DELETE /api/customers/{id}```| Delete a customer record by ID                                                |

</br>

## Products
Manage product data, including creating, updating, retrieving, and deleting product records.

|        Function          |                              Features                                         |
|--------------------------|-------------------------------------------------------------------------------|
| ```GET /api/products``` | Retrieve a list of all products|
| ```GET /api/products/{id}``` | Retrieve details of a specific product by ID|
| ```GET /api/products/Order/{id}``` | Returns all products associated by a specific product ID|
| ```POST /api/products```  | Create a new product. Payload should contain product information|
| ```PUT /api/products/{id}``` | Update an existing product by ID. Payload should contain updated information|
| ```DELETE /api/products/{id}``` | Delete a product record by ID|
</br>

## Orders
Manage order data, including creating, updating, retrieving, and deleting order records.

|        Function          |                              Features                                         |
|--------------------------|-------------------------------------------------------------------------------|
|```GET /api/orders```| Retrieve a list of all orders.|
|```GET /api/orders/{id}```| Retrieve details of a specific order by ID.|
|```GET /api/orders/CustomerOrder/{id}```| Retrieve all orders based of a customer's ID.|
|```POST /api/orders```| Create a new order. Payload should contain order information.|
|```PUT /api/orders/{id}```| Update an existing order by ID. Payload should contain updated information.|
|```DELETE /api/orders/{id}```| Delete an order record by ID.|


</br>

## OrderDetails
Manage order details data, including creating, updating, retrieving, and deleting order detail records.

|        Function          |                              Features                                         |
|--------------------------|-------------------------------------------------------------------------------|
|```GET /api/orderdetails ```| Retrieve a list of all order details.|
|```GET /api/orderdetails/{id} ```|  Retrieve details of a specific order detail by ID.|
|```POST /api/orderdetails ```| Create a new order detail. Payload should contain order detail information.|
|```PUT /api/orderdetails/{id} ```|  Update an existing order detail by ID. Payload should contain updated information.|
|```DELETE /api/orderdetails/{id} ```|  Delete an order detail record by ID.|

<!---
## Error-Handling
When errors occur, the API will return appropriate error responses with relevant status codes and error messages. Ensure to handle these errors on your end for a smooth user experience.

## Rate Limiting
To prevent abuse, the API has rate limiting in place. Each user has a limited number of requests they can make within a certain time period. If you exceed the limit, you'll receive a rate-limit exceeded response.
-->

# Using The API
Authentication Request & Obtaining API Access:
Before making use of the EcoPowerLogistics API, you need to authenticate yourself by first registering an account on the platform. You must then log in with your registered credentials (username and password) to the login endpoint on the server. Upon successful authentication, you will receive a token in the response.

Using tokens in Requests:
Once you have the token, you must include it in the header of your HTTP requests to the API (which will be done automatically by clicking the authorize on the interface and providing the token in the format specified below):

|Format|
|---------|
|```Authorization: Bearer <token>```|

### Making API Requests:
With the token in place, you can start making requests to the various such as the GET, PUT, DELETE, etc.. requests for the various Customer, Product, Order, and OrderDetails endpoints.

### Token Expiry and Refresh:
The token expired after 3 hours to enhance security. After the token expires, you will need to re-authenticate to obtain a new token.

### Logging Out:
You have the ability to log out after authorization. After logging out, your provided token is no longer valid for authentication.

### Protecting Your Token: 
It contains authentication information and should not be shared or exposed publicly.

## References
* CRUD ASP.NET Web API With Entity Framework In ASP.NET MVC. [C-sharpcorner.com](C-sharpcorner.com)<br>
Available at: [link](https://www.c-sharpcorner.com/article/crud-Asp-Net-web-api-with-entity-framework-in-Asp-Net-mvc/) - Kumar, M. (2020).

* Azure App Service documentation - Azure App Service. [Microsoft](Microsoft.com)</br>
Available at: [link](https://learn.microsoft.com/en-us/azure/app-service/ ) - SyntaxC4 (2023)

* Publish an ASP.NET Core web API to Azure API Management with Visual Studio. [Microsoft](Microsoft.com) </br>
Available at: [link](https://learn.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-api-management-using-vs?view=aspnetcore-6.0) -  codemillmatt (2022) 

* Stack Overflow - More than one DbContext was found. [Stack Overflow](StackOverflow) </br>
Available at: [link](https://stackoverflow.com/questions/52311053/more-than-one-dbcontext-was-found) (2018)

* Tutorial: Use EF Migrations in an ASP.NET MVC app and deploy to Azure. [Microsoft](Microsoft.com) </br>
Available at: [link](https://learn.microsoft.com/en-us/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/migrations-and-deployment-with-the-entity-framework-in-an-asp-net-mvc-application)

* There is already an object named in the database. [Stack Overflow](StackOverflow.com) </br>
Available at: [link](https://stackoverflow.com/questions/26305273/there-is-already-an-object-named-in-the-database) - x19 (2014).

* Consider Enabling Transient Error Resiliency By Adding EnableRetryOnFailure. [Stack Overflow](StackOverflow.com) </br>
Available at [link](https://stackoverflow.com/questions/62802173/consider-enabling-transient-error-resiliency-by-adding-enableretryonfailure) - Sheldon Cohen (2022)

‌* ASP.Net Core API Error (Unable to resolve service for type ... ). [Microsoft](Microsoft.com) </br>
Available at: [link]('https://learn.microsoft.com/en-us/answers/questions/788223/asp-net-core-api-error-(unable-to-resolve-service)') 
