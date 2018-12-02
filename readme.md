# Elevation Fitness API Documents

Welcome to the Elevation Fitness API! If you're looking to integrate your application with Elevation Fitness or create your own application in concert with data inside of Elevation Fitness, you are in the right place. 

# How Do You Authenticate With Our API?

Please contact support@elevationfit.com to obtain a personal access token.

# Making Requests

All URLs start with ```https://elevationfit.com/api/v1/xxx/```. URLs are HTTPS only. The path is prefixed with the account ID (the *xxx* part).

For example a request to see all your clients might look like this.

``` shell
curl -H "Authorization: Bearer $ACCESS_TOKEN" -H 'User-Agent: MyApp (yourname@example.com)' https://elevationfit.com/api/v1/123/clients
```

To insert a record, it is the same idea, but you also have to include the `Content-Type` header and the JSON data:

``` shell
curl -X POST \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ "UsersFirstName": "John", "UsersLastName": "Smith" }' \
  https://elevationfit.com/api/v1/123/clients
```

Throughout the Elevation Fitness API docs, we include "Curl Example". To try the examples in your shell, copy your access token into your clipboard and run:

``` shell
export ACCESS_TOKEN=PASTE_ACCESS_TOKEN_HERE
export ACCOUNT_ID=123
```

Then you should be able to copy/paste any example from the docs. After pasting a cURL example, you can pipe it to a JSON pretty printer to make it more readable. Try [jsonpp](https://jmhodges.github.io/jsonpp/) or `json_pp` on OSX:

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/clients | json_pp
```

# JSON Only

We use JSON for all API data. This means that you have to send the Content-Type header Content-Type: application/json; charset=utf-8 when you are POSTing or PUTing data into Basecamp. For debugging purposes you can also add ```?format=human``` to the end of any request and get back nicely formatted output. This is an alternative to using jsonpp (mentioned above.)

Curl Example: 

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/clients?format=human
```

# API Responses 

All API responses will be in the same format. Here is an example response for a successful response.

``` json
{
	"status": 1,
	"data": ....,
	"pages": 30
}
```

```status``` will be 1 for success and 0 for failure. 

```pages``` is the total number of pages possible.

On a failed call the api response will be as follows.

``` json
{
  "status": 0,
  "errors": [
    { "FieldName1": "Error message" },
    { "FieldName2": "Error message" }    
  ] 
}
```

# Pagination

All api calls are limited to returning just 100 records. We use the page flag to get additional records. 

For example lets make this call....

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/clients
```

Lets assume the response is as such.

``` json
{
	"status": 1,
	"data": [...100 records.....],
	"pages": 4
}
```

This api call will return the first 100 records. Now if we want the records between 101-200 we make this call.


``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/clients?page=2
```

# Ordering & Sorting

All api calls that return more than one record supports an order and sort option.

```updated_start_date=COLNAME``` and ```sort=asc|desc```

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts&order=TrackedWorkoutsUpdatedAt&sort=asc
```

# Filter By Updated Date

All api calls that return more than one record support start and end parameters based on the UpdatedAt field. 

```updated_start_date=XXXX-XX-XX``` and ```updated_end_date=XXXX-XX-XX```

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts?updated_start_date=2017-03-01&updated_end_date=2017-03-03
```

# Handling errors

If the Elevation Fitness API is having trouble, you might get a 5xx error. `500` means that the application is entirely down, but `502 Bad Gateway`, `503 Service Unavailable`, or `504 Gateway Timeout` errors are also possible. In all of these cases, it is your responsibility to retry your request later.

# Api Endpoints

- [Users](/users) 

- [Exercises](/exercises.md) 

- [Programs](/programs.md) 

- [Assigned Workouts](https://github.com/elevationfitness/elevationfit.com-api-docs/blob/master/sections/AssignedWorkouts.md)

- [Tracked Workouts](https://github.com/elevationfitness/elevationfit.com-api-docs/blob/master/sections/TrackedWorkouts.md)

- [Template Workouts](https://github.com/elevationfitness/elevationfit.com-api-docs/blob/master/sections/TemplateWorkouts.md)

# License

These API docs are licensed under [Creative Commons (CC BY-SA 4.0)](http://creativecommons.org/licenses/by-sa/4.0/). Please share, remix, and distribute as you see fit.

---

If you have a specific feature request or find a bug, [please open a GitHub issue](https://github.com/elevationfitness/elevationfit.com-api-docs/issues/new). We encourage you to fork these docs for local reference and happily accept pull requests with improvements.






