# project

### Fields

a project

Fields

id: int!

name: string!

code: string

### Relations

**client**(id: string, canSeeReports: boolean, orderBy: string, take: int, offset: int): [client](schema/objects/client.md)

**taskAssignments**(id: string, canSeeReports: boolean, orderBy: string, take: int, offset: int): [[taskAssignment](schema/objects/taskAssignment.md)]

**participations**(id: string, canSeeReports: boolean, orderBy: string, take: int, offset: int): [[participation](schema/objects/participation.md)]

**users**(id: string, userAccountId: string, firstName: string, lastName: string, code: string, role: string, orderBy: string, take: int, offset: int): [[user](schema/objects/user.md)]

**tasks**(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [[task](schema/objects/task.md)]

### Arguments

id: string

name: string

code: string

orderBy: string

take: int

offset: int