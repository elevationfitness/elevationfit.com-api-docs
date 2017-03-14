# Assigned Workouts

Endpoints:

- [Track Assigned Workout 100% Complete](#track-assgined-workout-100-complete)

## Track Assigned Workout 100% Complete

Here we can track an Assigned Workout to 100% complete. This api call returns the Id of the newly tracked workout.

* `POST https://elevationfit.com/api/v1/XXXX/assignedworkouts/{AssignedWorkoutId}/track100percent`

* `POST https://elevationfit.com/api/v1/XXXX/assignedworkouts/{AssignedWorkoutId}/track100percent?return=object`

###### JSON Parms

* TrackedWorkoutsDate - Date you are tracking (optional). If you leave this out it defaults to today. 


###### Curl Example

``` shell
curl -X POST \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ "TrackedWorkoutsDate": "9/18/2016" }' \
  https://elevationfit.com/api/v1/4/assignedworkouts/270/track100percent
```

###### Example JSON Response

```json
{
    "status": 1,
    "data": {
        "Id": 1806
    }
}
```
