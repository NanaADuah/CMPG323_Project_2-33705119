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
6. [Additional Functionalities](#additional-functionalities)

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

# API-Use
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
The token expires after 3 hours to enhance security. After the token expires, you will need to re-authenticate to obtain a new token.

### Logging Out:
You have the ability to log out after authorization. After logging out, your provided token is no longer valid for authentication.

### Protecting Your Token: 
It contains authentication information and should not be shared or exposed publicly.

# Additional-Functionalities
Microsoft Azure that helps you safeguard cryptographic keys, secrets, and other sensitive information. Implementation of Azure Key Vault for a connection string to the database provides a secure way to store and manage my connection strings, API keys, and passwords.

## References
<details>
   <summary>All the references used for the Project 2</summary>
   
* Brabec, M. (2014). Entity Framework rollback and remove bad migration. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/22680446/entity-framework-rollback-and-remove-bad-migration) ‌[Accessed 18 Aug. 2023].

* andersjanmyr (2008). How can I rename a project folder from within Visual Studio? [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/211241/how-can-i-rename-a-project-folder-from-within-visual-studio) [Accessed 18 Aug. 2023].

* Kumar, M. (2020). CRUD ASP.NET Web API With Entity Framework In ASP.NET MVC. [online] C-sharpcorner.com <br>
Available at: [link](https://www.c-sharpcorner.com/article/crud-Asp-Net-web-api-with-entity-framework-in-Asp-Net-mvc/) [Accessed 19 Aug. 2023].

* S, P.K. (2019). Creating A Web API Project In Visual Studio 2019. [online] C-sharpcorner.com. </br>
Available at: [link](https://www.c-sharpcorner.com/article/creating-a-web-api-project-in-visual-studio-2019/) [Accessed 20 Aug. 2023].

* Mori, A. (2020). What Is Startup Class And Program.cs In ASP.NET Core. [online] C-sharpcorner.com. </br>
Available at: [link](https://www.c-sharpcorner.com/article/what-is-startup-class-and-program-cs-in-asp-net-core/) [Accessed 20 Aug. 2023].

* Redhat.com. (2022). What is an API? [online] </br>
Available at: [link](https://www.redhat.com/en/topics/api/what-are-application-programming-interfaces) [Accessed 20 Aug. 2023].

* hrvn10 (2018). Azure SQL database not found or inaccessible problem. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/52828391/azure-sql-database-not-found-or-inaccessible-problem) [Accessed 21 Aug. 2023].

* Rick-Anderson (2022). Build RESTful APIs with ASP.NET Web API - ASP.NET 4.x. [online] Microsoft.com. </br>
Available at: [link](https://learn.microsoft.com/en-us/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api) [Accessed 21 Aug. 2023].

* dotnet (2021). Creating a Web API project [3 of 18] | Web APIs for Beginners. YouTube. </br>
Available at: [link](https://www.youtube.com/watch?v=AA5Fyt8sM7Y) [Accessed 31 Aug. 2023].

* SyntaxC4 (2023). Azure App Service documentation - Azure App Service. [online] Microsoft.com. </br>
Available at: [link](https://learn.microsoft.com/en-us/azure/app-service/ ) [Accessed 20 Aug. 2023].

* codemillmatt (2022). Publish an ASP.NET Core web API to Azure API Management with Visual Studio. [online] Microsoft.com </br>
Available at: [link](https://learn.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-api-management-using-vs?view=aspnetcore-6.0)  [Accessed 20 Aug. 2023]‌

* Sivakumar (2021). Azure CLI 2.x is not installed on this machine. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/70461134/azure-cli-2-x-is-not-installed-on-this-machine) [Accessed 24 Aug. 2023].

* tdykstra (2022). Tutorial: Use EF Migrations in an ASP.NET MVC app and deploy to Azure. [online] Microsoft.com. </br>
Available at: [link](https://learn.microsoft.com/en-us/aspnet/mvc/overview/getting-started/getting-started-with-ef-using-mvc/migrations-and-deployment-with-the-entity-framework-in-an-asp-net-mvc-application) [Accessed 28 Aug. 2023].

*  x19 (2014). There is already an object named in the database. [Stack Overflow](StackOverflow.com) </br>
Available at: [link](https://stackoverflow.com/questions/26305273/there-is-already-an-object-named-in-the-database) [Accessed 28 Aug. 2023]. 

* Sheldon Cohen (2022). Consider Enabling Transient Error Resiliency By Adding EnableRetryOnFailure. [online] StackOverflow.com </br>
Available at [link](https://stackoverflow.com/questions/62802173/consider-enabling-transient-error-resiliency-by-adding-enableretryonfailure) [Accessed 28 Aug. 2023].

* resting (2012). Markdown to create pages and table of contents? [online] Stack Overflow.</br>
Available at: [link](https://stackoverflow.com/questions/11948245/markdown-to-create-pages-and-table-of-contents) [Accessed 23 Aug. 2023].

* Yaourt (2021). Some services are not able to be constructed. Error while validating the service descriptor. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/69198882/some-services-are-not-able-to-be-constructed-error-while-validating-the-service) [Accessed 25 Aug. 2023].
‌
* kimbaudi (2016). Dependency Injection error: Unable to resolve service for type while attempting to activate, while class is registered. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/40900414/dependency-injection-error-unable-to-resolve-service-for-type-while-attempting) [Accessed 25 Aug. 2023].

* WilliamDAssafMSFT (2023). What is the Azure SQL Database service? - Azure SQL Database. [online] Microsoft.com </br>
Available at: [link](https://learn.microsoft.com/en-us/azure/azure-sql/database/sql-database-paas-overview?view=azuresql) [Accessed 28 Aug. 2023].

* KJBTech (2016). System.InvalidOperationException: Unable to resolve service for type. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/40265541/system-invalidoperationexception-unable-to-resolve-service-for-type?noredirect=1&lq=1) [Accessed 26 Aug. 2023].

* Rehman, F. (2020). Invalid value for key ‘authentication’. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/59654712/invalid-value-for-key-authentication) [Accessed 28 Aug. 2023].

* Ibanez1408 (2018). More than one DbContext was found. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/52311053/more-than-one-dbcontext-was-found) [Accessed 28 Aug. 2023].

* flashsplat (2022). How do I get the DBContext in a class? [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/73781004/how-do-i-get-the-dbcontext-in-a-class?noredirect=1&lq=1) [Accessed 26 Aug. 2023].

* Kovacevic, V. (2017). Unable to resolve service for type while attempting to activate. [online] Stack Overflow. </br>
Available at: [link](https://stackoverflow.com/questions/46930090/unable-to-resolve-service-for-type-while-attempting-to-activate?rq=3) [Accessed 29 Aug. 2023].

* markdefalco (2021). Creating a Web API project [3 of 18]. [online] Microsoft.com. </br>
Available at: [link](https://learn.microsoft.com/en-us/shows/beginners-series-to-web-apis/creating-a-web-api-project-3-of-18--beginners-series-to-web-apis) [Accessed 29 Aug. 2023].

* Nazar Pylyp (2019). .NET Core 3.0 possible object cycle was detected which is not supported. [Stack Overflow](StackOverflow.com) </br>
Available at: [link](https://stackoverflow.com/questions/59199593/net-core-3-0-possible-object-cycle-was-detected-which-is-not-supported)  [Accessed 31 Aug. 2023]

* Microsoft.com. (2022). ASP.net Core API Error (Unable to resolve service for type ‘TapAPI.Models.TodoContext’ while attempting to activate ‘TapAPI.Controllers.TapController’) - Microsoft Q&A. [online] </br>
Available at: [link](https://learn.microsoft.com/en-us/answers/questions/788223/asp-net-core-api-error-(unable-to-resolve-service)) [Accessed 30 Aug. 2023].

</details>
