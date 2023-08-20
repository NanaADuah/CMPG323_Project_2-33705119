# CMPG323 Project 2 - 33705119
## CMPG323 Module - Project 2

# Table of Contents
1. [Introduction](#introduction)
2. [Authentication](#introduction)
3. [Endpoints](#introduction)
   1. [Customers](#customer)
   2. [Orders](#orders)
   3. [Order Details](#orderdetails)
   4. [Products](#products)
5. [HTTP Methods](#http-methods)
6. [Error Handling](#error-handling)
7. [Rate Limiting](#rate-limiting)



# Introduction

This API is designed to manage various aspects of the EcoPower Logistics company, including customers, products, orders, and order details. It follows a CRUD (Create, Read, Update, Delete) approach and is built using C# and Entity Framework. This project involves creating of a .NET Core Web API using Visual Studio which will be accompanied by Azure SQL Server and hosted on the cloud using Azure's API Management service.

# Authentication
Authentication is required to access the API endpoints. Each request must include an API key in the headers for validation. Contact the API administrator to obtain your API key.

```
AUTHENTICATION THINGS
```
</br>

## HTTP Methods 
The API supports the following HTTP methods: </br>
```GET: Retrieve data.``` </br>
```POST: Create new records.``` </br>
```PUT: Update existing records.``` </br>
```DELETE: Delete records.``` </br>

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
## Error-Handling
When errors occur, the API will return appropriate error responses with relevant status codes and error messages. Ensure to handle these errors on your end for a smooth user experience.

## Rate Limiting
To prevent abuse, the API has rate limiting in place. Each user has a limited number of requests they can make within a certain time period. If you exceed the limit, you'll receive a rate-limit exceeded response.

## References
* CRUD ASP.NET Web API With Entity Framework In ASP.NET MVC. [C-sharpcorner.com](C-sharpcorner.com)<br>
Available at: [link](https://www.c-sharpcorner.com/article/crud-Asp-Net-web-api-with-entity-framework-in-Asp-Net-mvc/) - Kumar, M. (2020).

* Azure App Service documentation - Azure App Service. [Microsoft](Microsoft.com)</br>
Available at: [link](https://learn.microsoft.com/en-us/azure/app-service/ ) - SyntaxC4 (2023)

* Publish an ASP.NET Core web API to Azure API Management with Visual Studio. [Microsoft](Microsoft.com) </br>
Available at: [link](https://learn.microsoft.com/en-us/aspnet/core/tutorials/publish-to-azure-api-management-using-vs?view=aspnetcore-6.0) -  codemillmatt (2022) 


