# Tracked Workouts

Endpoints:

- [Get All Exercises](#get-all-exercises)
- [Get All Exercise Ids](#get-exercise-ids)
- [Get Exercise By Id](#get-exercise-by-id)


## Get All Exercises

This will return all Exercises that your access token has visibility to.


* `GET https://elevationfit.com/api/v1/xxx/exercises`

## Here are some parms you can pass into this (along with the standard filters)

| key        | value           | Note  |
| ---------- |:---------------:| -----:|
| account_only      | true | Returns only exercises in your library. Elevation exercises and the ones you added |

* `GET https://elevationfit.com/api/v1/xxx/exercises?account_only=true`

## Get All Exercise Ids

Use this to get an array of all exercise ids within the system this account has access to. This is useful for syncing up deletes. Make this API call to get an array of Ids -- Then compare this array against the Ids in the local database. If you find an ID in your local database that is not in this list you can assume it has been deleted. 

* `GET https://elevationfit.com/api/v1/xxx/exercises/ids`

## Get Exercise By Id

Use this to get back a full exercise with all the meta data to go with it. 

* `GET https://elevationfit.com/api/v1/xxx/exercises/{ExercisesId}`