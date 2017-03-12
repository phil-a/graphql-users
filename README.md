# GraphQL-users

This is a small express server for learning how to work with GraphQL.

## Queries
#### Get Company
    {
      company(id: "1"){
        id
        name
        description
        users {
          id
          firstName
        }
      }
    }

#### Get Company (with fragment)
    {
      apple: company(id: "1"){
    		...companyDetails
      }
    }

    fragment companyDetails on Company{
      id
      name
      description
      users {
        id
        firstName
      }
    }

## Mutations
#### Add User
    mutation {
      addUser(firstName: "Jim", age: 23) {
        id
      }
    }

#### Delete User
    mutation {
      deleteUser(id:"23") {
        id
      }
    }

#### Edit User
    mutation {
      editUser(id: "40", companyId: "1"){
        id
        age
        firstName
        company {
          id
          name
        }
      }
    }
