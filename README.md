# GraphQL Restaurant Database

## Project Description

This project implements a GraphQL API for managing restaurant data. It provides endpoints to perform various operations on restaurants and their associated dishes. The GraphQL API supports querying for individual restaurants by ID, retrieving a list of all restaurants, creating new restaurants, deleting existing restaurants, and updating restaurant details.

## Installation and Usage

- `npm install`
- `npm install express express-graphql graphql --save`

## Terminal

- run GraphQL server: `node index.js`

## Browser

- navigate in the browser to: `http://localhost:5500/graphql`

## GraphQL Code

```
mutation editrestaurants($iid: Int = 1, $name: String!, $description: String!) {
  editrestaurant(id: $iid, name: $name, description: $description) {
    name
    description
  }
}

mutation setrestaurants {
  setrestaurant(input: {
    name: "Newest New Food Store USA"
    description: "American"
  })
  {
    name
    description
  }
}

mutation deleterestaurants($iid: Int = 3) {
  deleterestaurant(id: $iid) {
    ok
  }
}

query getrestaurants {
  restaurants {
    name
    description
    dishes {
      name
      price
    }
  }
}

query getrestaurant($iid: Int = 2) {
  restaurant(id:$iid) {
    name
    description
  }
}
```

QUERY VARIABLES

```
{
  "iid": 1,
  "name": "New Name",
  "description": "New Description"
}
```

## License Info

[MIT](https://choosealicense.com/licenses/mit/)  
_Copyright (c) 2023 Jessica Cousins_

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Contributing

Contributions to this project are welcome. If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.
