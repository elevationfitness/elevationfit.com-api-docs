# Assigned Workouts

Endpoints:

- [Track Assigned Workout 100% Complete](#track-assgined-workout-100-complete)
- [Get All Assigned Workout By Id](#get-all-assigned-workout-by-id)
- [Get All Assigned Workouts By User Id](#get-all-assigned-workouts-by-user-id)

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

## Get All Assigned Workout By Id

We use this api call to get one particular Assigned workout 

* `GET https://elevationfit.com/api/v1/xxx/assignedworkouts/{TrackedWorkoutsId}`

###### Example JSON Response

```json
{
	"status": 1,
	"data": {
		"AssignedWorkoutsId": "1082",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "21",
		"AssignedWorkoutsClientId": "45",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "1",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "1 Mile Pyramids (5 miles Total)",
		"AssignedWorkoutsSex": "",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Running",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Quadriceps, Calves, Glutes",
		"AssignedWorkoutsExerciseTypesCsv": "Walking \/ Running",
		"AssignedWorkoutsEquipmentCsv": "Treadmill Machine",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2016-12-23 11:02:01",
		"AssignedWorkoutsUpdatedAt": "2017-03-01 16:45:11",
		"AssignedWorkoutsCreatedAt": "2016-12-23 10:51:50"
	},
	"pages": 0
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/assignedworkouts/890
```

## Get All Assigned Workouts By User Id

We use this api call to assigned Workouts by a particular user.  

* `GET https://elevationfit.com/api/v1/xxx/assignedworkouts/user/{UsersId}`

###### Example JSON Response

```json
{
	"status": 1,
	"data": [{
		"AssignedWorkoutsId": "538",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "71",
		"AssignedWorkoutsClientId": "25",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "6",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "Shoulders And Abs (15 Rep Endurance)",
		"AssignedWorkoutsSex": "",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Set\/Rep Based",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Shoulder, Abdominals, Back",
		"AssignedWorkoutsExerciseTypesCsv": "Body Weight, Machine, Free Weight",
		"AssignedWorkoutsEquipmentCsv": "Pull Up Bar, Adjustable Pulley Machine, Dumbbell",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2016-09-06 22:52:01",
		"AssignedWorkoutsUpdatedAt": "2017-03-03 17:54:24",
		"AssignedWorkoutsCreatedAt": "2016-09-06 22:41:49"
	}, {
		"AssignedWorkoutsId": "1469",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "71",
		"AssignedWorkoutsClientId": "25",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "1",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "20 Min Run",
		"AssignedWorkoutsSex": "Both",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Running",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Quadriceps",
		"AssignedWorkoutsExerciseTypesCsv": "Walking \/ Running",
		"AssignedWorkoutsEquipmentCsv": "No Equip. Needed",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2017-02-01 16:54:01",
		"AssignedWorkoutsUpdatedAt": "2017-03-03 17:54:24",
		"AssignedWorkoutsCreatedAt": "2017-02-01 16:43:21"
	}, {
		"AssignedWorkoutsId": "540",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "71",
		"AssignedWorkoutsClientId": "25",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "2",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "Chest And Abs (15 Rep Endurance)",
		"AssignedWorkoutsSex": "Both",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Set\/Rep Based",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Abdominals, Chest, Shoulder",
		"AssignedWorkoutsExerciseTypesCsv": "Body Weight, Free Weight, Machine",
		"AssignedWorkoutsEquipmentCsv": "Dumbbell, Cable Cross Over, Decline Bench",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2016-09-06 22:52:03",
		"AssignedWorkoutsUpdatedAt": "2017-03-03 17:54:24",
		"AssignedWorkoutsCreatedAt": "2016-09-06 22:41:53"
	}, {
		"AssignedWorkoutsId": "541",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "71",
		"AssignedWorkoutsClientId": "25",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "5",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "Triceps and Back (15 Rep Endurance)",
		"AssignedWorkoutsSex": "Both",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Set\/Rep Based",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Triceps, Shoulder, Back",
		"AssignedWorkoutsExerciseTypesCsv": "Body Weight, Free Weight, Other Cardio",
		"AssignedWorkoutsEquipmentCsv": "Dumbbell, Back Extension Stand, Barbell",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2016-09-06 22:52:04",
		"AssignedWorkoutsUpdatedAt": "2017-03-03 17:54:24",
		"AssignedWorkoutsCreatedAt": "2016-09-06 22:41:56"
	}, {
		"AssignedWorkoutsId": "535",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "71",
		"AssignedWorkoutsClientId": "25",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "3",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "Legs and Back (15 Rep Endurance)",
		"AssignedWorkoutsSex": "Both",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Set\/Rep Based",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Calves, Quadriceps, Glutes",
		"AssignedWorkoutsExerciseTypesCsv": "Machine, Body Weight, Free Weight",
		"AssignedWorkoutsEquipmentCsv": "Machine, Barbell, Exercise Ball",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2016-09-06 22:52:04",
		"AssignedWorkoutsUpdatedAt": "2017-03-03 17:54:24",
		"AssignedWorkoutsCreatedAt": "2016-09-06 22:41:45"
	}, {
		"AssignedWorkoutsId": "534",
		"AssignedWorkoutsAccountId": "4",
		"AssignedWorkoutsProgramId": "71",
		"AssignedWorkoutsClientId": "25",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsProgGroup": "4",
		"AssignedWorkoutsProgOrder": "0",
		"AssignedWorkoutsName": "Biceps and Abs (15 Rep Endurance)",
		"AssignedWorkoutsSex": "Both",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Set\/Rep Based",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsGroupsCsv": "Abdominals, Biceps, Forearm",
		"AssignedWorkoutsExerciseTypesCsv": "Body Weight, Machine, Free Weight",
		"AssignedWorkoutsEquipmentCsv": "Cable Machine, Dumbbell, Exercise Ball",
		"AssignedWorkoutsNote": "",
		"AssignedWorkoutStartDate": "0000-00-00",
		"AssignedWorkoutEndDate": "0000-00-00",
		"AssignedWorkoutMon": "No",
		"AssignedWorkoutTue": "No",
		"AssignedWorkoutWed": "No",
		"AssignedWorkoutThr": "No",
		"AssignedWorkoutFri": "No",
		"AssignedWorkoutSat": "No",
		"AssignedWorkoutSun": "No",
		"AssignedWorkoutPreformDate": "0000-00-00",
		"AssignedWorkoutsStatus": "Active",
		"AssignedWorkoutsOrder": "0",
		"AssignedWorkoutsEmailSentOn": "2016-09-06 22:52:05",
		"AssignedWorkoutsUpdatedAt": "2017-03-03 17:54:24",
		"AssignedWorkoutsCreatedAt": "2016-09-06 22:41:43"
	}],
	"pages": 1
}
```
