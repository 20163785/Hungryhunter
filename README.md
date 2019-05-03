# WEB system
Hungryhunter - Restaurant Finder

## Description
 This web system provides inforamtion of various restaurants, of various places and their food by search. Based on Zomato.

## Entity definition
 Restaurant
 
 Location - string (max length: 99);
 Location_details - string (max length: 99); 
 dailymenu - string (max length: 99);
 Reviews - string (max length: 99);
 Restaurant - string (max length: 999);


## API definition
 Search for restaurants in a specific area or just for the restaurant.


R - Read - GET - Get information from database by locations;
R - Read - GET - Get information from database by location_details;
R - Read - GET - Get information from database by dailymenu;
R - Read - GET - Get information from database by reviews;
R - Read - GET - Get information from database by restaurant;

GET https://developers.zomato.com/api/v2.1/locations?query=New%20York
  "code": 403,
  "status": "Forbidden",
  "message": "Invalid location parameters"
GET  https://developers.zomato.com/api/v2.1/location_details?entity_id=location_id&entity_type=location_id
  "code": 403,
  "status": "Forbidden",
  "message": "Invalid location parameters"
Get https://developers.zomato.com/api/v2.1/dailymenu?res_id=ramen
400	
Invalid res_id
GET https://developers.zomato.com/api/v2.1/restaurant?res_id=ramen
400	
Invalid res_id
GET https://developers.zomato.com/api/v2.1/reviews?res_id=ramen
400	
Invalid res_id


 https://www.tutorialsteacher.com/webapi/implement-get-method-in-web-api - So IActionResult type method returns an entity with error if not found: 
 "403 NotFound". 
 
byMultipleIds(Class entityClass): In hibernate Session and provide the class of the entities you want to load as a parameter. (List)
         
This code receives a sortOrder parameter from the query string in the URL. The query string value is provided by ASP.NET MVC as a parameter to the action method. The parameter is a string that's either "Name" or "Date", optionally followed by an underscore and the string "desc" to specify descending order. The default sort order is ascending.

https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api - 
PATCH [Organization URI]/api/data/v9.0/accounts(00000000-0000-0000-0000-000000000001)? - Update and return and status of 200 (OK)

## UI definition
 https://wireframe.cc/pro/edit/243773
