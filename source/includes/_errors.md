# Errors

<aside class="notice">Not all errors map cleanly onto HTTP response codes.</aside>

Mashvisor uses conventional HTTP response codes to indicate the success or failure of an API request. In general, codes in the `2xx` range indicate success, codes in the `4xx` range indicate an error that failed given the information provided (e.g., a required parameter was omitted), and codes in the `5xx` range indicate an error with Mashvisor's servers (these are rare).

Mashvisor API uses the following error codes:


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request sucks.
401 | Unauthorized -- Your API key is wrong or you have used an invalid JWT token.
403 | Forbidden -- The Mashvisor requested is hidden for administrators only.
404 | Not Found -- The specified object could not be found.
405 | Method Not Allowed -- You tried to access a Mashvisor with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
