# participation

### Fields

id: int

canSeeReports: boolean!

### Relations

**user**(id: string, userAccountId: string, firstName: string, lastName: string, code: string, role: string, orderBy: string, take: int, offset: int): [user](schema/objects/user.md)!

**project**(id: string, name: string, code: string, orderBy: string, take: int, offset: int): [project](schema/objects/project.md)!

