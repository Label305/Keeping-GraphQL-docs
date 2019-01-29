# User Mutations

createUser(organisationId: int!, firstName: string!, lastName: string!, code: string, role: string!): [User](schema/objects/user.md)

deleteUser(organisationId: int!, id: int, firstName: string, lastName: string): boolean

editUserDetails(organisationId: int!, id: int!, firstName: string, lastName: string, code: string): [User](schema/objects/user.md)

addUserToAllActiveProjects(organisationId: int!, id: int, firstName: string, lastName: string): boolean

archiveAndBlockUser(organisationId: int!, id: int, firstName: string, lastName: string): boolean

enableAddUserToNewProjectsAutomatically(organisationId: int!, id: int, firstName: string, lastName: string): boolean

disableAddUserToNewProjectsAutomatically(organisationId: int!, id: int, firstName: string, lastName: string): boolean

inviteUser(organisationId: int!, userToInviteId: int!, invitingUserId: int!, email: string!): boolean

restoreUser(organisationId: int!, id: int, firstName: string, lastName: string): boolean

setInvitationEmailAddress(organisationId: int!, id: int, firstName: string, lastName: string, email: string!): boolean