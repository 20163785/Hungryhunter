# WEB system
Hungryhunter - Restaurant Finder

## Description
 This web system provides inforamtion of various restaurants, of various places and their food by search. Based on Zomato.

## Entity definition
 Restaurant
 
 Region - string (max length: 99);
 Country - string (max length: 99); 
 City - string (max length: 99);
 Street - string (max length: 99);
 House number - number (max number: 999);
 Restaurant name - string (max length: 99).


## API definition
 Search for restaurants in a specific area or just for the restaurant.

C - Create - POST - Create a search by variable defined (Region, country, city, street, house number);
R - Read - GET - Get information from database by region;
R - Read - GET - Get information from database by country;
R - Read - GET - Get information from database by city;
R - Read - GET - Get information from database by street;
R - Read - GET - Get information from database by house number;
R - Read - GET - Get information from database by restaurant namer;

GET /api/category/:categoryId?size=:size&from=:from
404 category id not found
PUT  /api/phrase/:id
400 err message when validation fails
POST /phrase
400 err message when validation fails
Get /api/phrase/:id
404 phrase id not found
DELETE /phrase/id
404 phrase id not found
Post /category
400 err message when validation fail

"404 NotFound" for all



 https://www.tutorialsteacher.com/webapi/implement-get-method-in-web-api - So IActionResult type method returns an entity with error if not found: 
 "404 NotFound". 
 
byMultipleIds(Class entityClass): In hibernate Session and provide the class of the entities you want to load as a parameter. (List)
         
This code receives a sortOrder parameter from the query string in the URL. The query string value is provided by ASP.NET MVC as a parameter to the action method. The parameter is a string that's either "Name" or "Date", optionally followed by an underscore and the string "desc" to specify descending order. The default sort order is ascending.

https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api - 
PATCH [Organization URI]/api/data/v9.0/accounts(00000000-0000-0000-0000-000000000001)? - Update and return and status of 200 (OK)

## UI definition
 https://wireframe.cc/pro/edit/243773
