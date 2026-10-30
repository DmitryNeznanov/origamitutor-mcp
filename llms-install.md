# Installing Origami Tutor (for AI agents)

Origami Tutor is a hosted remote MCP server. There is nothing to clone, build or install, and no API key.

1. Add a server named `origami-tutor` to the client's MCP settings, using the remote URL `https://origamitutor.com/api/mcp` (Streamable HTTP):

   ```json
   {
     "mcpServers": {
       "origami-tutor": {
         "url": "https://origamitutor.com/api/mcp"
       }
     }
   }
   ```

2. If the client cannot connect to remote URLs directly, use the `mcp-remote` bridge instead:

   ```json
   {
     "mcpServers": {
       "origami-tutor": {
         "command": "npx",
         "args": ["-y", "mcp-remote", "https://origamitutor.com/api/mcp"]
       }
     }
   }
   ```

3. Check it works: list the tools. You should see `find_origami`, `get_origami`, `get_origami_steps`, `suggest_origami` and `list_categories`. Then call `find_origami` with `{"query": "paper plane"}`; it should return paper airplane models.
