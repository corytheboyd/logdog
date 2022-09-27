# LogDog

A JSON log explorer for locally running services.

## Why

Structured logs are awesome.

They provide an extremely powerful yet simple tool for emitting valuable targeted context for debugging system health.

They are easily parsed by machines to index for search and aggregation.

There is only one problem, they are difficult for humans to read at a glance without tooling.

You have that tooling in your production environments in the form of some very expensive Saas product (you'll never guess which one this tool is influenced by), but wouldn't it be nice to have that same functionality in development too?

That is exactly what this software aims to be: the JSON log explorer for local development.

# Features

- Subscribe to log sources.
	- A log source is just a WebSocket server that emits log lines as messages. [`websocketd`](https://github.com/joewalnes/websocketd) makes this dead simple, ex: `webocketd --port=9876 tail -f development.log`
	- Have many services you want to view logs for all at once? Just add multiple log sources.
- Data paths are automatically extracted from logs, i.e. `response.status`, `request.boody.people[].name`, etc.
- Select the data paths you want to see to set the columns in the logs table.
- Add filters to conditionally remove logs from the logs table.

