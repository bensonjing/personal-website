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
| Auth         | Owner   | authentication      | command | login(credentials)                   | log the owner into the system        | 
| Auth         | Owner   | authentication      | command | logout(id)                           | log the owner out of the system      | 
| Auth         | Owner   | authentication      | command | refresh(refreshToken)                | refresh access token                 | 
| Analytics    | Owner   | view dashbaord      | query   | getAnalytics()                       | retrieve web traffic data            | 
| Analytics    | ALL     | view dashbaord      | command | logAnalytics(eventData)              | logs web traffic data                | 
| Logging      | ALL     | -                   | command | logEvent(eventData)                  | logs system events                   | 
| Logging      | ALL     | error notification  | command | logError(eventData)                  | logs system errors                   | 
| Notification | Logging | error notification  | command | sendNotification(id, message)        | sends an error notification to owner | 

## Services 

- Content Mangement Service
- Authentication Service
- Analytics Service
- Logging Service
- Notification Service