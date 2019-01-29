# user

### Fields

id: int!

userAccountId: int

firstName: string!

lastName: string!

code: string

role: string!

### Relations

userAccount(id: string, email: string, testerRole: string): [userAccount](schema/objects/userAccount.md)!

participations(id: string, canSeeReports: boolean, orderBy: string, take: int, offset: int): [[participation](schema/objects/participation.md)]

projects(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [[project](schema/objects/project.md)]

entries(id: string, ongoing: boolean, orderBy: string, take: int, period: string = "month", offset: int): [[entry](schema/objects/entry.md)]

### Arguments

id: string  

userAccountId: string

firstName: string

lastName: string

code: string

role: string

orderBy: string

take: int

offset: int