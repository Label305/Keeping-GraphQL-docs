# Task Mutations

createTask(organisationId: int!, name: string!, code: string, willBeAssignedToNewProjects: boolean!): [Task]schema/objects/task.md)

deleteTask(organisationId: int!, id: int, name: string): boolean

editTaskDetails(organisationId: int!, id: int!, name: string, code: string, willBeAssignedToNewProjects: boolean): [Task](schema/objects/task.md)