# organisation

### Fields

id: int!

name: string!

subdomain: string!

isProjectsEnabled: boolean

isTasksEnabled: boolean

timesheetType: string

### Relations

**owner**: user!

**users**(id: string, userAccountId: string, firstName: string, lastName: string, code: string, role: string, orderBy: string, take: int, offset: int): [[user](schema/objects/user.md)]

**clients**(id: string, name: string, canSeeReports: boolean, orderBy: string, take: int, offset: int): [[client](schema/objects/client.md)]

**projects**(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [[project](schema/objects/project.md)]

**tasks**(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [[task](schema/objects/task.md)]

**report**(from: string, till: string, selecting: string): [report](schema/objects/reports/report.md)

### Arguments

id: int!