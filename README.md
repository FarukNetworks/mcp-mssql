# GUIDE 

1. **Create the Virtual Environment**: Run the following command to create a virtual environment named `venv`:
   ```bash
   python3.10 -m venv venv
   ```

2. **Activate the Virtual Environment**:
   - On macOS and Linux:
     ```bash
     source venv/bin/activate
     ```

3. **Verify the Python Version**: After activation, verify that the virtual environment is using Python 3.10 by running:
   ```bash
   python --version
   ```

4. **Enter Connection String Details**:
   - Create a `.env` file and add the following connection details:
   ```bash
   MSSQL_SERVER=localhost
   MSSQL_USER=SA
   MSSQL_PASSWORD=YourStrong@Passw0rd
   MSSQL_DATABASE=localdatabase
   MSSQL_PORT=1433
   ```

5. **Connect MSSQL MCP Server to Your Cursor Editor**:
   - Create or edit the file in folder: `.cursor/mcp.json`
   ```json
   {
     "mcpServers": {
       "mssql": {
         "command": "uv",
         "args": [
           "--directory", 
           "path/to/mssql_mcp_server",
           "run",
           "mssql_mcp_server"
         ],
         "env": {
           "MSSQL_SERVER": "localhost",
           "MSSQL_USER": "your_username",
           "MSSQL_PASSWORD": "your_password",
           "MSSQL_DATABASE": "your_database"
         }
       }
     }
   }
   ```
