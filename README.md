<div align="center">
  <br>
  <img alt="EmpMonitor Task Management" src="https://ik.imagekit.io/z8mv4l3fpw/63a2b9c395a5a.png?ik-sdk-version=javascript-1.4.3&updatedAt=1671608865932" width="300px">
  <h1>EmpMonitor Task Management</h1>
  <strong>APIs for EmpMonitor Task Management</strong>
</div>
<br>

 Task Management is the part of EMPMonitor Work Management.  Task Management APIs follows Restful API and build using [Node.js](https://nodejs.org/en/), [ExpressJs](https://expressjs.com/) and [MongoDB](https://www.mongodb.com/home) as a database.

[![task-api-swagger-doc](https://ik.imagekit.io/z8mv4l3fpw/taskSS.png?ik-sdk-version=javascript-1.4.3&updatedAt=1671607688486)
](http://localhost:9001/explorer/)

## ⚙️ Environment variables/ Config
- Add below code to localDev.json file
```
// config/localDev.json 
{
  "task": {
    "host_url": "localhost:9001",
    "port": "9001",
    "host": "localhost:9001"
  },
  "swagger_host_url": "localhost:9001",
  "mongo": {
    "username": "",
    "password": "",
    "host": "127.0.0.1",
    "db_name": "WM-EMP"
  },
  "customTaskType": 5,
  "customTaskStatus": 5,
  "mongo_atlas_enabled": false,
  "mongo_atlas_url": "",
  "token_secret": "SAkjSOciObOard_7541",
  "user_token_secret": "Emp_Work_management_7541"
}
```

## 📖 Prerequisites

- Install [Node.js](https://nodejs.org/en/) version 16.0.0 or higher
- Project management module is running

## 🖥️ Local development

- Clone the repository
```
git clone --branch task-development https://lokendra_globussoft@bitbucket.org/sumitghosh007/emp-monitor-work-management-api.git EMP-WM-Task
```
- Install dependencies
```
cd EMP-WM-Task
npm install
```

- Set local environment
```
set node_env=localDev
```
- Build and run the project
```
npm run dev
```
Navigate to `http://localhost:9001`

- API Document endpoints

  swagger-ui  Endpoint for Task Management : http://localhost:9001/explorer/ 

  swagger-ui  Endpoint for Project Management : http://localhost:9000/explorer/

## Getting started
- Login to to work management from project swagger link and get access toke
- Using access token user is able to run task APIs
- In postman in the headers add 
  - Key as x-access-token and 
  - Value as access token generated from user login 

## Project structure
```bash
├── config                    
│   ├── localDev.json       # Config file for local development
├── core                    
│   ├── task                # All task APIs 
│   │   ├── task.*.js
│   ├── subTask             # All sub task APIs
│   │   ├── subtask.*.js
│   ├── taskType            # All task type APIs
│   ├── taskStatus          # All task status APIs
│   ├── subTaskType         # All subtask type APIs
│   └── subTaskStatus       # All subtask status APIs
├── middleware              
│   │   ├── verifyToken.js  # Middleware for token verification
├── node_modules            
├── resources
│   ├── database            # Database connection
│   │   ├── mongo.connect.js
│   ├── logs                # Logger service
│   │   ├── logger.log.js
│   ├── routes              # Routes for task module
│   │   ├── public.routes.js
│   └── views
│   │   ├── swagger.config.js #Swagger documentation
├── utils
│   │   ├── task.utils.js   # Utility for db connection
├── README.md
├── jwt.service.js          # JWT authentication service
├── package.json            
├── package-lock.json
└── .gitignore
```

### 🚀 Production deployment

A production deployment is a complete build of the project, including the build of the static assets.


## ⚖️ LICENSE

MIT © [EmpMonitor](LICENSE)
