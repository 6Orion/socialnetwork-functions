# socialnetwork-functions
Google Firebase Functions app which serves as REST API for [Social Network](https://bit.ly/2ABep1S). Find the front-end code [here](https://bit.ly/37z0jtT).

## Demo
Site: </br>
[Social Network](https://bit.ly/2ABep1S) 


## Interface
Route: </br>
[https://europe-west1-orion-socialnetwork.cloudfunctions.net/api/](https://europe-west1-orion-socialnetwork.cloudfunctions.net/api/)

---
### /signup 

method: **POST**

description: *Sign up new user with unique email and user handle*

##### parameters:
property | type | required 
--------------|------|----------
email *(unique)* | string | *
userHandle *(unique)* | string | *
password | string | *
confirmPassword | string | *


##### returns:
property | type | description
--------------|------|----------
token | string | JSON Web Token generated by Google Firebase Authentication
    
---
### /login 

method: **POST** 

description: *Log in existing user*

##### parameters:
property | type | required 
--------------|------|----------
email | string | *
password | string | *

##### returns:
property | type | description
--------------|------|----------
token | string | JSON Web Token generated by Google Firebase Authentication

---
### /user

method: **GET**

description: *Retrieve authenticated user's data*

##### returns:
property | type | description
--------------|------|----------
*user object* | object | All saved user data

---
### /user

method: **POST**

description: *Add new user details*

##### parameters:
property | type | required 
--------------|------|----------
all | all | /

##### returns:
property | type | description
--------------|------|----------
*user object* | object | All saved user data

---
### /user/:userHandle

method: **GET**

description: *Retrieve :userHandle's public data*


##### returns:
property | type | description
--------------|------|----------
*user object* | object | All saved user data

---
### /stories

method: **GET**

description: *Retrieve authenticated user's stories*


##### returns:
property | type | description
--------------|------|----------
*story documents* | array | List of all user's stories

---
### /stories

method: **POST**

description: *Creates new story*

##### parameters:
property | type | required 
--------------|------|----------
body | string | *

##### returns:
property | type | description
--------------|------|----------
*story* | object | Story data

---
### /stories/:storyId

method: **GET**

description: *Retrieve a public story with ID = storyId*


##### returns:
property | type | description
--------------|------|----------
*story doc* | object | Public story with ID = storyId

---
### /stories/:storyId

method: **DELETE**

description: *Delete authenticated user's story with ID = storyId*


##### returns:
property | type | description
--------------|------|----------
message | string | Status update

---
### /stories/:storyId/comment

method: **POST**

description: *Creates new comment on a story with ID = storyId*

##### parameters:
property | type | required 
--------------|------|----------
body | string | *

##### returns:
property | type | description
--------------|------|----------
*comment* | object | Comment data

---
### /stories/:storyId/like

method: **GET**

description: *Like a story with ID = storyId*


##### returns:
property | type | description
--------------|------|----------
message | string | Status update

