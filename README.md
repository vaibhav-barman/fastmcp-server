# fastmcp-demo-server

A small expense tracker exposed as an MCP server, built with [FastMCP](https://gofastmcp.com) and SQLite.

## Setup

Requires Python 3.14+ and [uv](https://docs.astral.sh/uv/).

```sh
uv sync
uv run python main.py
```

The server stores data in `expenses.db` next to `main.py`. The file is created on first run and is ignored by git.
