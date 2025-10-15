## Static files are used from the /static path on the MCP server

After running ```pnpm run build``` you need to copy all the test*.* files in the /assets directory to the /static folder under this server.

### Example /static folder structure after copying:

```
/static/
├── test-2d2b.css
├── test-2d2b.html
├── test-2d2b.js
└── test.js.map
```

Copy command example:
```bash
cp assets/test*.* src/test_server_python/static/
```

## Running the server locally

Use the following command from the top folder:
```
uv run test_server_python/main.py
```

## Verifying the server locally

Use MCP inspector by running the following command:
```
npx @modelcontextprotocol/inspector
```
Then when the inspector opens in your browser add the following settings:
```
Tranport Type: Streamable HTTP
URL = http://0.0.0.0:8000/mcp
Connection Type: Direct
```
Click Connect or Reconnect. Once connected you can list to tools, resources, and templates.


## Deploying

I've been using the Render.com to deploy this MCP server. For testing , you can use a -free- account to create a Web Service.

# Config settings:

Use the following for the 'Build Command'
```
uv sync
```

Use the following for the start command:
```
uv run test_server_python/main.py
```
