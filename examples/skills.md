---
name: dellstore
description: MCP tools for dellstore. Available tools: list_tables, get_table_schema, execute_query, test_connection. Use when the user needs to call these MCP tools.
---

# dellstore MCP Tools

## Available Tools

### list_tables

List all tables in the database.

Args:
    db_name: Identifier for the database instance (default: "default")

**Execute:**
```python
python3 /Users/supermcp/workspace/forge-mcp-to-skills/.cursor/skills/dellstore/scripts/call.py list_tables
```

### get_table_schema

Get schema information for a specific table.

Args:
    table_name: Name of the table to inspect
    db_name: Identifier for the database instance (default: "default")

Returns:
    JSON string with table schema information

**Parameters:**
- `table_name` (string, required): -

**Execute:**
```python
python3 /Users/supermcp/workspace/forge-mcp-to-skills/.cursor/skills/dellstore/scripts/call.py get_table_schema '{"table_name": "<table_name>"}'
```

### execute_query

Execute a SQL query with optional parameters.

This tool allows you to execute any SQL query
(SELECT, INSERT, UPDATE, DELETE, etc.)
with support for parameterized queries to prevent SQL injection.

Args:
    query: SQL query to execute
    params: Optional dictionary of parameters for parameterized queries
    db_name: Identifier for the database instance (default: "default")

Returns:
    For SELECT queries: List of dictionaries representing rows
    For INSERT/UPDATE/DELETE: List with affected_rows count

**Parameters:**
- `query` (string, required): -
- `params` (any, optional): -

**Execute:**
```python
python3 /Users/supermcp/workspace/forge-mcp-to-skills/.cursor/skills/dellstore/scripts/call.py execute_query '{"query": "<query>"}'
```

### test_connection

Test the database connection and return connection status information.

This tool verifies that the database connection is active and returns
connection details including database type, version, and pool
configuration.

Args:

Returns:
    Dictionary with connection status, database information, and pool
    settings

**Execute:**
```python
python3 /Users/supermcp/workspace/forge-mcp-to-skills/.cursor/skills/dellstore/scripts/call.py test_connection
```


### command:
```
mcp-cli --url http://localhost:8027/mcp/a0504710-203f-4c4b-b864-5e64641d9ed3 --token mcp_token_dummy --name dellstore --script python --output .cursor/skills
```