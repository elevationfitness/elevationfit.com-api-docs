# Programs

## Delete Workout Group

This will delete a workout group from a program (currently only support assigned programs not tracked or template programs).

This call returns no data but will return status 204 if all went well. 

* `DELETE https://elevationfit.com/api/v1/xxx/programs/{program_id}/groups/{group_number}`