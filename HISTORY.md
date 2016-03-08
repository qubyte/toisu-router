# History

## v3.0.0

Complete overhaul of the API. The `get` method has been dropped and a `route` method added. The
route method takes an object of HTTP methods as fields and middleware arrays as values. This change
allows middleware arrays to be added for multiple methods at the same time for the same path.
Crucially, it also means that the router knows when a path matches, but there is no middleware array
for the HTTP method used. This knowledge means that the router now responds with a `405` status code
and an `Allow` header with a list of implemented HTTP methods when this happens.

See the [README](./README.md) for more information.