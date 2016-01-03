# Errors

```
{
	"status": "400",
	"message": "channel is not joined"
}
```

Any request with a non-200 status code represents an error. We return the status as an HTTP status as well as within the response of API requests to make debugging easier.

For every error, a human-readable error message is returned under the `message` key. In the future, we will likely expand error handling to include error codes so that each error can be better documented and handled by third parties.
