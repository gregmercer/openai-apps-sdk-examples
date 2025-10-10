## Known issues:
I haven't been able to get these two calls to work from the 'test' widget.
```
  const helloAgain = async () => {
    await window.openai.sendFollowUpMessage({ "prompt": "can you show the test app again with the title 'hello again.'" });
    // todo: using callTool isn't working for me yet.
    //await window.openai.callTool("test-tool", { "title_text": "hi again. :)" });
  };

  const gotoDoc = async () => {
    // todo: this isn't working for me yet.
    window.openai.openExternal({ "payload": "https://developers.openai.com/apps-sdk" });
  };
```

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