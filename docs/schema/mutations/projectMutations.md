# Project Mutations

createProject(organisationId: int, name: string!, code: string, clientId: string): [Project](schema/objects/project.md)

deleteProject(organisationId: int, id: int, name: string): boolean

editProjectDetails(id: int, name: string): [Project](schema/objects/project.md)

archiveProject(id: int, organisationId: int): boolean

attachTaskToProject(organisationId: int, projectId: int, taskId: int): boolean

disableProjects(organisationId: int, id: int): boolean

enableProjects(organisationId: int, id: int): boolean

restoreProjects(organisationId: int, id: int): boolean