# Housework record app

## Why?
Ania suggested that we start recording all of the different things that we do around the house. Ania felt that she was doing a lot more around the house and that having it recorded could give us some information to work with. I was completely on board with this and we started recording tasks on a paper document, however it became easy to forget to fill in and as a result kind of defeats its purpose. Recording this information digitally means it can more easily be added and in a specific format which can be added from any device at any time.

## Technical Why?
I've recently started using NestJS at work and completed the Official NestJS Fundamentals course and would like to build a toy app that might be useful as well as trying to implement what I've learned.

This might be better suited using lambda's to interact with the database, however I'd prefer not to deal with AWS/Terraform/Localstack/AWS Sam...etc.

### Stack
- Frontend (will be in different repo) will be React with Typescript
  - It may be a better idea for this to be written in React Native since it'll most likely be used on phone (I just have no experience with it).
- Backend NestJS with Typescript
  
## MVP
- Backend only
- Be able to record a new task. 
- Get list of completed tasks. 
- Get running total of hours completed per person

## Min data required
We will need a table for the tasks and people completing tasks which will be hard coded at first.

### Completed task table
| column name  | description  | data type  | 
|---|---|---|
| id   | ID of recorded task  | int
| completedBy   | ID from the person table  | int
| completedAt  | Date of when the task was completed  |   Date
| task  | ID from the task item table  | int
| timeTaken  | time taken to perform task minutes | int
| description | Description of completed task - may be default from task table or custom description  | string

### Task item table
| column name  | description  | data type  | 
|---|---|---|
| id   | ID of task item  | int
| name   | Name of task  | string
| shortDescription  | Short description of what the task is  |   string
| longDescription  | Longer description outlining the task  |   string
| defaultTimeToComplete   | The normal time expected to perform the task  | int

### Person table
| column name  | description  | data type  | 
|---|---|---|
| id   | ID of person  | int
| name   | Name of person  | string

## Later
- Allow deleting and editing specific tasks and task items
- Allow editing/adding people
- Maybe allow adding families/households?
- Get list of only tasks names
- Add a frontend to display the data and perform crud actions
- Add new field indicated frequency task should be performed
- Run a command to tell us when certain tasks need to be performed
- Send alert to slack/mobile (twilio?) - something free
- Create some charts with the data
- Maybe update migrate to lambda so service doesn't need to run always - it'll be used very infrequently
- Look into caching
- Logging/Datadog?
- Sentry/error tracking
- Grouping of tasks i.e bathroom, bedroom etc..
- Paginating
- Filtering
- Dockerize
- New tasks should be confirmed by all members
  
## When will the project be considered complete
- When a frontend exists to add task items, to record new completed tasks and when it correctly displays a non-paginated list of completed tasks alongside a running total of hours.