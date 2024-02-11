# GraphQL Restaurant API

## Description

This project implements a GraphQL API for managing restaurant data, including operations to fetch, add, edit, and delete restaurant information. It uses Express.js and the `express-graphql` middleware to set up the GraphQL server.

## Features

- **Fetch Restaurants**: Retrieve a list of all restaurants or a single restaurant by ID.
- **Add Restaurant**: Add a new restaurant with details including name, description, and dishes.
- **Edit Restaurant**: Update details of an existing restaurant.
- **Delete Restaurant**: Remove a restaurant from the list.

## Installation

To run this project, you'll need Node.js installed on your system. Follow these steps to get it up and running:

1. Clone the repository:
```bash
git clone [repository-url]
```

2. Install dependencies:
```bash
cd [project-directory]
npm install
```

3. Start the server:
```bash
node index.js
```
The server will run on `http://localhost:5500/graphql`.

## Usage

Access the GraphQL interface through `http://localhost:5500/graphql` in your browser to run queries and mutations.

### Queries

- Fetch all restaurants:
```graphql
{
  restaurants {
    id
    name
    description
    dishes {
      name
      price
    }
  }
}
```

- Fetch a single restaurant by ID:
```graphql
{
  restaurant(id: 1) {
    name
    description
    dishes {
      name
      price
    }
  }
}
```

### Mutations

- Add a restaurant:
```graphql
mutation {
  setrestaurant(input: {id: 4, name: "New Restaurant", description: "Description here"}) {
    id
    name
  }
}
```

- Edit a restaurant:
```graphql
mutation {
  editrestaurant(id: 1, name: "Updated Name") {
    name
  }
}
```

- Delete a restaurant:
```graphql
mutation {
  deleterestaurant(id: 1) {
    ok
  }
}
```

## Technologies

- Node.js
- Express.js
- GraphQL
- express-graphql

## Contributors

Feel free to contribute to this project by submitting a pull request.

## License

This project is licensed under the MIT License.

---

This README provides a basic overview of the project setup, features, and usage instructions. Feel free to customize it further based on your project's specific requirements or additional functionalities.
