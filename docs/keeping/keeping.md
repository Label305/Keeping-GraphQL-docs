# What is Keeping?

Keeping is a time registration application for PC, Android and iOS. 
The application is built up out of several objects that each have their own fields.

These objects are: 

* [Organisation](schema/objects/organisation.md)

The organisation contains one or more users and their entries. It also contains all projects that users might be working on and the tasks that have to be completed for those projects. These projects are often done for a client. 

* [User](schema/objects/user.md)

For every organisation that the a user is part of a new user object is created. It is under this object that new time entries will be created. 

* [UserAccount](schema/objects/userAccount.md)

The user account holds all user instances for the different organisations that a user of Keeping might be a part of. It holds some basic information such as the users email address.

* [Client](schema/objects/client.md)

The client for which a project is done

* [Task](schema/objects/task.md)

Specific tasks to which time entries can be assigned

* [Project](schema/objects/project.md)

Specific project to which time entries, tasks and a client can be assigned

* [Entry](schema/objects/entry.md)

A new time entry is created whenever the timer is started. 

* [Report](schema/objects/reports/report.md)

Reports can be generated to contain information such as: the total hours spent spent by a certain user, or on a certain project.