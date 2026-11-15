# fastmcp-demo-server

A small expense tracker exposed as an MCP server, built with [FastMCP](https://gofastmcp.com) and SQLite.

## Setup

Requires Python 3.14+ and [uv](https://docs.astral.sh/uv/).

```sh
uv sync
uv run python main.py
```

The server stores data in `expenses.db` next to `main.py`. The file is created on first run and is ignored by git.

## Tools

| Tool | Arguments | Description |
|------|-----------|-------------|
| `add_expense` | `date`, `amount`, `category`, `subcategory?`, `note?` | Add an expense and return its id. |
| `list_expenses` | `start_date`, `end_date` | List expenses in an inclusive date range. |
| `summarize` | `start_date`, `end_date`, `category?` | Total amount per category in a date range. |
| `update_expense` | `expense_id`, `date?`, `amount?`, `category?`, `subcategory?`, `note?` | Change only the fields you pass. |
| `delete_expense` | `expense_id` | Remove an expense. |

`update_expense` and `delete_expense` return an error status if the id does not exist.

## Resources

- `expense://categories`: contents of `categories.json`, read on every request so edits apply without a restart.
