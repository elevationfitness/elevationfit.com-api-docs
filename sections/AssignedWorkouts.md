# Assigned Workouts

Endpoints:

- [Track Assigned Workout 100% Complete](#track-assgined-workout-100-complete)
- [Get Assigned Workout By Id](#get-assigned-workout-by-id)
- [Get All Assigned Workouts By User Id](#get-all-assigned-workouts-by-user-id)
- [Create New Assigned Workout Payload](#create-assigned-workout-payload)
- [Delete Assigned Workout](#delete-addigned-workout)

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

## Get Assigned Workout By Id

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

## Create New Assigned Workout Payload

This is the core api call to assign a workout. We post in a rather complex json object to this API. Best to see examples below. There currently is no validation on this API call. Make sure to post in a complete and correct object.

This api call will return the ID (or new ID) of the assigned workout. If you would like more data you can include ```?return=object``` to the url and this API call will return a complete tracked workout object. 

* `POST https://elevationfit.com/api/v1/4/assignedworkouts/payload`

* `POST https://elevationfit.com/api/v1/4/assignedworkouts/payload?return=object`

###### Curl Example

``` shell
curl -X POST \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ json object below..... }' \
  https://elevationfit.com/api/v1/4/assignedworkouts/payload
```

###### JSON Payload Example

Here is a bigger example of the Payload.

``` json
{

	"AssignedWorkoutsProgramId": "3",
	"AssignedWorkoutsClientId": "6",
	"AssignedWorkoutsTrainerId": "6",
	"AssignedWorkoutsProgGroup": "1",
	"AssignedWorkoutsProgOrder": "3",
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
	"AssignedWorkoutsEquipmentCsv": "Dumbbell, No Equip. Needed, Adjustable Pulley Machine",
	"AssignedWorkoutsNote": "",
	"AssignedWorkoutStartDate": "1969-12-30",
	"AssignedWorkoutEndDate": "1969-12-30",
	"AssignedWorkoutMon": "No",
	"AssignedWorkoutTue": "No",
	"AssignedWorkoutWed": "No",
	"AssignedWorkoutThr": "No",
	"AssignedWorkoutFri": "No",
	"AssignedWorkoutSat": "No",
	"AssignedWorkoutSun": "No",
	"AssignedWorkoutPreformDate": "1969-12-30",
	"AssignedWorkoutsOrder": "0",
	"Exercises": {
		"Warmup": [{
			"AssignedExercisesType": "Warmup",
			"AssignedExercisesAttrType": "Distance",
			"AssignedExercisesCol0": "Distance (mi)",
			"AssignedExercisesCol1": "Time (mins)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "asdfasdf",
			"AssignedExercisesExerciseId": "290",
			"AssignedExercisesOrder": "0",
			"Attrs": [{
				"AssignedAttrsAttr0": "0.00",
				"AssignedAttrsAttr1": "600.00",
				"AssignedAttrsAttr2": "30.00",
				"AssignedAttrsAttr3": "75.00",
				"AssignedAttrsOrder": "0"
			}]
		}, {
			"AssignedExercisesType": "Warmup",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Time (mins)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "",
			"AssignedExercisesExerciseId": "1465",
			"AssignedExercisesOrder": "1",
			"Attrs": [{
				"AssignedAttrsAttr0": "10.00",
				"AssignedAttrsAttr1": "0.00",
				"AssignedAttrsAttr2": "30.00",
				"AssignedAttrsAttr3": "75.00",
				"AssignedAttrsOrder": "0"
			}, {
				"AssignedAttrsAttr0": "10.00",
				"AssignedAttrsAttr1": "0.00",
				"AssignedAttrsAttr2": "30.00",
				"AssignedAttrsAttr3": "75.00",
				"AssignedAttrsOrder": "2"
			}, {
				"AssignedAttrsAttr0": "10.00",
				"AssignedAttrsAttr1": "0.00",
				"AssignedAttrsAttr2": "30.00",
				"AssignedAttrsAttr3": "75.00",
				"AssignedAttrsOrder": "3"
			}]
		}],
		"Normal": [{
			"type": "superset",
			"data": [{
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "2",
				"AssignedExercisesNote": "324234",
				"AssignedExercisesExerciseId": "3094",
				"AssignedExercisesOrder": "2",
				"Attrs": [{
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}, {
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "2",
				"AssignedExercisesNote": "asdf",
				"AssignedExercisesExerciseId": "80",
				"AssignedExercisesOrder": "3",
				"Attrs": [{
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "55.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "55.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "55.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}]
		}, {
			"type": "superset",
			"data": [{
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "6",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "3095",
				"AssignedExercisesOrder": "4",
				"Attrs": [{
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "25.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}, {
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "6",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "81",
				"AssignedExercisesOrder": "5",
				"Attrs": [{
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "60.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "60.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "60.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "60.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}]
		}, {
			"type": "superset",
			"data": [{
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Time",
				"AssignedExercisesCol0": "Time (mins)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "4",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "257",
				"AssignedExercisesOrder": "6",
				"Attrs": [{
					"AssignedAttrsAttr0": "60.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "60.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "60.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "60.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}, {
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "4",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "82",
				"AssignedExercisesOrder": "7",
				"Attrs": [{
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "18.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}]
		}, {
			"type": "normal",
			"data": {
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "No",
				"AssignedExercisesSuperNum": "0",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "249",
				"AssignedExercisesOrder": "8",
				"Attrs": [{
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "0.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "0.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "0.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "20.00",
					"AssignedAttrsAttr1": "0.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "0.00",
					"AssignedAttrsOrder": "3"
				}]
			}
		}, {
			"type": "superset",
			"data": [{
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "5",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "346",
				"AssignedExercisesOrder": "9",
				"Attrs": [{
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "50.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}, {
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "5",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "2798",
				"AssignedExercisesOrder": "10",
				"Attrs": [{
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "65.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "65.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "65.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "65.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}, {
				"AssignedExercisesType": "Normal",
				"AssignedExercisesAttrType": "Reps",
				"AssignedExercisesCol0": "Reps (ea)",
				"AssignedExercisesCol1": "Weight (lbs)",
				"AssignedExercisesCol2": "Rest (mins)",
				"AssignedExercisesCol3": "Intensity (%)",
				"AssignedExercisesSuperSet": "Yes",
				"AssignedExercisesSuperNum": "5",
				"AssignedExercisesNote": "",
				"AssignedExercisesExerciseId": "347",
				"AssignedExercisesOrder": "11",
				"Attrs": [{
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "40.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "0"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "40.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "1"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "40.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "2"
				}, {
					"AssignedAttrsAttr0": "15.00",
					"AssignedAttrsAttr1": "40.00",
					"AssignedAttrsAttr2": "30.00",
					"AssignedAttrsAttr3": "75.00",
					"AssignedAttrsOrder": "3"
				}]
			}]
		}],
		"CoolDown": [{
			"AssignedExercisesType": "Cool Down",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "",
			"AssignedExercisesExerciseId": "3097",
			"AssignedExercisesOrder": "12",
			"Attrs": [{
				"AssignedAttrsAttr0": "1.00",
				"AssignedAttrsAttr1": "25.00",
				"AssignedAttrsAttr2": "60.00",
				"AssignedAttrsAttr3": "75.00",
				"AssignedAttrsOrder": "1"
			}]
		}, {
			"AssignedExercisesType": "Cool Down",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "",
			"AssignedExercisesExerciseId": "34314",
			"AssignedExercisesOrder": "13",
			"Attrs": [{
				"AssignedAttrsAttr0": "1.00",
				"AssignedAttrsAttr1": "25.00",
				"AssignedAttrsAttr2": "60.00",
				"AssignedAttrsAttr3": "75.00",
				"AssignedAttrsOrder": "1"
			}]
		}]
	}
}
```

## Delete Assigned Workout

This is a DELETE method for removing an assigned workout. 

* `DELETE https://elevationfit.com/api/v1/4/assignedworkouts/{AssignedWorkoutsId}`

###### Curl Example

``` shell
curl -X DELETE \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ json object below..... }' \
  https://elevationfit.com/api/v1/4/assignedworkouts/{AssignedWorkoutsId}
```