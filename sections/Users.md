# Tracked Workouts

Endpoints:

- [Get Me](#get-me)
- [Update TOS Accept](#update-tos-accept)

## Get Me

Returns a JSON object of with information on the logged in user.

* `GET https://elevationfit.com/api/v1/xxx/me`

## Update TOS Accepts

PUT in a empty body and we will mark the user as accepting of the TOS (UsersTosAgreed)

* `PUT https://elevationfit.com/api/v1/xxx/me/accept_tos`
