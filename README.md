# Task_Trelli
For CRUD operations in a ToDo Table with user Authentication.

Usage Example:

Register a User:
----------------
curl -X POST -d 'username=jpzk&password=yourguess' \
http://localhost:8000/register/
Get Authentication Token
curl -X POST -d \
'username=jpzk&password=yourguess&grant_type=password&client_id=jpzk' \
http://localhost:8000/oauth2/access_token/
 
{"access_token": "41b59e8238bb418c1fc98cfc6f523dd1a7839a03", "token_type":
"Bearer", "expires_in": 2591999, "scope": "read"} 


Create a Todo:
--------------
curl -X POST -H 'Content-Type: application/json' -H 'Authorization: bearer \
41b59e8238bb418c1fc98cfc6f523dd1a7839a03' -d '{"description":"bake a bread"}' \
http://localhost:8000/todos/ 

Get All Todos:
-------------
curl -X GET -H 'Content-Type: application/json' \
-H 'Authorization: bearer 41b59e8238bb418c1fc98cfc6f523dd1a7839a03' \
http://localhost:8000/todos/

Update a Todo:
-------------
curl -X PUT -H 'Content-Type: application/json' \
-H 'Authorization: bearer 41b59e8238bb418c1fc98cfc6f523dd1a7839a03' \
-d '{"description":"bake a bread", "done":"True"}' \
http://localhost:8000/todos/1

Delete a Todo:
--------------
curl -X DELETE -H 'Content-Type: application/json' \
-H 'Authorization: bearer 41b59e8238bb418c1fc98cfc6f523dd1a7839a03' \
-d '{"description":"bake a bread", "done":"True"}' \
http://localhost:8000/todos/1
