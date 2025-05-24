# restViz

`restViz` is a lightweight library designed to create a dynamic web interface for Express applications. It automatically lists all defined API routes, providing an interactive interface to explore and document your API.

## Features

- **Automatic Route Discovery**: Detects and lists all routes defined in your Express app.
- **Dynamic API Documentation**: No need for manually updating documentation as your app evolves.
- **Seamless Integration**: Works seamlessly with Express without additional configurations.
- **Enriched Metadata**: Add descriptions, notes, responses, and request bodies per route.
- **Interactive API Doc Viewer**: A dynamic, dev-friendly view of your app's endpoints.
- **Header Support**: Add custom headers to your requests directly in the UI for better testing of protected or customized endpoints.
- **Interactive API Testing**: Send real HTTP requests to your endpoints directly from the interface — supports all HTTP methods, headers, and request bodies.

---

## Installation

Install `restViz` using NPM:

```bash
npm install restviz
```

## How It Works

- Simply import init from restviz and pass (express).
- pass init in your `app.use(init(express))`.
- Run your app, and restViz will generate a dynamic web interface listing all your routes.

Example Output:
After starting your app, visit `http://localhost:your-port-here` in your browser. You’ll see:

A list of all defined routes:

```
GET /
PUT /
POST /
DELETE /
PATCH /
```

Configuration Options
You can customize restViz by passing options to restViz.init():

```js
import { init, Options, Theme } from 'restviz'

const app = express()

const theme: Theme = 'light'

const options: Options = {
  title: 'My API Documentation', // Set a custom title for the web interface
  theme: 'dark', // Choose between "light" or "dark" theme
}

app.use(init(express, options))
```

Available Options
`title`: Customizes the web interface title (`default: "API Documentation"`).
`theme`: Chooses the theme for the interface (`default: "light"`)

## Compatibility

⚠️ `Note`: restViz is currently compatible with Express v4 and v5 only for alpha version.
To install latest express:

```bash
npm install express
```

## Addtional usage

You can enrich your route documentation using metadata annotations. These are attached to each route and enhance the clarity and purpose of your API documentation.

**Supported Metadata Fields:**

- **`description`**: A brief explanation of what the endpoint does.  
  _Example_: `"description": "Update user details"`

- **`notes`**: Extra details like warnings, use cases, or behavior explanation.  
  _Example_: `"notes": "Only admins can perform this action."`

- **`responses`**: A key-value map describing expected HTTP response codes and their meanings.  
  _Example_:
  ```json
  "responses": {
    "200": "Success",
    "400": "Bad request",
    "401": "Unauthorized"
  }
  ```
- **`body`**:An example object representing the expected request payload.
  Used for methods like _POST_, _PUT_, or _PATCH_.
  _Example_:

  ```json
  "body": {
  "email": "example@gmail.com",
  "password": "testing@123"
  }
  ```

## Contributing

Contributions are welcome!
If you encounter bugs, have ideas for improvements, or want to extend functionality, feel free to [open an issue](https://github.com/theCalculatar/restViz/issues) or submit a pull request.

Before contributing, please take a moment to review our [CONTRIBUTING.md](./CONTRIBUTING.md) guidelines for helpful tips and requirements.

## License

This project is licensed under the [MIT License](./LICENSE).

You are free to use, modify, and distribute this software with proper attribution. See the full license text for more details.
