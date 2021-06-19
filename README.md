# Bootcamp-REST-API


# Bootcamp API

Backend API for the DevCamper application to manage bootcamps, courses, reviews, users and authentication

## Indices

* [Authentication](#authentication)

  * [Forgot Password](#1-forgot-password)
  * [Get Logged In User via Token](#2-get-logged-in-user-via-token)
  * [Login User](#3-login-user)
  * [Logout User](#4-logout-user)
  * [Register User](#5-register-user)
  * [Reset Password](#6-reset-password)
  * [Update Password](#7-update-password)
  * [Update User Details](#8-update-user-details)

* [Bootcamps](#bootcamps)

  * [Create New Bootcamp](#1-create-new-bootcamp)
  * [Delete Bootcamp](#2-delete-bootcamp)
  * [Get All Bootcamps](#3-get-all-bootcamps)
  * [Get Bootcamps By Distance](#4-get-bootcamps-by-distance)
  * [Get Single Bootcamp](#5-get-single-bootcamp)
  * [Update Bootcamp](#6-update-bootcamp)
  * [Upload Photo](#7-upload-photo)

* [Courses](#courses)

  * [Create Course](#1-create-course)
  * [Delete Course](#2-delete-course)
  * [Get All Courses](#3-get-all-courses)
  * [Get Courses For Bootcamp](#4-get-courses-for-bootcamp)
  * [Get Single Course](#5-get-single-course)
  * [Update Course](#6-update-course)

* [Reviews](#reviews)

  * [Add Review For Bootcamp](#1-add-review-for-bootcamp)
  * [Delete Review](#2-delete-review)
  * [Get All Reviews](#3-get-all-reviews)
  * [Get Reviews For Bootcamp](#4-get-reviews-for-bootcamp)
  * [Get Single Review](#5-get-single-review)
  * [Update Review](#6-update-review)

* [Users](#users)

  * [Create User](#1-create-user)
  * [Delete User](#2-delete-user)
  * [Get All Users](#3-get-all-users)
  * [Get Single User](#4-get-single-user)
  * [Update User](#5-update-user)


--------


## Authentication
Routes for user authentication including register, login, reset password, etc



### 1. Forgot Password


Generate password token and send email


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/auth/forgotpassword
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |



***Body:***

```js        
{
	"email": "john@gmail.com"
}
```



### 2. Get Logged In User via Token



***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/auth/me
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 3. Login User



***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/auth/login
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |



***Body:***

```js        
{
	"email": "john@gmail.com",
	"password": "123456"
}
```



### 4. Logout User


Clear token cookie 


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/auth/logout
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 5. Register User


Add user to database with encrypted password


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/auth/register
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |



***Body:***

```js        
{
	"name": "John Doe",
	"email": "john@gmail.com",
	"password": "123456",
	"role": "publisher"
}
```



### 6. Reset Password


Reset user password using token


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/auth/resetpassword/cd4739d9ae2f1b04299c99e1d4c2bfa0046caf77
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |



***Body:***

```js        
{
	"password": "1234567"
}
```



### 7. Update Password


Update logged in user password, send in the body currentPassword and newPassword


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/auth/updatepassword
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"currentPassword": "1234567",
	"newPassword": "123456"
}
```



### 8. Update User Details


Update logged in user name and email


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/auth/updatedetails
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"email": "john@gmail.com",
	"name": "John Doe"
}
```



## Bootcamps
Bootcamps CRUD functionality



### 1. Create New Bootcamp


Add new bootcamp to database. Must be authenticated and must be publisher or admin. Only 1 bootcamp allowed per publisher


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/bootcamps
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"name": "ModernTech Bootcamp",
		"description": "ModernTech has one goal, and that is to make you a rockstar developer and/or designer with a six figure salary. We teach both development and UI/UX",
		"website": "https://moderntech.com",
		"phone": "(222) 222-2222",
		"email": "enroll@moderntech.com",
		"address": "220 Pawtucket St, Lowell, MA 01854",
		"careers": ["Web Development", "UI/UX", "Mobile Development"],
		"housing": false,
		"jobAssistance": true,
		"jobGuarantee": false,
		"acceptGi": true
}
```



### 2. Delete Bootcamp


Delete bootcamp from database


***Endpoint:***

```bash
Method: DELETE
Type: 
URL: {{URL}}/api/v1/bootcamps/5d713a66ec8f2b88b8f830b8
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 3. Get All Bootcamps


Fetch all bootcamps from database. Includes pagination, filtering, etc


***Endpoint:***

```bash
Method: GET
Type: RAW
URL: http://localhost:5000/api/v1/bootcamps
```



***Query params:***

| Key | Value | Description |
| --- | ------|-------------|
| page | 1 |  |
| limit | 2 |  |
| select | name |  |



### 4. Get Bootcamps By Distance


Get bootcamps within a radius of a specific zipcode


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/bootcamps/radius/02118/10
```



### 5. Get Single Bootcamp


Get single bootcamp by ID


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/bootcamps/5d90afc3a5c9f7592c0712e4
```



### 6. Update Bootcamp


Update single bootcamp in database


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/bootcamps/5d713a66ec8f2b88b8f830b8
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"careers": ["Web Development", "UI/UX"]
}
```



### 7. Upload Photo


Route to upload a bootcamp photo


***Endpoint:***

```bash
Method: PUT
Type: FORMDATA
URL: {{URL}}/api/v1/bootcamps/5d725a1b7b292f5f8ceff788/photo
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

| Key | Value | Description |
| --- | ------|-------------|
| file |  |  |



## Courses
Create, read, update and delete courses



### 1. Create Course


Create a course for a specific bootcamp


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/bootcamps/5d725a1b7b292f5f8ceff788/courses
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"title": "Full Stack Web Development",
    "description": "In this course you will learn full stack web development, first learning all about the frontend with HTML/CSS/JS/Vue and then the backend with Node.js/Express/MongoDB",
    "weeks": 12,
    "tuition": 10000,
    "minimumSkill": "intermediate",
    "scholarhipsAvailable": true
}
```



### 2. Delete Course


Remove course from database


***Endpoint:***

```bash
Method: DELETE
Type: 
URL: {{URL}}/api/v1/courses/5d725c84c4ded7bcb480eaa0
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 3. Get All Courses


Get all courses in database


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/courses
```



### 4. Get Courses For Bootcamp


Get the specific courses for a bootcamp


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/bootcamps/5d713995b721c3bb38c1f5d0/courses
```



### 5. Get Single Course


Get a single course by its ID


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/courses/5d725c84c4ded7bcb480eaa0
```



### 6. Update Course


Update course in database


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/courses/5d725c84c4ded7bcb480eaa0
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"tuition": 13000,
	"minimumSkill": "advanced"
}
```



## Reviews
Manage course reviews



### 1. Add Review For Bootcamp


Insert review for a specific bootcamp


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/bootcamps/5d725a1b7b292f5f8ceff788/reviews
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"title": "Nice Bootcamp",
	"text": "I learned a lot",
	"rating": 8
}
```



### 2. Delete Review


Remove review from database


***Endpoint:***

```bash
Method: DELETE
Type: 
URL: {{URL}}/api/v1/reviews/5da0942ee0b3f01c6d89f053
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 3. Get All Reviews


Get all reviews from database and populate with bootcamp name and description


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/reviews
```



### 4. Get Reviews For Bootcamp


Fetch the reviews for a specific bootcamp


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/bootcamps/5d725a1b7b292f5f8ceff788/reviews
```



### 5. Get Single Review


Fetch a review from database by id and populate Bootcamp name and description


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/reviews/5d7a514b5d2c12c7449be027
```



### 6. Update Review


Update review in database


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/reviews/5da0942ee0b3f01c6d89f053
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"title": "Had Fun"
}
```



## Users
CRUD functionality for users only available to admin users



### 1. Create User


Add user to database (admin)


***Endpoint:***

```bash
Method: POST
Type: RAW
URL: {{URL}}/api/v1/users/
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"name": "Nate Smith",
	"email": "nate@gmail.com",
	"password": "123456"
}
```



### 2. Delete User


Delete user from database (admin)


***Endpoint:***

```bash
Method: DELETE
Type: 
URL: {{URL}}/api/v1/users/5d98b144deacc60761649c61
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 3. Get All Users


Get all users (admin)


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/users
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 4. Get Single User


get single user by id (admin)


***Endpoint:***

```bash
Method: GET
Type: 
URL: {{URL}}/api/v1/users/5c8a1d5b0190b214360dc038
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



### 5. Update User


Update user in database (admin)


***Endpoint:***

```bash
Method: PUT
Type: RAW
URL: {{URL}}/api/v1/users/5d98b144deacc60761649c61
```


***Headers:***

| Key | Value | Description |
| --- | ------|-------------|
| Content-Type | application/json | JSON Type |
| Authorization | Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjVkN2E1MTRiNWQyYzEyYzc0NDliZTA0NSIsImlhdCI6MTU3MTA1NzkzMywiZXhwIjoxNTczNjQ5OTMzfQ.rTumDmWSKzoiGrarbCRqpVBVVfHo5su4TNagQM6c2Ts |  |



***Body:***

```js        
{
	"name": "Nate Johnson"
}
```



---
[Back to top](#bootcamp-api)
> Made with &#9829; by [thedevsaddam](https://github.com/thedevsaddam) | Generated at: 2021-06-19 15:49:26 by [docgen](https://github.com/thedevsaddam/docgen)
