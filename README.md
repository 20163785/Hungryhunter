# WEB system
- [ ] Replace "WEB system" with your system name - Hungryhunter - Restaurant Finder

## Description
- [ ] Provide WEB system description in few sentences - its purpose, users, etc. - This web system provides inforamtion of various restaurants, of various places and their food by search. Based on Zomato.

## Entity definition
- [ ] Define the entity ("object" that will be manipulated) of WEB system - Searching entity
- [ ] Entity should have a name - Search
- [ ] Entity should have 3 mandatory attributes:
    - [ ] ID - depending on specific service this could be a number or string - Number(8 letters)
    - [ ] Creation date - (if applicable for specific service) ISO 8601 format date string - mm/dd/yyyy
    - [ ] Modification date - (if applicable for specific service) ISO 8601 format date string - mm/dd/yyyy
- [ ] Entity should have at least 5 custom attributes - Region; Country; City; Street; House number.
    - [ ] Each attribute should have a type defined: number, string, ISO 8601 date string, boolean, object, array or other. - Region - string; Country - string; City - string; Street - string; House number - number.
    - [ ] Each attribute should have restrictions defined: list of constants, or number range, or string length, or string format, or object schema, or array schema or other. For example, you can use `joi` language to define restrictions: https://github.com/hapijs/joi/blob/v13.1.2/API.md - all will use 15 letter string range, but the house number will use 999 letter range.

## API definition
- [ ] Define specific service (konkrečios paslaugos) API methods that WEB system is going to use - Search for restaurants in a specific area.
- [ ] Optionally define additional API methods that WEB system is going to expose - C - Create - POST;
R - Read - GET;
U - Update - PUT;
D - Delete - DELETE;
- [ ] API should have at least 4 methods:
    - [ ] A method to return entity by ID. Should not have request body: https://www.tutorialsteacher.com/webapi/implement-get-method-in-web-api - So this method returns an entity, also if the entity is not found it will return a response: "404 NotFound". https://docs.microsoft.com/en-us/aspnet/core/web-api/action-return-types?view=aspnetcore-2.2 - aditional method.
    - [ ] A method to return multiple entities (Array) by ID. This method should support at least one header value to: https://thoughts-on-java.org/fetch-multiple-entities-id-hibernate/ ; https://softwareengineering.stackexchange.com/questions/335768/can-a-rest-api-return-multiple-resources-as-one-single-compound-resource - Aditional URI method to sort returned entities.
        - [ ] Return only entities that match pattern in one of its attributes - Hibernate’s default behaviour already takes care of it and it’s most often also good enough for performance critical use cases.
        - [ ] Return 10 entities starting provided index - byMultipleIds(Class entityClass): In hibernate Session and provide the class of the entities you want to load as a parameter
        - [ ] Return sorted entities by one of its attributes (both ascending and descending) - This code receives a sortOrder parameter from the query string in the URL. The query string value is provided by ASP.NET MVC as a parameter to the action method. The parameter is a string that's either "Name" or "Date", optionally followed by an underscore and the string "desc" to specify descending order. The default sort order is ascending.
        - [ ] Other (should be approved by Product Owner (PO))
    - [ ] A method to remove entity by ID. Returns removed entity. Should not have request body - https://dotnettutorials.net/lesson/delete-method-in-web-api/ - This works fine and deletes the employee record from the database as expected. The problem here is that since the return type of the Delete method is void, we get status code 204 No Content. When the Deletion is successful, we want to return status code 200 OK indicating that the deletion is successful.https://docs.microsoft.com/en-us/dotnet/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services - URI.
    - [ ] A method to update entity by ID. Accepts entity to update and returns updated entity - https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/update-delete-entities-using-web-api - Retrieve data from an entity you are updating, you can compose your PATCH request so that data from the created record will be returned with a status of 200 (OK). To get this result, you must use the return=representation preference in the request headers. https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/create-update-entity-relationships-using-web-api - URI.
- [ ] Each method should have HTTP method defined
- [ ] Each method should have URI defined (use {id} as entity ID placeholder)
- [ ] Should return all 4xx errors in unified format. Define format using `joi` language
- [ ] Should return all 5xx errors in unified format. Define format using `joi` language

## UI definition
- [ ] Define the structure of how visually the WEB system is going to look like - Header of the web name in the top, in the middle of the page there will be a search bar,  after entering a search option, all restaurants will be listed.
- [ ] Should have at least one view defined with https://wireframe.cc (or other wireframe tool):
- [ ] The view should have a title - https://wireframe.cc/xJS7nD - The title will be in the top f screen with big letters.
- [ ] The view should have a description of a service provided by web system - https://wireframe.cc/CyU7Vy - The description will be under the title with smaller letters, the description will be brief about the system.
- [ ] The view should include at least 2 UI components:
    - [ ] A component to display multiple entities with all their attribute values visible. It should be posible to remove and edit selected entity. - https://ionicframework.com/docs/api/list; Filter - https://ionicframework.com/docs/api/datetime - the entities will be desplayed in list format, there will be a filter to sort them out.
        - [ ] Depending on chosen header of API method that returns multiple entities, it should be posible to select specific 10 entities starting index, sort entities by attribute, filter entities by attribute pattern, or other (should be approved by Product Owner (PO))
    - [ ] A component to create a new entity/edit existing entity. It should be posbile to create new entity and edit selected entity - https://ionicframework.com/docs/api/input; Date -https://ionicframework.com/docs/api/datetime - There will be an input entity (create), date and time entities will also be given but will not be able to edit.
        - [ ] Each attribute should have a dedicated editor field: text box for string or number, checkbox or radio buttons for boolean, date picker for date, etc.
