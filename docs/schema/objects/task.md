# task

### Fields

id: int!

name: string!

code: string

### Relations

taskAssignment(id: string, canSeeReports: boolean, orderBy: string, take: int, offset: int): [taskAssignment](schema/objects/taskAssignment.md)

projects(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [[project](schema/objects/project.md)]

### Arguments

id: string

name: string

code: string

orderBy: string

take: int

offset: int