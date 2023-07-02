
```bash
$ npm install
```

## Running the app

```bash
$ npm run start:dev
```

```docker
docker-compose -f docker-compose.yml up
```

Please develop CRUD for User entity in REST API style.
So i want to have next endpoints to access:

|HTTP METHOD | DESCRIBE | ENDPOINT | REQUEST BODY STRUCTURE | RESPONSE BODY STRUCTURE | PARAMETERS (ONLY FOR METHOD - GET) | PATH PARAMETERS | 
|---|----|----------|--------------|---------------|------------------------------------|----|
| GET | Get list of users | /users | - | ```[{"id": "number", "login": "string", "email": "string"}...]``` | **limit** - parameter which is limited count records which will receive from the server. **id**, **login**, **email** - to filter.
| GET | Get certain user by id |/users/{id} | - | ```{"id":"number", "login": "string", "password": "string", "email": "string"}``` | - | id
| POST | Create user from request body |/users | ```{"login": "string", "password": "string", "email": "string"}``` | ```{"id":"number", "login": "string", "password": "string", "email": "string"}``` 
| DELETE | Delete user by id|/users/{id} | - | ```{"id":"number", "login": "string", "password": "string", "email": "string"}``` - means return object which was deleted | - | id
| PATCH | Update user by id |/users/{id} | ```{"id":"number", "login": "string", "email": "string"}``` | ```{"id":"number", "login": "string", "email": "string"}``` | - | id
| POST | Generate new password for user and return it in response |/users/{id}/change-password | ```{"password":"string"}``` | ```{"password":"string"}``` | - | id
| POST | Login user into system - if login and password is matched with any record from db need return. Create for that endpoint new controller which called like AuthController  |/login | ```{"login":"string", "password":"string"}``` | ```{"success":"boolean"}``` | - | -
