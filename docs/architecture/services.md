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

| Actor | Story | Type | Operation | Description | 
| ----- | ----- | ---- | --------- | ----------- | 
| Visitor | view project list | query | getProjectList() | retrieve a list of projects | 
| Visitor | view project detail | query | getProject(id) | retrieve a project | 
| Owner | create project | command | createProject(metadata, content) | create a project | 
| Owner | update project | command | updateProject(id, metadata, content) | update a project | 
| Owner | delete project | command | deleteProject(id) | delete a project | 
| Owner | authentication | command | login(credentials) | log the owner into the system | 
| Owner | authentication | command | logout(id) | log the owner out of the system | 
| Owner | authentication | command | refresh(refreshToken) | refresh access token | 
| | | query | getAnalytics() | retrieve web traffic data | 
| | | command | logAnalytics(eventData) | logs web traffic data | 
| | | command | logEvent(eventData) | logs system events | 
| | | command | logError(eventData) | logs system errors | 
| | | comamnd | sendNotification(id, message) | sends an error notification to owner | 