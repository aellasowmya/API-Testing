# Employees API #

This API allows you to get create and update dummy employee details

The API is available at `https://dummy.restapiexample.com/api/v1`

## Endpoints ##

### Status ###

GET `/status`

Returns the status of the API.

### Get all employee data ###

GET `/employee`

Returns a list of all employees.



### Get a single employee data###

GET `/employee/{id}`

Retrieve detailed information about a employee.


### Create new record in database###

POST `/create`

Allows you to create new employee record in db.

The request body needs to be in JSON format and include the following properties:

 -	{"name":"test","salary":"123","age":"23"}

No Authorization required.

Response body contains Name,Id,Salary ,Age

### Update an employee record###

PUT`	/update/{id}`

Allows you to update employee Records.
The request body needs to be in JSON format and include the following properties:

	{"name":"test","salary":"123","age":"23"}

  Response body contains:
  {
    "status": "success",
    "data": {
        "name": "test",
        "salary": "123",
        "age": "23",
        "id": 25
    }
}


### Delete an employee record	 ###

DELETE `/delete/{id}`

Delete an existing order. Requires authentication.

The request body needs to be empty.



## API Authentication ##

To submit or view an order, you need to register your API client.

POST `/api-clients/`

The request body needs to be in JSON format and include the following properties:

 - `clientName` - String
 - `clientEmail` - String

 Example

 ```
 {
    "clientName": "Postman",
    "clientEmail": "abc@gmail.com"
}
 ```

The response body will contain the access token. The access token is valid for 7 days.

**Possible errors**

Status code 409 - "API client already registered." Try changing the values for `clientEmail` and `clientName` to something else.
