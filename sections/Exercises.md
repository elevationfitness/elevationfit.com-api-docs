# Tracked Workouts

Endpoints:

- [Get All Exercises](#get-all-exercises)
- [Get Exercise By Id](#get-exercise-by-id)


## Get All Exercises

This will return all Exercises that your access token has visibility to.


* `GET https://elevationfit.com/api/v1/xxx/exercises`

## Here are some parms you can pass into this (along with the standard filters)

| key        | value           | Note  |
| ---------- |:---------------:| -----:|
| only      | library | Returns only exercises in your library. Elevation exercises and the ones you added |

## Get Exercise By Id

Use this to get back a full exercise with all the meta data to go with it. 

* `GET https://elevationfit.com/api/v1/xxx/exercises/{ExercisesId}`