# Template Workouts

Endpoints:

- [Get All Template Workouts](#get-all-template-workouts)
- [Get Template Workout By Id](#get-template-workout-by-id)
- [Create New Template Workout - Payload](#create-new-template-workout-payload)
- [Delete Template Workout](#delete-template-workout)


## Get All Template Workouts

This typically is a rather big call. This will return all Template Workouts that your access token has visibility to.


* `GET https://elevationfit.com/api/v1/xxx/templateworkouts`

###### Example JSON Response

```json
{
  "status": 1,
  "data": [{
    "TemplateWorkoutsId": "788",
    "TemplateWorkoutsAccountId": "4",
    "TemplateWorkoutsOwnerId": "69",
    "TemplateWorkoutsProgramId": "0",
    "TemplateWorkoutsName": "Circuit Training Test Workout Lysa",
    "TemplateWorkoutsProgGroup": "0",
    "TemplateWorkoutsProgOrder": "0",
    "TemplateWorkoutsCategory": "",
    "TemplateWorkoutsType": "",
    "TemplateWorkoutsSex": "",
    "TemplateWorkoutsSystem": "",
    "TemplateWorkoutsModality": "Circuit Training",
    "TemplateWorkoutsSkillLevel": "",
    "TemplateWorkoutsDifficulty": "",
    "TemplateWorkoutsAgeGroup": "",
    "TemplateWorkoutsPurpose": "",
    "TemplateWorkoutsPerWeek": "0",
    "TemplateWorkoutsGroupsCsv": "Shoulder, Triceps, Abdominals",
    "TemplateWorkoutsTypesCsv": "Body Weight, Other Cardio",
    "TemplateWorkoutsEquipmentCsv": "No Equip. Needed, Back Extension Stand, Exercise Ball",
    "TemplateWorkoutsPeriod": "0",
    "TemplateWorkoutsRecovery": "0",
    "TemplateWorkoutsNote": "",
    "TemplateWorkoutsPublic": "No",
    "TemplateWorkoutsLibShow": "Yes",
    "TemplateWorkoutsStatus": "Active",
    "TemplateWorkoutsOrder": "0",
    "TemplateWorkoutsUpdatedAt": "2016-03-04 19:40:02",
    "TemplateWorkoutsCreatedAt": "2016-03-04 19:40:01"
  }]
	"pages": 30
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/templateworkouts
```

## Get All Template Workout By Id

We use this api call to get one particular Template workout 

* `GET https://elevationfit.com/api/v1/xxx/templateworkouts/{TemplateWorkoutsId}`

###### Example JSON Response

```json
{
	"status": 1,
	"data": {
    "TemplateWorkoutsId": "788",
    "TemplateWorkoutsAccountId": "4",
    "TemplateWorkoutsOwnerId": "69",
    "TemplateWorkoutsProgramId": "0",
    "TemplateWorkoutsName": "Circuit Training Test Workout Lysa",
    "TemplateWorkoutsProgGroup": "0",
    "TemplateWorkoutsProgOrder": "0",
    "TemplateWorkoutsCategory": "",
    "TemplateWorkoutsType": "",
    "TemplateWorkoutsSex": "",
    "TemplateWorkoutsSystem": "",
    "TemplateWorkoutsModality": "Circuit Training",
    "TemplateWorkoutsSkillLevel": "",
    "TemplateWorkoutsDifficulty": "",
    "TemplateWorkoutsAgeGroup": "",
    "TemplateWorkoutsPurpose": "",
    "TemplateWorkoutsPerWeek": "0",
    "TemplateWorkoutsGroupsCsv": "Shoulder, Triceps, Abdominals",
    "TemplateWorkoutsTypesCsv": "Body Weight, Other Cardio",
    "TemplateWorkoutsEquipmentCsv": "No Equip. Needed, Back Extension Stand, Exercise Ball",
    "TemplateWorkoutsPeriod": "0",
    "TemplateWorkoutsRecovery": "0",
    "TemplateWorkoutsNote": "",
    "TemplateWorkoutsPublic": "No",
    "TemplateWorkoutsLibShow": "Yes",
    "TemplateWorkoutsStatus": "Active",
    "TemplateWorkoutsOrder": "0",
    "TemplateWorkoutsUpdatedAt": "2016-03-04 19:40:02",
    "TemplateWorkoutsCreatedAt": "2016-03-04 19:40:01"  	
	},
	"pages": 0
}
```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/templateworkouts/788
```

## Return A Complete Tracked Workout Object

A Workout within Elevation is layered. All the example calls above just returns the top layer. A complete workout is: the workout data, all the exercises that goes with it, and the attributes that goes with each exercise. 

```TemplateWorkouts -> TemplateExercises -> TemplateAttrs```

Any TemplateWorkout call that is designed to return one template workout such as [Get Template Workout By Id](#get-template-workout-by-id) has an option of returning the entire layered workout. You simply add ```?full=true``` to the end of the call. 

As you can imagine this call is very expensive. Make sure you really need this API call when you call it. Sometimes you can get away with combining other api calls into one. 

For our example here lets use the [Get Template Workout By Id](#get-template-workout-by-id) API call. 

* `GET https://elevationfit.com/api/v1/xxx/templateworkouts/{TemplateWorkoutsId}?full=true`

###### Example JSON Response

```json
{
  "status": 1,
  "data": {
    "TemplateWorkoutsId": "1001",
    "TemplateWorkoutsAccountId": "4",
    "TemplateWorkoutsOwnerId": "6",
    "TemplateWorkoutsProgramId": "293",
    "TemplateWorkoutsName": "Test Workout Name",
    "TemplateWorkoutsProgGroup": "0",
    "TemplateWorkoutsProgOrder": "0",
    "TemplateWorkoutsCategory": "Weight Training",
    "TemplateWorkoutsType": "Weight Training - Free Weights",
    "TemplateWorkoutsSex": "Both",
    "TemplateWorkoutsSystem": "Reps Based",
    "TemplateWorkoutsModality": "Body Weight Training - Full Body",
    "TemplateWorkoutsSkillLevel": "Beginner",
    "TemplateWorkoutsDifficulty": "Low",
    "TemplateWorkoutsAgeGroup": "All",
    "TemplateWorkoutsPurpose": "Personal - Maintain",
    "TemplateWorkoutsPerWeek": "3",
    "TemplateWorkoutsGroupsCsv": "",
    "TemplateWorkoutsTypesCsv": "Body Weight",
    "TemplateWorkoutsEquipmentCsv": "",
    "TemplateWorkoutsPeriod": "0",
    "TemplateWorkoutsRecovery": "0",
    "TemplateWorkoutsNote": "This is a test note.",
    "TemplateWorkoutsPublic": "No",
    "TemplateWorkoutsLibShow": "Yes",
    "TemplateWorkoutsStatus": "Active",
    "TemplateWorkoutsOrder": "0",
    "TemplateWorkoutsUpdatedAt": "2017-10-29 01:01:34",
    "TemplateWorkoutsCreatedAt": "2017-10-29 01:01:34",
    "Exercises": {
      "Warmup": [{
        "TemplateExercisesId": "8513",
        "TemplateExercisesType": "Warmup",
        "TemplateExercisesAttrType": "Distance",
        "TemplateExercisesCol0": "Distance (mi)",
        "TemplateExercisesCol1": "Time (mins)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "No",
        "TemplateExercisesSuperNum": "0",
        "TemplateExercisesNote": "asdfasdf",
        "TemplateExercisesExerciseId": "290",
        "TemplateExercisesOrder": "0",
        "Exercise": {
          "ExercisesId": "290",
          "ExercisesAccountId": "0",
          "ExercisesOwnerId": "0",
          "ExercisesName": "Jump Rope",
          "ExercisesDisplayName": "Jump Rope",
          "ExercisesGroupName": "Jump Rope",
          "ExercisesVariationName": "No Additional Equipment",
          "ExercisesEquipCsv": "Jump Rope",
          "ExercisesPriMusCsv": "Gastrocnemius, Soleus",
          "ExercisesSecMusCsv": "Quadriceps Femoris, Deltoid, Biceps Brachii",
          "ExercisesGroupsCsv": "Calves",
          "ExercisesImage": "exercises\/531c526a315f1_800.jpeg",
          "ExercisesThumb": "exercises\/531c526a315f1_150.jpeg",
          "ExercisesLevelOfDifficulty": "Low",
          "ExercisesTeral": "Unilateral",
          "ExercisesForce": "Push",
          "ExercisesTempo": "Fast",
          "ExercisesBodyPosition": "Standing Athletic Stance",
          "ExercisesApplications": "",
          "ExercisesParentId": "0"
        },
        "Attrs": [{
          "TemplateAttrsId": "19908",
          "TemplateAttrsAttr0": "0.00",
          "TemplateAttrsAttr1": "600.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }]
      }, {
        "TemplateExercisesId": "8514",
        "TemplateExercisesType": "Warmup",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Time (mins)",
        "TemplateExercisesSuperSet": "No",
        "TemplateExercisesSuperNum": "0",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "1465",
        "TemplateExercisesOrder": "1",
        "Exercise": {
          "ExercisesId": "1465",
          "ExercisesAccountId": "0",
          "ExercisesOwnerId": "0",
          "ExercisesName": "Pullup 01b (Wide Grip)",
          "ExercisesDisplayName": "Pullup - Wide Grip",
          "ExercisesGroupName": "Pullup",
          "ExercisesVariationName": "Wide Grip",
          "ExercisesEquipCsv": "Pull Up Bar",
          "ExercisesPriMusCsv": "Teres Major, Latissimus Dorsi",
          "ExercisesSecMusCsv": "Palmaris Longus, Brachioradialis, Biceps Brachii",
          "ExercisesGroupsCsv": "Shoulder, Lats",
          "ExercisesImage": "exercises\/44dad36a10b3a52ba53abea8ab95cee6.jpeg",
          "ExercisesThumb": "exercises\/44dad36a10b3a52ba53abea8ab95cee6_thumb.jpeg",
          "ExercisesLevelOfDifficulty": "Low",
          "ExercisesTeral": "Unilateral",
          "ExercisesForce": "Pull",
          "ExercisesTempo": "Medium",
          "ExercisesBodyPosition": "Hanging",
          "ExercisesApplications": "",
          "ExercisesParentId": "163"
        },
        "Attrs": [{
          "TemplateAttrsId": "19909",
          "TemplateAttrsAttr0": "10.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsId": "19910",
          "TemplateAttrsAttr0": "10.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsId": "19911",
          "TemplateAttrsAttr0": "10.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }]
      }],
      "Normal": [{
        "type": "superset",
        "data": [{
          "TemplateExercisesId": "8515",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "2",
          "TemplateExercisesNote": "324234",
          "TemplateExercisesExerciseId": "3094",
          "TemplateExercisesOrder": "2",
          "Exercise": {
            "ExercisesId": "3094",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Ab Crunch 01g (Weight on Chest)",
            "ExercisesDisplayName": "Ab Crunch - Weight on Chest",
            "ExercisesGroupName": "Ab Crunch - Exercise Ball",
            "ExercisesVariationName": "Weighted - On Chest",
            "ExercisesEquipCsv": "Exercise Ball, General Weight",
            "ExercisesPriMusCsv": "Rectus Abdominis, Obliques External, Obliques Internal",
            "ExercisesSecMusCsv": "Gracilis, Pectineus, Adductor Magnus, Adductor Longus, Adductor Brevis",
            "ExercisesGroupsCsv": "Abdominals",
            "ExercisesImage": "exercises\/530abb6f44d78_800.jpeg",
            "ExercisesThumb": "exercises\/530abb6f44d78_150.jpeg",
            "ExercisesLevelOfDifficulty": "Medium",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Slow",
            "ExercisesBodyPosition": "Supine",
            "ExercisesApplications": "",
            "ExercisesParentId": "3098"
          },
          "Attrs": [{
            "TemplateAttrsId": "19912",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19913",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19914",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }, {
          "TemplateExercisesId": "8516",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "2",
          "TemplateExercisesNote": "asdf",
          "TemplateExercisesExerciseId": "80",
          "TemplateExercisesOrder": "3",
          "Exercise": {
            "ExercisesId": "80",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Chest Press 06a (Supine)",
            "ExercisesDisplayName": "Supine Chest Press - Both Arms",
            "ExercisesGroupName": "Chest Press - Flat Bench, Dumbbell",
            "ExercisesVariationName": "Both Arms",
            "ExercisesEquipCsv": "Dumbbell, Flat Bench",
            "ExercisesPriMusCsv": "Triceps Brachii, Pectoralis Major",
            "ExercisesSecMusCsv": "Anconeus, Deltoid",
            "ExercisesGroupsCsv": "Triceps, Chest",
            "ExercisesImage": "exercises\/52d3161f8124c_800.jpeg",
            "ExercisesThumb": "exercises\/52d3161f8124c_150.jpeg",
            "ExercisesLevelOfDifficulty": "Medium",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Push",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Supine",
            "ExercisesApplications": "",
            "ExercisesParentId": "0"
          },
          "Attrs": [{
            "TemplateAttrsId": "19915",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "55.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19916",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "55.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19917",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "55.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }]
      }, {
        "type": "superset",
        "data": [{
          "TemplateExercisesId": "8517",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "6",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "3095",
          "TemplateExercisesOrder": "4",
          "Exercise": {
            "ExercisesId": "3095",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Decline Ab Crunch 01g (Weight on Chest)",
            "ExercisesDisplayName": "Decline Ab Crunch - Weight on Chest",
            "ExercisesGroupName": "Decline Ab Crunch - Decline Bench",
            "ExercisesVariationName": "Weighted - On Chest",
            "ExercisesEquipCsv": "General Weight, Decline Bench",
            "ExercisesPriMusCsv": "Rectus Abdominis, Obliques External, Obliques Internal",
            "ExercisesSecMusCsv": "Iliopsoas, Rectus Femoris, Tibialis Anterior, Tensor Fasciae Latae",
            "ExercisesGroupsCsv": "Abdominals",
            "ExercisesImage": "",
            "ExercisesThumb": "",
            "ExercisesLevelOfDifficulty": "Medium",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Slow",
            "ExercisesBodyPosition": "Declined",
            "ExercisesApplications": "",
            "ExercisesParentId": "246"
          },
          "Attrs": [{
            "TemplateAttrsId": "19918",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19919",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19920",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19921",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "25.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }, {
          "TemplateExercisesId": "8518",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "6",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "81",
          "TemplateExercisesOrder": "5",
          "Exercise": {
            "ExercisesId": "81",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Decline Chest Press 02a",
            "ExercisesDisplayName": "Decline Chest Press - Both Arms",
            "ExercisesGroupName": "Decline Chest Press - Dumbbells, Decl. Bench",
            "ExercisesVariationName": "Both Arms",
            "ExercisesEquipCsv": "Dumbbell, Decline Bench",
            "ExercisesPriMusCsv": "Triceps Brachii, Pectoralis Major",
            "ExercisesSecMusCsv": "Anconeus, Deltoid",
            "ExercisesGroupsCsv": "Triceps, Chest",
            "ExercisesImage": "exercises\/52d3281dcbb51_800.jpeg",
            "ExercisesThumb": "exercises\/52d3281dcbb51_150.jpeg",
            "ExercisesLevelOfDifficulty": "Low",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Push",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Declined",
            "ExercisesApplications": "",
            "ExercisesParentId": "0"
          },
          "Attrs": [{
            "TemplateAttrsId": "19922",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "60.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19923",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "60.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19924",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "60.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19925",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "60.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }]
      }, {
        "type": "superset",
        "data": [{
          "TemplateExercisesId": "8519",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Time",
          "TemplateExercisesCol0": "Time (mins)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "4",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "257",
          "TemplateExercisesOrder": "6",
          "Exercise": {
            "ExercisesId": "257",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Flutter Kicks 2 (Arms By Side)",
            "ExercisesDisplayName": "Flutter Kicks - Arms By Side",
            "ExercisesGroupName": "Flutter Kicks - On Ground (Supine)",
            "ExercisesVariationName": "Arms By Side",
            "ExercisesEquipCsv": "No Equip. Needed",
            "ExercisesPriMusCsv": "Obliques Internal, Obliques External, Rectus Abdominis",
            "ExercisesSecMusCsv": "Tensor Fasciae Latae, Quadriceps Femoris, Iliopsoas",
            "ExercisesGroupsCsv": "Abdominals",
            "ExercisesImage": "exercises\/f7e294aac7992e7ebb7b9df413b4b440.jpeg",
            "ExercisesThumb": "exercises\/f7e294aac7992e7ebb7b9df413b4b440_thumb.jpeg",
            "ExercisesLevelOfDifficulty": "Low",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Supine",
            "ExercisesApplications": "",
            "ExercisesParentId": "259"
          },
          "Attrs": [{
            "TemplateAttrsId": "19926",
            "TemplateAttrsAttr0": "60.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19927",
            "TemplateAttrsAttr0": "60.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19928",
            "TemplateAttrsAttr0": "60.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19929",
            "TemplateAttrsAttr0": "60.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }, {
          "TemplateExercisesId": "8520",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "4",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "82",
          "TemplateExercisesOrder": "7",
          "Exercise": {
            "ExercisesId": "82",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Incline Chest Press 02a",
            "ExercisesDisplayName": "Incline Chest Press",
            "ExercisesGroupName": "Incline Chest Press - Dumbbells, Incl. Bench",
            "ExercisesVariationName": "Both Arms",
            "ExercisesEquipCsv": "Dumbbell, Incline Bench",
            "ExercisesPriMusCsv": "Triceps Brachii, Pectoralis Major",
            "ExercisesSecMusCsv": "Deltoid, Anconeus",
            "ExercisesGroupsCsv": "Triceps, Chest",
            "ExercisesImage": "exercises\/52d5b5601a875_800.jpeg",
            "ExercisesThumb": "exercises\/52d5b5601a875_150.jpeg",
            "ExercisesLevelOfDifficulty": "Low",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Push",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Inclined",
            "ExercisesApplications": "",
            "ExercisesParentId": "0"
          },
          "Attrs": [{
            "TemplateAttrsId": "19930",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19931",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19932",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19933",
            "TemplateAttrsAttr0": "18.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }]
      }, {
        "type": "normal",
        "data": {
          "TemplateExercisesId": "8521",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "No",
          "TemplateExercisesSuperNum": "0",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "249",
          "TemplateExercisesOrder": "8",
          "Exercise": {
            "ExercisesId": "249",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Leg Lifts 14a (Hanging)",
            "ExercisesDisplayName": "Hanging Leg Lifts - Both Legs",
            "ExercisesGroupName": "Leg Lifts - Pull Up Bar",
            "ExercisesVariationName": "Both Legs",
            "ExercisesEquipCsv": "Pull Up Bar",
            "ExercisesPriMusCsv": "Rectus Abdominis, Obliques External, Obliques Internal, Iliopsoas, Tensor Fasciae Latae",
            "ExercisesSecMusCsv": "Quadriceps Femoris",
            "ExercisesGroupsCsv": "Abdominals, Iliac, Hip Abductor",
            "ExercisesImage": "exercises\/b42661d1581c5a404f5a5cfd22bdea62.jpeg",
            "ExercisesThumb": "exercises\/b42661d1581c5a404f5a5cfd22bdea62_thumb.jpeg",
            "ExercisesLevelOfDifficulty": "Low",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Hanging",
            "ExercisesApplications": "",
            "ExercisesParentId": "0"
          },
          "Attrs": [{
            "TemplateAttrsId": "19934",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "0.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19935",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "0.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19936",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "0.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19937",
            "TemplateAttrsAttr0": "20.00",
            "TemplateAttrsAttr1": "0.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "0.00",
            "TemplateAttrsOrder": "3"
          }]
        }
      }, {
        "type": "superset",
        "data": [{
          "TemplateExercisesId": "8522",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "5",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "346",
          "TemplateExercisesOrder": "9",
          "Exercise": {
            "ExercisesId": "346",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Chest Fly 07g (Standing Downward)",
            "ExercisesDisplayName": "Standing Downward Chest Fly - Both Arms",
            "ExercisesGroupName": "Chest Fly - Cable Cross Over (Standing)",
            "ExercisesVariationName": "Downward Fly - Both Arms",
            "ExercisesEquipCsv": "Cable Cross Over",
            "ExercisesPriMusCsv": "Deltoid, Rhomboids, Pectoralis Major, Pectoralis Minor",
            "ExercisesSecMusCsv": "Latissimus Dorsi, Serratus Anterior, Rectus Abdominis",
            "ExercisesGroupsCsv": "Shoulder, Back, Chest",
            "ExercisesImage": "exercises\/f13d3fa53eb7606992ee0d273f5535d5.jpeg",
            "ExercisesThumb": "exercises\/f13d3fa53eb7606992ee0d273f5535d5_thumb.jpeg",
            "ExercisesLevelOfDifficulty": "Medium",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Standing Split Stance",
            "ExercisesApplications": "",
            "ExercisesParentId": "99"
          },
          "Attrs": [{
            "TemplateAttrsId": "19938",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19939",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19940",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19941",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "50.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }, {
          "TemplateExercisesId": "8523",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "5",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "2798",
          "TemplateExercisesOrder": "10",
          "Exercise": {
            "ExercisesId": "2798",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Trunk Rotation 05d (Seated)",
            "ExercisesDisplayName": "Seated Trunk Rotation",
            "ExercisesGroupName": "Trunk Rotation - Adj. Pulley Machine",
            "ExercisesVariationName": "Exercise Ball (Seated)",
            "ExercisesEquipCsv": "Exercise Ball, Adjustable Pulley Machine",
            "ExercisesPriMusCsv": "Rectus Abdominis, Obliques External, Obliques Internal",
            "ExercisesSecMusCsv": "Pectoralis Minor, Deltoid, Serratus Anterior, Rhomboids",
            "ExercisesGroupsCsv": "Abdominals",
            "ExercisesImage": "",
            "ExercisesThumb": "",
            "ExercisesLevelOfDifficulty": "Low",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Seated",
            "ExercisesApplications": "",
            "ExercisesParentId": "1560"
          },
          "Attrs": [{
            "TemplateAttrsId": "19942",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "65.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19943",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "65.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19944",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "65.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19945",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "65.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }, {
          "TemplateExercisesId": "8524",
          "TemplateExercisesType": "Normal",
          "TemplateExercisesAttrType": "Reps",
          "TemplateExercisesCol0": "Reps (ea)",
          "TemplateExercisesCol1": "Weight (lbs)",
          "TemplateExercisesCol2": "Rest (mins)",
          "TemplateExercisesCol3": "Intensity (%)",
          "TemplateExercisesSuperSet": "Yes",
          "TemplateExercisesSuperNum": "5",
          "TemplateExercisesNote": "",
          "TemplateExercisesExerciseId": "347",
          "TemplateExercisesOrder": "11",
          "Exercise": {
            "ExercisesId": "347",
            "ExercisesAccountId": "0",
            "ExercisesOwnerId": "0",
            "ExercisesName": "Chest Fly 07d (Standing Upward)",
            "ExercisesDisplayName": "Standing Upward Chest Fly - Both Arms",
            "ExercisesGroupName": "Chest Fly - Cable Cross Over (Standing)",
            "ExercisesVariationName": "Upward Fly - Both Arms",
            "ExercisesEquipCsv": "Cable Cross Over",
            "ExercisesPriMusCsv": "Deltoid, Rhomboids, Pectoralis Major, Pectoralis Minor",
            "ExercisesSecMusCsv": "Latissimus Dorsi, Serratus Anterior, Rectus Abdominis",
            "ExercisesGroupsCsv": "Shoulder, Back, Chest",
            "ExercisesImage": "exercises\/a1c44b3a80924122b6d6dbb03c15de2b.jpeg",
            "ExercisesThumb": "exercises\/a1c44b3a80924122b6d6dbb03c15de2b_thumb.jpeg",
            "ExercisesLevelOfDifficulty": "Medium",
            "ExercisesTeral": "Unilateral",
            "ExercisesForce": "Pull",
            "ExercisesTempo": "Medium",
            "ExercisesBodyPosition": "Standing Split Stance",
            "ExercisesApplications": "",
            "ExercisesParentId": "99"
          },
          "Attrs": [{
            "TemplateAttrsId": "19946",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "40.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "0"
          }, {
            "TemplateAttrsId": "19947",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "40.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "1"
          }, {
            "TemplateAttrsId": "19948",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "40.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "2"
          }, {
            "TemplateAttrsId": "19949",
            "TemplateAttrsAttr0": "15.00",
            "TemplateAttrsAttr1": "40.00",
            "TemplateAttrsAttr2": "30.00",
            "TemplateAttrsAttr3": "75.00",
            "TemplateAttrsOrder": "3"
          }]
        }]
      }],
      "CoolDown": [{
        "TemplateExercisesId": "8525",
        "TemplateExercisesType": "Cool Down",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "No",
        "TemplateExercisesSuperNum": "0",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "3097",
        "TemplateExercisesOrder": "12",
        "Exercise": {
          "ExercisesId": "3097",
          "ExercisesAccountId": "0",
          "ExercisesOwnerId": "0",
          "ExercisesName": "Ab Crunch 01a (Arms by Sides)",
          "ExercisesDisplayName": "Ab Crunch - Arms by Sides",
          "ExercisesGroupName": "Ab Crunch - On Floor",
          "ExercisesVariationName": "Arms By Sides",
          "ExercisesEquipCsv": "No Equip. Needed",
          "ExercisesPriMusCsv": "Rectus Abdominis, Obliques External, Obliques Internal",
          "ExercisesSecMusCsv": "Gracilis, Pectineus, Adductor Brevis, Adductor Longus, Adductor Magnus",
          "ExercisesGroupsCsv": "Abdominals",
          "ExercisesImage": "exercises\/52ce0b221b5ad_800.jpeg",
          "ExercisesThumb": "exercises\/52ce0b221b5ad_150.jpeg",
          "ExercisesLevelOfDifficulty": "Low",
          "ExercisesTeral": "Unilateral",
          "ExercisesForce": "Pull",
          "ExercisesTempo": "Slow",
          "ExercisesBodyPosition": "Supine",
          "ExercisesApplications": "",
          "ExercisesParentId": "0"
        },
        "Attrs": [{
          "TemplateAttrsId": "19950",
          "TemplateAttrsAttr0": "1.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "60.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }]
      }, {
        "TemplateExercisesId": "8526",
        "TemplateExercisesType": "Cool Down",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "No",
        "TemplateExercisesSuperNum": "0",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "34314",
        "TemplateExercisesOrder": "13",
        "Exercise": {
          "ExercisesId": "34314",
          "ExercisesAccountId": "4",
          "ExercisesOwnerId": "6",
          "ExercisesName": "Ab Crunch - Arms by Sides (Test)",
          "ExercisesDisplayName": "Ab Crunch - Arms by Sides (Test)",
          "ExercisesGroupName": "Ab Crunch - On Floor",
          "ExercisesVariationName": "Ab Crunch - Arms by Sides (Test)",
          "ExercisesEquipCsv": "Adjustable Pulley Machine, Rope, No Equip. Needed",
          "ExercisesPriMusCsv": "Rectus Abdominis, Obliques External, Obliques Internal",
          "ExercisesSecMusCsv": "Gracilis, Pectineus, Adductor Brevis, Adductor Longus, Adductor Magnus",
          "ExercisesGroupsCsv": "Abdominals",
          "ExercisesImage": "exercises\/52ce0b221b5ad_800.jpeg",
          "ExercisesThumb": "",
          "ExercisesLevelOfDifficulty": "Low",
          "ExercisesTeral": "Unilateral",
          "ExercisesForce": "Pull",
          "ExercisesTempo": "Slow",
          "ExercisesBodyPosition": "Supine",
          "ExercisesApplications": "",
          "ExercisesParentId": "3097"
        },
        "Attrs": [{
          "TemplateAttrsId": "19951",
          "TemplateAttrsAttr0": "1.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "60.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }]
      }]
    }
  },
  "pages": 0
}

```

###### Curl Example

``` shell
curl -s -H "Authorization: Bearer $ACCESS_TOKEN" https://elevationfit.com/api/v1/$ACCOUNT_ID/templateworkouts/788?full=true
```

## Create New Template Workout - Payload

This is the core api call to template a workout. We post in a rather complex json object to this API. Best to see the two examples below. There currently is no validation on this API call. Make sure to post in a complete and correct object.

This api call will return the ID (or new ID) of the tracked workout. If you would like more data you can include ```?return=object``` to the url and this API call will return a complete template workout object. 

* `POST https://elevationfit.com/api/v1/4/templateworkouts/payload`

* `POST https://elevationfit.com/api/v1/4/templateworkouts/payload?return=object`

###### Curl Example

``` shell
curl -X POST \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ json object below..... }' \
  https://elevationfit.com/api/v1/4/templateworkouts/payload
```

###### JSON Payload Example

``` json
{
  "TemplateWorkoutsProgramId": 293,
  "TemplateWorkoutsName": "Test Workout Name",
  "TemplateWorkoutsProgGroup": 0,
  "TemplateWorkoutsProgOrder": 0,
  "TemplateWorkoutsCategory": "Weight Training",
  "TemplateWorkoutsType": "Weight Training - Free Weights",
  "TemplateWorkoutsSex": "Both",
  "TemplateWorkoutsSystem": "Reps Based",
  "TemplateWorkoutsModality": "Body Weight Training - Full Body",
  "TemplateWorkoutsSkillLevel": "Beginner",
  "TemplateWorkoutsDifficulty": "Low",
  "TemplateWorkoutsAgeGroup": "All",
  "TemplateWorkoutsPurpose": "Personal - Maintain",
  "TemplateWorkoutsPerWeek": 3,
  "TemplateWorkoutsPeriod": "",
  "TemplateWorkoutsRecovery": "",
  "TemplateWorkoutsNote": "This is a test note.",
  "TemplateWorkoutsPublic": "No",
  "TemplateWorkoutsLibShow": "Yes",
  "TemplateWorkoutsStatus": "Active",
  "TemplateWorkoutsOrder": 0,
  "Exercises": {
  "Warmup": [{
      "TemplateExercisesType": "Warmup",
      "TemplateExercisesAttrType": "Distance",
      "TemplateExercisesCol0": "Distance (mi)",
      "TemplateExercisesCol1": "Time (mins)",
      "TemplateExercisesCol2": "Rest (mins)",
      "TemplateExercisesCol3": "Intensity (%)",
      "TemplateExercisesSuperSet": "No",
      "TemplateExercisesSuperNum": "0",
      "TemplateExercisesNote": "asdfasdf",
      "TemplateExercisesExerciseId": "290",
      "TemplateExercisesOrder": "0",
      "Attrs": [{
        "TemplateAttrsAttr0": "0.00",
        "TemplateAttrsAttr1": "600.00",
        "TemplateAttrsAttr2": "30.00",
        "TemplateAttrsAttr3": "75.00",
        "TemplateAttrsOrder": "0"
      }]
    }, {
      "TemplateExercisesType": "Warmup",
      "TemplateExercisesAttrType": "Reps",
      "TemplateExercisesCol0": "Reps (ea)",
      "TemplateExercisesCol1": "Weight (lbs)",
      "TemplateExercisesCol2": "Rest (mins)",
      "TemplateExercisesCol3": "Time (mins)",
      "TemplateExercisesSuperSet": "No",
      "TemplateExercisesSuperNum": "0",
      "TemplateExercisesNote": "",
      "TemplateExercisesExerciseId": "1465",
      "TemplateExercisesOrder": "1",
      "Attrs": [{
        "TemplateAttrsAttr0": "10.00",
        "TemplateAttrsAttr1": "0.00",
        "TemplateAttrsAttr2": "30.00",
        "TemplateAttrsAttr3": "75.00",
        "TemplateAttrsOrder": "0"
      }, {
        "TemplateAttrsAttr0": "10.00",
        "TemplateAttrsAttr1": "0.00",
        "TemplateAttrsAttr2": "30.00",
        "TemplateAttrsAttr3": "75.00",
        "TemplateAttrsOrder": "1"
      }, {
        "TemplateAttrsAttr0": "10.00",
        "TemplateAttrsAttr1": "0.00",
        "TemplateAttrsAttr2": "30.00",
        "TemplateAttrsAttr3": "75.00",
        "TemplateAttrsOrder": "2"
      }]
    }], 
  "Normal": [{
      "type": "superset",
      "data": [{
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "2",
        "TemplateExercisesNote": "324234",
        "TemplateExercisesExerciseId": "3094",
        "TemplateExercisesOrder": "2",
        "Attrs": [{
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }, {
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "2",
        "TemplateExercisesNote": "asdf",
        "TemplateExercisesExerciseId": "80",
        "TemplateExercisesOrder": "3",
        "Attrs": [{
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "55.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "55.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "55.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }]
    }, {
      "type": "superset",
      "data": [{
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "6",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "3095",
        "TemplateExercisesOrder": "4",
        "Attrs": [{
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "25.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }, {
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "6",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "81",
        "TemplateExercisesOrder": "5",
        "Attrs": [{
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "60.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "60.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "60.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "60.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }]
    }, {
      "type": "superset",
      "data": [{
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Time",
        "TemplateExercisesCol0": "Time (mins)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "4",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "257",
        "TemplateExercisesOrder": "6",
        "Attrs": [{
          "TemplateAttrsAttr0": "60.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "60.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "60.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "60.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }, {
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "4",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "82",
        "TemplateExercisesOrder": "7",
        "Attrs": [{
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "18.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }]
    }, {
      "type": "normal",
      "data": {
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "No",
        "TemplateExercisesSuperNum": "0",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "249",
        "TemplateExercisesOrder": "8",
        "Attrs": [{
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "0.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "0.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "0.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "20.00",
          "TemplateAttrsAttr1": "0.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "0.00",
          "TemplateAttrsOrder": "3"
        }]
      }
    }, {
      "type": "superset",
      "data": [{
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "5",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "346",
        "TemplateExercisesOrder": "9",
        "Attrs": [{
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "50.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }, {
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "5",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "2798",
        "TemplateExercisesOrder": "10",
        "Attrs": [{
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "65.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "65.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "65.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "65.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }, {
        "TemplateExercisesType": "Normal",
        "TemplateExercisesAttrType": "Reps",
        "TemplateExercisesCol0": "Reps (ea)",
        "TemplateExercisesCol1": "Weight (lbs)",
        "TemplateExercisesCol2": "Rest (mins)",
        "TemplateExercisesCol3": "Intensity (%)",
        "TemplateExercisesSuperSet": "Yes",
        "TemplateExercisesSuperNum": "5",
        "TemplateExercisesNote": "",
        "TemplateExercisesExerciseId": "347",
        "TemplateExercisesOrder": "11",
        "Attrs": [{
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "40.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "0"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "40.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "1"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "40.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "2"
        }, {
          "TemplateAttrsAttr0": "15.00",
          "TemplateAttrsAttr1": "40.00",
          "TemplateAttrsAttr2": "30.00",
          "TemplateAttrsAttr3": "75.00",
          "TemplateAttrsOrder": "3"
        }]
      }]
    }], 
  "CoolDown": [{
      "TemplateExercisesType": "Cool Down",
      "TemplateExercisesAttrType": "Reps",
      "TemplateExercisesCol0": "Reps (ea)",
      "TemplateExercisesCol1": "Weight (lbs)",
      "TemplateExercisesCol2": "Rest (mins)",
      "TemplateExercisesCol3": "Intensity (%)",
      "TemplateExercisesSuperSet": "No",
      "TemplateExercisesSuperNum": "0",
      "TemplateExercisesNote": "",
      "TemplateExercisesExerciseId": "3097",
      "TemplateExercisesOrder": "12",
      "Attrs": [{
        "TemplateAttrsAttr0": "1.00",
        "TemplateAttrsAttr1": "25.00",
        "TemplateAttrsAttr2": "60.00",
        "TemplateAttrsAttr3": "75.00",
        "TemplateAttrsOrder": "1"
      }]
    }, {
      "TemplateExercisesType": "Cool Down",
      "TemplateExercisesAttrType": "Reps",
      "TemplateExercisesCol0": "Reps (ea)",
      "TemplateExercisesCol1": "Weight (lbs)",
      "TemplateExercisesCol2": "Rest (mins)",
      "TemplateExercisesCol3": "Intensity (%)",
      "TemplateExercisesSuperSet": "No",
      "TemplateExercisesSuperNum": "0",
      "TemplateExercisesNote": "",
      "TemplateExercisesExerciseId": "34314",
      "TemplateExercisesOrder": "13",
      "Attrs": [{
        "TemplateAttrsAttr0": "1.00",
        "TemplateAttrsAttr1": "25.00",
        "TemplateAttrsAttr2": "60.00",
        "TemplateAttrsAttr3": "75.00",
        "TemplateAttrsOrder": "1"
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

## Delete Template Workout

This is a DELETE method for removing an template workout. 

* `DELETE https://elevationfit.com/api/v1/4/templateworkouts/{TemplateWorkoutsId}`

###### Curl Example

``` shell
curl -X DELETE \ 
  -H "Authorization: Bearer $ACCESS_TOKEN" \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: MyApp (yourname@example.com)' \
  -d '{ json object below..... }' \
  https://elevationfit.com/api/v1/4/templateworkouts/{TemplateWorkoutsId}
```
