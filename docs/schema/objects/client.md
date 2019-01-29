# client

### Fields

id: int!

name: string!

code: string

### Relations

**projects**(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [[project](schema/objects/project.md)]

### Arguments

id: string

name: string

canSeeReports: boolean

orderBy: string

take: int

offset: int