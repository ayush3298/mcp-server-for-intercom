# MCP Server for Intercom

This guide explains how to set up and configure the Model Context Protocol (MCP) server for Intercom integration.

## For Operators

### Step 1: Clone the Repository
First, clone the repository to your local machine:
```bash
git clone https://github.com/ayush3298/mcp-server-for-intercom.git
cd mcp-server-for-intercom
```

### Step 2: Install Dependencies and Build
Run the following commands to install dependencies and build the project:
```bash
npm i
npm run build
```

This will create a new folder named `build`, inside which you will find the compiled `index.js` file.

### Step 3: Get the Full Path to index.js

To get the complete path to your `index.js` file:

#### On macOS/Linux:
1. Navigate to the build directory:
```bash
cd build
```

2. Get the full path:
```bash
pwd
```

3. The output will show the directory path. Your complete path will be this output plus `/index.js`
For example: `/Users/apple/PycharmProjects/mcp_servers/mcp-server-for-intercom/build/index.js`

#### On Windows:
1. Navigate to the build directory:
```cmd
cd build
```

2. Get the full path:
```cmd
cd
```

3. The output will show the directory path. Your complete path will be this output plus `\index.js`
For example: `C:\Users\username\Projects\mcp-server-for-intercom\build\index.js`

### Step 4: Configure Claude MCP

In your Claude MCP configuration file, add the following configuration for Intercom:

```json
{
  "intercom": {
    "command": "node",
    "args": [
      "yourpath/mcp-server-for-intercom/build/index.js"
    ],
    "env": {
      "INTERCOM_ACCESS_TOKEN": "your--api-key"
    }
  }
}
```

> **Important**: Make sure to replace the path in `args` with the complete path to the `index.js` file on your machine.

### Step 5: Start the MCP Server
After configuring, start your MCP server according to your environment's standard procedure.

## Troubleshooting

If you encounter any issues with the Intercom integration:

1. Verify the path to the `index.js` file is correct in your configuration
2. Check that your Intercom access token is valid
3. Ensure your MCP server has network access to reach Intercom's API

## Security Notes

- Keep your Intercom access token secure
- Do not share the configuration file containing the token
- Consider using environment variables for the token in production environments