Sure, here's the updated README with emojis:

# API_nodeJS_mySQL :computer:

This is a simple API developed with Node.js and connected to a MySQL database. It provides an example of CRUD operations using the Express framework.

## Features :star:

- Connects to a MySQL database
- Provides basic CRUD operations
- Built with Node.js and Express

## Setup :wrench:

To set up the API, follow these steps:

1. Clone the repository to your local machine.
2. Install the necessary dependencies by running `npm install`.
3. Update the connection details to your MySQL database in the `infraestrutura/conexao.js` file.
4. Start the server by running `npm start`.
5. The API should now be running on `http://localhost:3000`.

## Usage :rocket:

The API provides the following endpoints:

- GET `/atendimentos` - Returns a list of all appointments in the database.
- GET `/atendimentos/:id` - Returns the appointment with the specified ID.
- POST `/atendimentos` - Creates a new appointment in the database.
- PATCH `/atendimentos/:id` - Updates the appointment with the specified ID.
- DELETE `/atendimentos/:id` - Deletes the appointment with the specified ID.

## Controller :gear:

The controller is responsible for handling the API endpoints and interacting with the model. Here's an example of a controller:

```js
const Atendimento = require('../models/atendimentos')

module.exports = app => {
    app.get('/atendimentos', (req, res) => {
        Atendimento.lista(res);
    })

    app.get('/atendimentos/:id', (req, res) => {
        const id = parseInt(req.params.id)
        Atendimento.listaPorID(id, res);
    })

    app.patch('/atendimentos/:id', (req, res) => {
        const id = parseInt(req.params.id)
        Atendimento.atualizarRegistro(id, req.body, res);
    })

    app.post('/atendimentos', (req, res) => {
       const atendimento = req.body

        Atendimento.adiciona(atendimento, res);
    })

    app.delete('/atendimentos/:id', (req, res) => {
        const id = parseInt(req.params.id)
        Atendimento.deletarRegistro(id, res);
    })
}
```

## Further Help :question:

For further help or more detailed information, please refer to the [Node.js documentation](https://nodejs.org/en/docs/) and the [Express documentation](https://expressjs.com/).
