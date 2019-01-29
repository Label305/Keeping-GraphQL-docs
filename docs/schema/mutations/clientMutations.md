# Client Mutations

createClient(organisationId: int!, name: string!, code: string): [Client](schema/objects/client.md)

deleteClient(id: int, organisationId: int!, name: string): boolean

editClientDetails(id: int!, organisationId: int!, name: string, code: string): [Client](schema/objects/client.md)