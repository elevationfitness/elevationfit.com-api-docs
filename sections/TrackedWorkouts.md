# Tracked Workouts

Endpoints:

- [Get All Tracked Workouts](#get-all-tracked-workouts)
- [Get Tracked Workout By Id](#get-tracked-workout-by-id)
- [Get All Tracked Workouts By User Id](#get-all-tracked-workouts-by-user-id)
- [Get All Tracked Workout By Assigned Workout Id And Date](#get-all-tracked-workouts-by-assigned-workout-id-and-date)
- [Return A Complete Tracked Workout Object](#return-a-complete-tracked-workout-object)
- [Create New Tracked Workout - Payload](#create-new-tracked-workout-payload)


## Get All Tracked Workouts

This typically is a rather big call. This will return all Tracked Workouts that your access token has visibility to. If you are an account admin this will be every Tracked Workout in the system.


* `GET https://elevationfit.com/api/v1/xxx/trackedworkouts`

###### Example JSON Response

```json
{
	"status": 1,
	"data": [
      {
        "TrackedWorkoutsId": 890,
        "TrackedWorkoutsAccountId": 4,
        "TrackedWorkoutsProgramId": 0,
        "TrackedWorkoutsDate": "2016-11-12",
        "TrackedWorkoutsGroupsCsv": "Chest, Shoulder, Lats",
        "TrackedWorkoutsEquipmentCsv": "No Equip. Needed",
        "TrackedWorkoutsExerciseTypesCsv": "Swimming",
        "AssignedWorkoutsClientId": 6,
        "AssignedWorkoutsTrainerId": 6,
        "AssignedWorkoutsId": 717,
        "AssignedWorkoutsProgramId": 0,
        "AssignedWorkoutsName": "1750yds Freestyle Swim",
        "AssignedWorkoutsSex": "Both",
        "AssignedWorkoutsAgeGroup": "", 
        "AssignedWorkoutsPurpose": "", 
        "AssignedWorkoutsSystem": "", 
        "AssignedWorkoutsModality": "Swimming",
        "AssignedWorkoutsSkillLevel": "",
        "AssignedWorkoutsPeriod": 0,
        "AssignedWorkoutsRecovery": 0,
        "AssignedWorkoutsPerWeek": 0,
        "AssignedWorkoutsNote": "",
        "TrackedWorkoutsRecordedTime": 0,
        "AssignedWorkoutsOrder": 0,
        "TrackedWorkoutsEmailSentOn": "2016-11-14 10:53:02",
        "TrackedWorkoutsUpdatedAt": "2016-11-14 10:53:02",
        "TrackedWorkoutsCreatedAt": "2016-11-14 10:42:24"  	
      }
	],
	"pages": 30
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts
```

## Get All Tracked Workout By Id

We use this api call to get one particular Tracked workout 

* `GET https://elevationfit.com/api/v1/xxx/trackedworkouts/{TrackedWorkoutsId}`

###### Example JSON Response

```json
{
	"status": 1,
	"data": {
      "TrackedWorkoutsId": 890,
      "TrackedWorkoutsAccountId": 4,
      "TrackedWorkoutsProgramId": 0,
      "TrackedWorkoutsDate": "2016-11-12",
      "TrackedWorkoutsGroupsCsv": "Chest, Shoulder, Lats",
      "TrackedWorkoutsEquipmentCsv": "No Equip. Needed",
      "TrackedWorkoutsExerciseTypesCsv": "Swimming",
      "AssignedWorkoutsClientId": 6,
      "AssignedWorkoutsTrainerId": 6,
      "AssignedWorkoutsId": 717,
      "AssignedWorkoutsProgramId": 0,
      "AssignedWorkoutsName": "1750yds Freestyle Swim",
      "AssignedWorkoutsSex": "Both",
      "AssignedWorkoutsAgeGroup": "", 
      "AssignedWorkoutsPurpose": "", 
      "AssignedWorkoutsSystem": "", 
      "AssignedWorkoutsModality": "Swimming",
      "AssignedWorkoutsSkillLevel": "",
      "AssignedWorkoutsPeriod": 0,
      "AssignedWorkoutsRecovery": 0,
      "AssignedWorkoutsPerWeek": 0,
      "AssignedWorkoutsNote": "",
      "TrackedWorkoutsRecordedTime": 0,
      "AssignedWorkoutsOrder": 0,
      "TrackedWorkoutsEmailSentOn": "2016-11-14 10:53:02",
      "TrackedWorkoutsUpdatedAt": "2016-11-14 10:53:02",
      "TrackedWorkoutsCreatedAt": "2016-11-14 10:42:24"  	
	},
	"pages": 0
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts/890
```

## Get All Tracked Workout By User Id

We use this api call to Tracked Workouts by a particular user.  

* `GET https://elevationfit.com/api/v1/xxx/trackedworkouts/user/{UsersId}`

###### Example JSON Response

```json
{
	"status": 1,
	"data": [
      {
        "TrackedWorkoutsId": 890,
        "TrackedWorkoutsAccountId": 4,
        "TrackedWorkoutsProgramId": 0,
        "TrackedWorkoutsDate": "2016-11-12",
        "TrackedWorkoutsGroupsCsv": "Chest, Shoulder, Lats",
        "TrackedWorkoutsEquipmentCsv": "No Equip. Needed",
        "TrackedWorkoutsExerciseTypesCsv": "Swimming",
        "AssignedWorkoutsClientId": 6,
        "AssignedWorkoutsTrainerId": 6,
        "AssignedWorkoutsId": 717,
        "AssignedWorkoutsProgramId": 0,
        "AssignedWorkoutsName": "1750yds Freestyle Swim",
        "AssignedWorkoutsSex": "Both",
        "AssignedWorkoutsAgeGroup": "", 
        "AssignedWorkoutsPurpose": "", 
        "AssignedWorkoutsSystem": "", 
        "AssignedWorkoutsModality": "Swimming",
        "AssignedWorkoutsSkillLevel": "",
        "AssignedWorkoutsPeriod": 0,
        "AssignedWorkoutsRecovery": 0,
        "AssignedWorkoutsPerWeek": 0,
        "AssignedWorkoutsNote": "",
        "TrackedWorkoutsRecordedTime": 0,
        "AssignedWorkoutsOrder": 0,
        "TrackedWorkoutsEmailSentOn": "2016-11-14 10:53:02",
        "TrackedWorkoutsUpdatedAt": "2016-11-14 10:53:02",
        "TrackedWorkoutsCreatedAt": "2016-11-14 10:42:24"  	
      }
	],
	"pages": 0
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts/user/6
```

## Get All Tracked Workout By Assigned Workout Id And Date

We typically use this call when we start to track a workout. Just before starting to track an Assigned Workout on a particular day you call this API call. If it returns empty you know there has not been any tracking for this Assigned Workout / Date combination. If empty you know you need to call [Get Assigned Workout By Id](#get-assigned-workout-by-id) and use that as a start for your new tracking. 

If this API call returns data you know there has already been a tracking. In this case you might be calling this api just for the data or more likely you are calling this api to use to update (edit) a workout tracking. 

* `GET https://elevationfit.com/api/v1/xxx/trackedworkouts/assignedworkout/{AssignedWorkoutsId}/date/{TrackedWorkoutsDate}`

###### Example JSON Response

```json
{
	"status": 1,
	"data": {
      "TrackedWorkoutsId": 890,
      "TrackedWorkoutsAccountId": 4,
      "TrackedWorkoutsProgramId": 0,
      "TrackedWorkoutsDate": "2016-11-12",
      "TrackedWorkoutsGroupsCsv": "Chest, Shoulder, Lats",
      "TrackedWorkoutsEquipmentCsv": "No Equip. Needed",
      "TrackedWorkoutsExerciseTypesCsv": "Swimming",
      "AssignedWorkoutsClientId": 6,
      "AssignedWorkoutsTrainerId": 6,
      "AssignedWorkoutsId": 717,
      "AssignedWorkoutsProgramId": 0,
      "AssignedWorkoutsName": "1750yds Freestyle Swim",
      "AssignedWorkoutsSex": "Both",
      "AssignedWorkoutsAgeGroup": "", 
      "AssignedWorkoutsPurpose": "", 
      "AssignedWorkoutsSystem": "", 
      "AssignedWorkoutsModality": "Swimming",
      "AssignedWorkoutsSkillLevel": "",
      "AssignedWorkoutsPeriod": 0,
      "AssignedWorkoutsRecovery": 0,
      "AssignedWorkoutsPerWeek": 0,
      "AssignedWorkoutsNote": "",
      "TrackedWorkoutsRecordedTime": 0,
      "AssignedWorkoutsOrder": 0,
      "TrackedWorkoutsEmailSentOn": "2016-11-14 10:53:02",
      "TrackedWorkoutsUpdatedAt": "2016-11-14 10:53:02",
      "TrackedWorkoutsCreatedAt": "2016-11-14 10:42:24"  	
	},
	"pages": 0
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts/assignedworkout/717/date/2016-11-12
```

## Return A Complete Tracked Workout Object

A Workout within Elevation is layered. All the example calls above just returns the top layer. A complete workout is: the workout data, all the exercises that goes with it, and the attributes that goes with each exercise. 

```TrackedWorkouts -> TrackedExercises -> TrackedAttrs```

Any TrackedWorkout call that is designed to return one tracked workout such as [Get Tracked Workout By Id](#get-tracked-workout-by-id) has an option of returning the entire layered workout. You simply add ```?full=true``` to the end of the call. 

As you can imagine this call is very expensive. Make sure you really need this API call when you call it. Sometimes you can get away with combining other api calls into one. 

For our example here lets use the [Get Tracked Workout By Id](#get-tracked-workout-by-id) API call. 

* `GET https://elevationfit.com/api/v1/xxx/trackedworkouts/{TrackedWorkoutsId}?full=true`

###### Example JSON Response

```json
{
	"status": 1,
	"data": {
		"TrackedWorkoutsId": "890",
		"TrackedWorkoutsAccountId": "4",
		"TrackedWorkoutsProgramId": "0",
		"TrackedWorkoutsDate": "2016-11-12",
		"TrackedWorkoutsGroupsCsv": "Chest, Shoulder, Lats",
		"TrackedWorkoutsEquipmentCsv": "No Equip. Needed",
		"TrackedWorkoutsExerciseTypesCsv": "Swimming",
		"AssignedWorkoutsClientId": "6",
		"AssignedWorkoutsTrainerId": "6",
		"AssignedWorkoutsId": "717",
		"AssignedWorkoutsProgramId": "0",
		"AssignedWorkoutsName": "1750yds Freestyle Swim",
		"AssignedWorkoutsSex": "Both",
		"AssignedWorkoutsAgeGroup": "",
		"AssignedWorkoutsPurpose": "",
		"AssignedWorkoutsSystem": "",
		"AssignedWorkoutsModality": "Swimming",
		"AssignedWorkoutsSkillLevel": "",
		"AssignedWorkoutsPeriod": "0",
		"AssignedWorkoutsRecovery": "0",
		"AssignedWorkoutsPerWeek": "0",
		"AssignedWorkoutsNote": "",
		"TrackedWorkoutsRecordedTime": "0",
		"AssignedWorkoutsOrder": "0",
		"TrackedWorkoutsEmailSentOn": "2016-11-14 10:53:02",
		"TrackedWorkoutsUpdatedAt": "2016-11-14 10:53:02",
		"TrackedWorkoutsCreatedAt": "2016-11-14 10:42:24",
		"UsersId": "6",
		"UsersAccountId": "4",
		"UsersFirstName": "Matt",
		"UsersLastName": "Davidson",
		"UsersEmail": "matt@elevationfit.com",
		"UsersUserType": "Admin",
		"UsersLastActivity": "2017-03-06 12:56:00",
		"UsersUpdatedAt": "2017-03-06 20:56:00",
		"UsersCreatedAt": "2015-08-17 23:58:13",
		"TrackedWorkoutsDate_df1": "11\/12\/2016",
		"TrackedWorkoutsDate_df2": "11\/12\/2016",
		"TrackedWorkoutsDate_df3": "4 months ago",
		"TrackedWorkoutsDate_df4": "11\/12\/16",
		"TrackedWorkoutsDate_df5": "Nov 12",
		"Exercises": [{
			"TrackedExercisesId": "9346",
			"TrackedExercisesAccountId": "4",
			"TrackedExercisesWorkoutId": "890",
			"AssignedExercisesId": "5222",
			"AssignedExercisesWorkoutId": "717",
			"AssignedExercisesExerciseId": "328",
			"AssignedExercisesOrder": "0",
			"AssignedExercisesType": "Cool Down",
			"AssignedExercisesAttrType": "Distance",
			"AssignedExercisesCol0": "Distance (mi)",
			"AssignedExercisesCol1": "Time (mins)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"TrackedExercisesUpdatedAt": "2016-11-14 10:42:24",
			"TrackedExercisesCreatedAt": "2016-11-14 10:42:24",
			"Attrs": [{
				"TrackedAttrsId": "28802",
				"TrackedAttrsAccountId": "4",
				"AssignedAttrsId": "16624",
				"TrackedAttrsExerciseId": "9346",
				"AssignedAttrsExerciseId": "5222",
				"AssignedAttrsOrder": "0",
				"TrackedAttrsOrder": "0",
				"AssignedAttrsAttr0": 250,
				"AssignedAttrsAttr1": "0:00",
				"AssignedAttrsAttr2": "1:00",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 250,
				"TrackedAttrsAttr1": "0:00",
				"TrackedAttrsAttr2": "1:00",
				"TrackedAttrsAttr3": 75,
				"TrackedAttrsUpdatedAt": "2016-11-14 10:42:24",
				"TrackedAttrsCreatedAt": "2016-11-14 10:42:24",
				"AssignedAttrsAttr0Raw": 250,
				"AssignedAttrsAttr1Raw": 0,
				"AssignedAttrsAttr2Raw": 60,
				"AssignedAttrsAttr3Raw": 75,
				"TrackedAttrsAttr0Raw": 250,
				"TrackedAttrsAttr1Raw": 0,
				"TrackedAttrsAttr2Raw": 60,
				"TrackedAttrsAttr3Raw": 75
			}],
			"PercentComplete": 100,
			"Exercise": {
				"ExercisesId": "328",
				"ExercisesName": "Freestyle",
				"ExercisesDisplayName": "Freestyle",
				"ExercisesEquipCsv": "No Equip. Needed",
				"ExercisesThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/exercises\/e08295a8d9fc98fdbbe69126a3f07c16_thumb.jpeg",
				"ExercisesImage": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/exercises\/e08295a8d9fc98fdbbe69126a3f07c16.jpeg",
				"ExerciseCategoriesClass": "Cardio",
				"ExerciseCategoriesType": "Swimming",
				"ExercisesTeral": "Unilateral",
				"ExercisesGroupsCsv": "Lats, Shoulder, Chest",
				"ExercisesNameEllipsis20": "Freestyle",
				"ExercisesNameEllipsis25": "Freestyle",
				"ExercisesNameEllipsis50": "Freestyle",
				"Parent": [],
				"Sequences": [],
				"Equipment": [{
					"EquipmentId": "68",
					"EquipmentName": "No Equip. Needed"
				}],
				"PrimaryMuscles": [{
					"MusclesId": "92",
					"MusclesMuscle": "Latissimus Dorsi"
				}, {
					"MusclesId": "216",
					"MusclesMuscle": "Teres Major"
				}, {
					"MusclesId": "28",
					"MusclesMuscle": "Deltoid"
				}, {
					"MusclesId": "131",
					"MusclesMuscle": "Pectoralis Major"
				}],
				"SecondaryMuscles": [{
					"MusclesId": "129",
					"MusclesMuscle": "Palmaris Longus"
				}, {
					"MusclesId": "154",
					"MusclesMuscle": "Quadriceps Femoris"
				}, {
					"MusclesId": "79",
					"MusclesMuscle": "Iliopsoas"
				}, {
					"MusclesId": "114",
					"MusclesMuscle": "Obliques External"
				}, {
					"MusclesId": "115",
					"MusclesMuscle": "Obliques Internal"
				}, {
					"MusclesId": "156",
					"MusclesMuscle": "Rectus Abdominis"
				}],
				"Movements": [{
					"MovementsId": "222743",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Reach",
					"MovementsActions": ["While kicking the legs up and down with a focus on using the quads and hip flexors, reach one arm out of the water and over the head.", "Focus on using the deltoid to raise the arm and keep it close to the water as it extends.", "Keep the shoulders retracted as the arm reaches to avoid injury to the shoulder joint."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/c23a322dfb144a8de49a1f15eca883cc.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/c23a322dfb144a8de49a1f15eca883cc_thumb.jpeg",
					"MovementsOrder": "0",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}, {
					"MovementsId": "222744",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Pull",
					"MovementsActions": ["Bring the first arm back into the water, keeping the hand in a cupped position.", "Use the lats and pec muscles to pull the hand down and towards the naval.", "At the same time bring the opposite arm out of the water and begin to reach as in the starting position.", "The legs should continue kicking throughout the exercise.", "Take a breath every 3 strokes.  Make sure when breathing that the breath is started once the arm has moved.  Only half the face should come out of the water.", "Once the reaching arm starts rotating back, the face should start to move back into the water."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/598b22f67e0af9ed925c5ade3f991382.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/598b22f67e0af9ed925c5ade3f991382_thumb.jpeg",
					"MovementsOrder": "1",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}, {
					"MovementsId": "222745",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Flip Turn",
					"MovementsActions": ["At two arm lengths away from the pool wall, extend one hand out while pulling the other down towards the side of your body.", "Pull the other hand down forcefully to gain momentum and accelerate towards the wall.", "At one arm length away, start to turn the body, leading forward with the head as if to do a summersault.", "Complete a somersault so that the feet are facing the wall.", "As the somersault finishes the feet should gently touch the wall.", "Push away from the wall with the hands above the head and touching.", "The head should be down, with the arms on the ears."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/6b9e2bfca779ba0071c77bed25e72056.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/6b9e2bfca779ba0071c77bed25e72056_thumb.jpeg",
					"MovementsOrder": "2",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}]
			}
		}, {
			"TrackedExercisesId": "9345",
			"TrackedExercisesAccountId": "4",
			"TrackedExercisesWorkoutId": "890",
			"AssignedExercisesId": "5221",
			"AssignedExercisesWorkoutId": "717",
			"AssignedExercisesExerciseId": "328",
			"AssignedExercisesOrder": "0",
			"AssignedExercisesType": "Normal",
			"AssignedExercisesAttrType": "Distance",
			"AssignedExercisesCol0": "Distance (yds)",
			"AssignedExercisesCol1": "Time (mins)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"TrackedExercisesUpdatedAt": "2016-11-14 10:42:24",
			"TrackedExercisesCreatedAt": "2016-11-14 10:42:24",
			"Attrs": [{
				"TrackedAttrsId": "28801",
				"TrackedAttrsAccountId": "4",
				"AssignedAttrsId": "16623",
				"TrackedAttrsExerciseId": "9345",
				"AssignedAttrsExerciseId": "5221",
				"AssignedAttrsOrder": "0",
				"TrackedAttrsOrder": "0",
				"AssignedAttrsAttr0": 1250,
				"AssignedAttrsAttr1": "0:00",
				"AssignedAttrsAttr2": "2:00",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 1250,
				"TrackedAttrsAttr1": "0:00",
				"TrackedAttrsAttr2": "2:00",
				"TrackedAttrsAttr3": 75,
				"TrackedAttrsUpdatedAt": "2016-11-14 10:42:24",
				"TrackedAttrsCreatedAt": "2016-11-14 10:42:24",
				"AssignedAttrsAttr0Raw": 1250,
				"AssignedAttrsAttr1Raw": 0,
				"AssignedAttrsAttr2Raw": 120,
				"AssignedAttrsAttr3Raw": 75,
				"TrackedAttrsAttr0Raw": 1250,
				"TrackedAttrsAttr1Raw": 0,
				"TrackedAttrsAttr2Raw": 120,
				"TrackedAttrsAttr3Raw": 75
			}],
			"PercentComplete": 100,
			"Exercise": {
				"ExercisesId": "328",
				"ExercisesName": "Freestyle",
				"ExercisesDisplayName": "Freestyle",
				"ExercisesEquipCsv": "No Equip. Needed",
				"ExercisesThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/exercises\/e08295a8d9fc98fdbbe69126a3f07c16_thumb.jpeg",
				"ExercisesImage": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/exercises\/e08295a8d9fc98fdbbe69126a3f07c16.jpeg",
				"ExerciseCategoriesClass": "Cardio",
				"ExerciseCategoriesType": "Swimming",
				"ExercisesTeral": "Unilateral",
				"ExercisesGroupsCsv": "Lats, Shoulder, Chest",
				"ExercisesNameEllipsis20": "Freestyle",
				"ExercisesNameEllipsis25": "Freestyle",
				"ExercisesNameEllipsis50": "Freestyle",
				"Parent": [],
				"Sequences": [],
				"Equipment": [{
					"EquipmentId": "68",
					"EquipmentName": "No Equip. Needed"
				}],
				"PrimaryMuscles": [{
					"MusclesId": "92",
					"MusclesMuscle": "Latissimus Dorsi"
				}, {
					"MusclesId": "216",
					"MusclesMuscle": "Teres Major"
				}, {
					"MusclesId": "28",
					"MusclesMuscle": "Deltoid"
				}, {
					"MusclesId": "131",
					"MusclesMuscle": "Pectoralis Major"
				}],
				"SecondaryMuscles": [{
					"MusclesId": "129",
					"MusclesMuscle": "Palmaris Longus"
				}, {
					"MusclesId": "154",
					"MusclesMuscle": "Quadriceps Femoris"
				}, {
					"MusclesId": "79",
					"MusclesMuscle": "Iliopsoas"
				}, {
					"MusclesId": "114",
					"MusclesMuscle": "Obliques External"
				}, {
					"MusclesId": "115",
					"MusclesMuscle": "Obliques Internal"
				}, {
					"MusclesId": "156",
					"MusclesMuscle": "Rectus Abdominis"
				}],
				"Movements": [{
					"MovementsId": "222743",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Reach",
					"MovementsActions": ["While kicking the legs up and down with a focus on using the quads and hip flexors, reach one arm out of the water and over the head.", "Focus on using the deltoid to raise the arm and keep it close to the water as it extends.", "Keep the shoulders retracted as the arm reaches to avoid injury to the shoulder joint."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/c23a322dfb144a8de49a1f15eca883cc.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/c23a322dfb144a8de49a1f15eca883cc_thumb.jpeg",
					"MovementsOrder": "0",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}, {
					"MovementsId": "222744",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Pull",
					"MovementsActions": ["Bring the first arm back into the water, keeping the hand in a cupped position.", "Use the lats and pec muscles to pull the hand down and towards the naval.", "At the same time bring the opposite arm out of the water and begin to reach as in the starting position.", "The legs should continue kicking throughout the exercise.", "Take a breath every 3 strokes.  Make sure when breathing that the breath is started once the arm has moved.  Only half the face should come out of the water.", "Once the reaching arm starts rotating back, the face should start to move back into the water."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/598b22f67e0af9ed925c5ade3f991382.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/598b22f67e0af9ed925c5ade3f991382_thumb.jpeg",
					"MovementsOrder": "1",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}, {
					"MovementsId": "222745",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Flip Turn",
					"MovementsActions": ["At two arm lengths away from the pool wall, extend one hand out while pulling the other down towards the side of your body.", "Pull the other hand down forcefully to gain momentum and accelerate towards the wall.", "At one arm length away, start to turn the body, leading forward with the head as if to do a summersault.", "Complete a somersault so that the feet are facing the wall.", "As the somersault finishes the feet should gently touch the wall.", "Push away from the wall with the hands above the head and touching.", "The head should be down, with the arms on the ears."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/6b9e2bfca779ba0071c77bed25e72056.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/6b9e2bfca779ba0071c77bed25e72056_thumb.jpeg",
					"MovementsOrder": "2",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}]
			}
		}, {
			"TrackedExercisesId": "9344",
			"TrackedExercisesAccountId": "4",
			"TrackedExercisesWorkoutId": "890",
			"AssignedExercisesId": "5220",
			"AssignedExercisesWorkoutId": "717",
			"AssignedExercisesExerciseId": "328",
			"AssignedExercisesOrder": "0",
			"AssignedExercisesType": "Warmup",
			"AssignedExercisesAttrType": "Distance",
			"AssignedExercisesCol0": "Distance (yds)",
			"AssignedExercisesCol1": "Time (mins)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"TrackedExercisesUpdatedAt": "2016-11-14 10:42:24",
			"TrackedExercisesCreatedAt": "2016-11-14 10:42:24",
			"Attrs": [{
				"TrackedAttrsId": "28800",
				"TrackedAttrsAccountId": "4",
				"AssignedAttrsId": "16622",
				"TrackedAttrsExerciseId": "9344",
				"AssignedAttrsExerciseId": "5220",
				"AssignedAttrsOrder": "0",
				"TrackedAttrsOrder": "0",
				"AssignedAttrsAttr0": 250,
				"AssignedAttrsAttr1": "0:00",
				"AssignedAttrsAttr2": "0:00",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 250,
				"TrackedAttrsAttr1": "0:00",
				"TrackedAttrsAttr2": "0:00",
				"TrackedAttrsAttr3": 75,
				"TrackedAttrsUpdatedAt": "2016-11-14 10:42:24",
				"TrackedAttrsCreatedAt": "2016-11-14 10:42:24",
				"AssignedAttrsAttr0Raw": 250,
				"AssignedAttrsAttr1Raw": 0,
				"AssignedAttrsAttr2Raw": 0,
				"AssignedAttrsAttr3Raw": 75,
				"TrackedAttrsAttr0Raw": 250,
				"TrackedAttrsAttr1Raw": 0,
				"TrackedAttrsAttr2Raw": 0,
				"TrackedAttrsAttr3Raw": 75
			}],
			"PercentComplete": 100,
			"Exercise": {
				"ExercisesId": "328",
				"ExercisesName": "Freestyle",
				"ExercisesDisplayName": "Freestyle",
				"ExercisesEquipCsv": "No Equip. Needed",
				"ExercisesThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/exercises\/e08295a8d9fc98fdbbe69126a3f07c16_thumb.jpeg",
				"ExercisesImage": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/exercises\/e08295a8d9fc98fdbbe69126a3f07c16.jpeg",
				"ExerciseCategoriesClass": "Cardio",
				"ExerciseCategoriesType": "Swimming",
				"ExercisesTeral": "Unilateral",
				"ExercisesGroupsCsv": "Lats, Shoulder, Chest",
				"ExercisesNameEllipsis20": "Freestyle",
				"ExercisesNameEllipsis25": "Freestyle",
				"ExercisesNameEllipsis50": "Freestyle",
				"Parent": [],
				"Sequences": [],
				"Equipment": [{
					"EquipmentId": "68",
					"EquipmentName": "No Equip. Needed"
				}],
				"PrimaryMuscles": [{
					"MusclesId": "92",
					"MusclesMuscle": "Latissimus Dorsi"
				}, {
					"MusclesId": "216",
					"MusclesMuscle": "Teres Major"
				}, {
					"MusclesId": "28",
					"MusclesMuscle": "Deltoid"
				}, {
					"MusclesId": "131",
					"MusclesMuscle": "Pectoralis Major"
				}],
				"SecondaryMuscles": [{
					"MusclesId": "129",
					"MusclesMuscle": "Palmaris Longus"
				}, {
					"MusclesId": "154",
					"MusclesMuscle": "Quadriceps Femoris"
				}, {
					"MusclesId": "79",
					"MusclesMuscle": "Iliopsoas"
				}, {
					"MusclesId": "114",
					"MusclesMuscle": "Obliques External"
				}, {
					"MusclesId": "115",
					"MusclesMuscle": "Obliques Internal"
				}, {
					"MusclesId": "156",
					"MusclesMuscle": "Rectus Abdominis"
				}],
				"Movements": [{
					"MovementsId": "222743",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Reach",
					"MovementsActions": ["While kicking the legs up and down with a focus on using the quads and hip flexors, reach one arm out of the water and over the head.", "Focus on using the deltoid to raise the arm and keep it close to the water as it extends.", "Keep the shoulders retracted as the arm reaches to avoid injury to the shoulder joint."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/c23a322dfb144a8de49a1f15eca883cc.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/c23a322dfb144a8de49a1f15eca883cc_thumb.jpeg",
					"MovementsOrder": "0",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}, {
					"MovementsId": "222744",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Pull",
					"MovementsActions": ["Bring the first arm back into the water, keeping the hand in a cupped position.", "Use the lats and pec muscles to pull the hand down and towards the naval.", "At the same time bring the opposite arm out of the water and begin to reach as in the starting position.", "The legs should continue kicking throughout the exercise.", "Take a breath every 3 strokes.  Make sure when breathing that the breath is started once the arm has moved.  Only half the face should come out of the water.", "Once the reaching arm starts rotating back, the face should start to move back into the water."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/598b22f67e0af9ed925c5ade3f991382.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/598b22f67e0af9ed925c5ade3f991382_thumb.jpeg",
					"MovementsOrder": "1",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}, {
					"MovementsId": "222745",
					"MovementsExerciseId": "328",
					"MovementsTitle": "Flip Turn",
					"MovementsActions": ["At two arm lengths away from the pool wall, extend one hand out while pulling the other down towards the side of your body.", "Pull the other hand down forcefully to gain momentum and accelerate towards the wall.", "At one arm length away, start to turn the body, leading forward with the head as if to do a summersault.", "Complete a somersault so that the feet are facing the wall.", "As the somersault finishes the feet should gently touch the wall.", "Push away from the wall with the hands above the head and touching.", "The head should be down, with the arms on the ears."],
					"MovementsFile": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/6b9e2bfca779ba0071c77bed25e72056.jpeg",
					"MovementsThumb": "https:\/\/d1bxnu833a1mwo.cloudfront.net\/movements\/6b9e2bfca779ba0071c77bed25e72056_thumb.jpeg",
					"MovementsOrder": "2",
					"MovementsCreatedAt": "2017-01-24 10:02:17",
					"MovementsUpdatedAt": "0000-00-00 00:00:00"
				}]
			}
		}],
		"Trainer": {
			"UsersId": "6",
			"UsersFirstName": "Matt",
			"UsersLastName": "Davidson",
			"UsersEmail": "matt@elevationfit.com"
		},
		"PercentComplete": 100,
		"Duration": "3"
	}
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/trackedworkouts/890?full=true
```

## Create New Tracked Workout - Payload

This is the core api call to track a workout. We post in a rather complex json object to this API. Best to see the two examples below. There currently is no validation on this API call. Make sure to post in a complete and correct object.

One thing to note is we do not update tracked workouts. We delete the old one and replace with a new one. You use this call for tracking a new workout and for "updating" (delete and insert).

This api call will return the ID (or new ID) of the tracked workout. If you would like more data you can include ```?return=object``` to the url and this API call will return a complete tracked workout object. 

* `POST https://elevationfit.com/api/v1/4/trackedworkouts/payload`

* `POST https://elevationfit.com/api/v1/4/trackedworkouts/payload?return=object`

###### Curl Example

``` shell
curl -X POST \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ json object below..... }' \
  https://elevationfit.com/api/v1/4/trackedworkouts/payload
```

###### JSON Payload Example

Here is a bigger example of the Payload : https://gist.github.com/cloudmanic/6b267cacabd58432b9af715a0863972e

``` json
{
	"AssignedWorkoutsId": "270",
	"AssignedWorkoutsClientId": "6",
	"TrackedWorkoutsDate": "03\/08\/2017",
	"Exercises": {
		"Warmup": [{
			"TrackedExercisesId": "17942",
			"AssignedExercisesAttrType": "Distance",
			"AssignedExercisesCol0": "Distance (mi)",
			"AssignedExercisesCol1": "Time (mins)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesExerciseId": "445",
			"AssignedExercisesId": "13748",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"AssignedExercisesOrder": 0,
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesType": "Warmup",
			"AssignedExercisesWorkoutId": "270",
			"Attrs": [{
				"AssignedAttrsAttr0": 2,
				"AssignedAttrsAttr1": "14:00",
				"AssignedAttrsAttr2": "1:00",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 0,
				"TrackedAttrsAttr1": "14:00",
				"TrackedAttrsAttr2": "0:00",
				"TrackedAttrsAttr3": 0,
				"AssignedAttrsId": "42492",
				"AssignedAttrsExerciseId": "13748",
				"AssignedAttrsOrder": 0
			}]
		}],
		"Normal": [{
			"TrackedExercisesId": "17946",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesExerciseId": "132",
			"AssignedExercisesId": "2012",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"AssignedExercisesOrder": 4,
			"AssignedExercisesSuperNum": "8",
			"AssignedExercisesSuperSet": "Yes",
			"AssignedExercisesType": "Normal",
			"AssignedExercisesWorkoutId": "270",
			"Attrs": [{
				"AssignedAttrsAttr0": 15,
				"AssignedAttrsAttr1": 20,
				"AssignedAttrsAttr2": "0:30",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 15,
				"TrackedAttrsAttr1": 20,
				"TrackedAttrsAttr2": "0:30",
				"TrackedAttrsAttr3": 75,
				"AssignedAttrsId": "27603",
				"AssignedAttrsExerciseId": "2012",
				"AssignedAttrsOrder": 0
			}, {
				"AssignedAttrsAttr0": 15,
				"AssignedAttrsAttr1": 20,
				"AssignedAttrsAttr2": "0:30",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 15,
				"TrackedAttrsAttr1": 20,
				"TrackedAttrsAttr2": "0:30",
				"TrackedAttrsAttr3": 75,
				"AssignedAttrsId": "29322",
				"AssignedAttrsExerciseId": "2012",
				"AssignedAttrsOrder": 1
			}]
		}, {
			"TrackedExercisesId": "17947",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesExerciseId": "141",
			"AssignedExercisesId": "6861",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"AssignedExercisesOrder": 5,
			"AssignedExercisesSuperNum": "8",
			"AssignedExercisesSuperSet": "Yes",
			"AssignedExercisesType": "Normal",
			"AssignedExercisesWorkoutId": "270",
			"Attrs": [{
				"AssignedAttrsAttr0": 15,
				"AssignedAttrsAttr1": 25,
				"AssignedAttrsAttr2": "0:30",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 0,
				"TrackedAttrsAttr1": 0,
				"TrackedAttrsAttr2": "0:00",
				"TrackedAttrsAttr3": 0,
				"AssignedAttrsId": "21212",
				"AssignedAttrsExerciseId": "6861",
				"AssignedAttrsOrder": 0
			}, {
				"AssignedAttrsAttr0": 15,
				"AssignedAttrsAttr1": 25,
				"AssignedAttrsAttr2": "0:30",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 0,
				"TrackedAttrsAttr1": 0,
				"TrackedAttrsAttr2": "0:00",
				"TrackedAttrsAttr3": 0,
				"AssignedAttrsId": "29382",
				"AssignedAttrsExerciseId": "6861",
				"AssignedAttrsOrder": 1
			}]
		}],
		"Cooldown": [{
			"TrackedExercisesId": "17956",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesExerciseId": "34318",
			"AssignedExercisesId": "13752",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"AssignedExercisesOrder": 24,
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesType": "Cool Down",
			"AssignedExercisesWorkoutId": "270",
			"Attrs": [{
				"AssignedAttrsAttr0": 1,
				"AssignedAttrsAttr1": 25,
				"AssignedAttrsAttr2": "1:00",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 0,
				"TrackedAttrsAttr1": 0,
				"TrackedAttrsAttr2": "0:00",
				"TrackedAttrsAttr3": 0,
				"AssignedAttrsId": "42500",
				"AssignedAttrsExerciseId": "13752",
				"AssignedAttrsOrder": 0
			}]
		}, {
			"TrackedExercisesId": "17943",
			"AssignedExercisesAttrType": "Reps",
			"AssignedExercisesCol0": "Reps (ea)",
			"AssignedExercisesCol1": "Weight (lbs)",
			"AssignedExercisesCol2": "Rest (mins)",
			"AssignedExercisesCol3": "Intensity (%)",
			"AssignedExercisesExerciseId": "34318",
			"AssignedExercisesId": "13752",
			"AssignedExercisesNote": "",
			"TrackedExercisesNote": "",
			"AssignedExercisesOrder": 25,
			"AssignedExercisesSuperNum": "0",
			"AssignedExercisesSuperSet": "No",
			"AssignedExercisesType": "Cool Down",
			"AssignedExercisesWorkoutId": "270",
			"Attrs": [{
				"AssignedAttrsAttr0": 1,
				"AssignedAttrsAttr1": 25,
				"AssignedAttrsAttr2": "1:00",
				"AssignedAttrsAttr3": 75,
				"TrackedAttrsAttr0": 0,
				"TrackedAttrsAttr1": 0,
				"TrackedAttrsAttr2": "0:00",
				"TrackedAttrsAttr3": 0,
				"AssignedAttrsId": "42500",
				"AssignedAttrsExerciseId": "13752",
				"AssignedAttrsOrder": 0
			}]
		}]
	}
}
```

###### Example JSON Response

If you include ```?return=object``` you get a complete object and not the response below.


``` json
{
    "status": 1,
    "data": {
        "Id": 1805
    }
}
```
