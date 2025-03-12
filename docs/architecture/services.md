# Services 

## Domain model 
[Domain Model](https://www.figma.com/board/KbTFzGSjoDWLn48sB3dicG/Server?node-id=0-1&p=f&t=gtjuR8M1aZok18ya-0)
- Visitor 
- Owner 
- Project 
- Tag
- Authentication 
- Notification 
- Analytics 
- Log

## System operations

| Service      | Actor   | Story               | Type    | Operation                            | Description                          | 
| ------------ | ------- | ------------------- | ------- | ------------------------------------ | ------------------------------------ | 
| CMS          | Visitor | view project list   | query   | getProjectList()                     | retrieve a list of projects          | 
| CMS          | Visitor | view project detail | query   | getProject(id)                       | retrieve a project                   | 
| CMS          | Owner   | create project      | command | createProject(metadata, content)     | create a project                     | 
| CMS          | Owner   | update project      | command | updateProject(id, metadata, content) | update a project                     | 
| CMS          | Owner   | delete project      | command | deleteProject(id)                    | delete a project                     |  
| Analytics    | Owner   | view dashbaord      | query   | getAnalytics()                       | retrieve web traffic data            | 
| Analytics    | ALL     | view dashbaord      | command | logAnalytics(eventData)              | logs web traffic data                | 
| Notification | Logging | error notification  | command | sendNotification(id, message)        | sends an error notification to owner | 
| API Gateway  | Owner   | authentication      | command | login(credentials)                   | log the owner into the system        | 
| API Gateway  | Owner   | authentication      | command | logout(id)                           | log the owner out of the system      |
| API Gateway  | Owner   | authentication      | command | refresh(refreshToken)                | refresh access token                 | 
| API Gateway  | ALL     | -                   | command | logEvent(eventData)                  | logs system events                   | 
| API Gateway  | ALL     | error notification  | command | logError(eventData)                  | logs system errors                   | 
| API Gateway  | Owner   | health status       | query   | getStatus()                          | return health status of the Gateway  | 
| API Gateway  | Owner   | monitoring          | query   | getMetrics()                         | return metric on API usage and perf  | 

## Services 
- Content Mangement Service
- Analytics Service
- Notification Service
- API Gateway 
  - Authentication
  - Authorization
  - Rate limiting
  - Caching
  - Metrics collection
  - Request logging

## API 
- Content Management Service: synchronous request/response - RESTful API 
  - GET /cms/project 
  - GET /cms/project/{id} 
  - POST /cms/project 
  - PATCH /cms/project/{id} 
  - DELETE /cms/project/{id} 
- Analytics Service: 
  - getAnalytics(): retrieve real-time analytics data using gRPC streaming 
  - logAnalytics(): log an events using asynchronous messaging API 
- Notification Service: 
  - sendNotification: asynchronous one-way notification API (The notification in API name means the notificatin sends to the owner. The one-way notification means how other services call Notification service. they does not represent the same thing)
- API Gateway: synchronous request/response - GraphQL
<!-- TODO: rewrite those endpoint definition using GraphQL -->
  - GET /status 
  - GET /metrics 
  - GET /cms/project 
  - GET /cms/project/{id} 
  - POST /cms/project 
  - PATCH /cms/project/{id} 
  - DELETE /cms/project/{id} 
  - POST /auth/login
  - POST /auth/logout
  - POST /auth/refresh
  - POST /analytics/log
  - GET /analytics