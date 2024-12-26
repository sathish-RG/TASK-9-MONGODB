# MongoDB Task
## database for Zen class programme
## users:
```json
[
  {
    "_id": 1,
    "name": "Sathish",
    "email": "sathish@gmail.com",
    "role": "student",
    "attendance": [
      {
        "date": "2024-12-26",
        "status": "present"
      }
    ],
    "tasks_submitted": [
      {
        "task_id": 1,
        "submitted_date": "2024-12-26"
      }
    ],
    "codekata_problems_solved": 300
  }

  {
    "_id": 2,
    "name": "Sowmiya",
    "email": "sowmiya@gmail.com",
    "role": "student",
    "attendance": [
      {
        "date": "2024-12-26",
        "status": "Absent"
      }
    ],
    "tasks_submitted": [
      {
        "task_id": 1,
        "submitted_date": "2024-12-26"
      }
    ],
    "codekata_problems_solved": 1000
  }

  {
    "_id": 3,
    "name": "Abinaya",
    "email": "abinaya@gmail.com",
    "role": "student",
    "attendance": [
      {
        "date": "2024-12-26",
        "status": "present"
      }
    ],
    "tasks_submitted": [
      {
        "task_id": 1,
        "submitted_date": "2024-12-26"
      }
    ],
    "codekata_problems_solved": 600
  }
]
```
## Codekata Collection
```json
[
{
  "_id": 1,
  "user_id": 1,
  "problems_solved": 300
},
{
  "_id": 2,
  "user_id": 2,
  "problems_solved": 1000
},
{
  {
  "_id": 3,
  "user_id": 3,
  "problems_solved": 600
}
}

]
```
## Attendance Collection
```json
[
{
  "_id": 1,
  "user_id": 1,
  "date":"2024-12-26" ,
  "status": "present"
},
{
  "_id": 2,
  "user_id": 2,
  "date":"2024-12-26" ,
  "status": "Absent"
},
{
  "_id": 3,
  "user_id": 3,
  "date":"2024-12-26" ,
  "status": "present"
}

]
```
## Topics Collection
```json
[
    {
  "_id": 1,
  "title": "React JS",
  "description": "JavaScript library",
  "date": "2024-12-26"

},
  {
  "_id": 2,
  "title": "Node JS",
  "description": "JavaScript library for backend",
  "date": "2024-12-27"
  
}
]
```
## Tasks Collection
```json
[
  {
  "_id": 1,
  "title": "Search Movies",
  "description": "using reactjs",
  "due_date": "2024-12-30",
  "assigned_date": "2024-12-27"
},
 {
  "_id": 2,
  "title": "Expence Tracker",
  "description": "using JavaScript,HTML,CSS",
  "due_date": "2024-12-30",
  "assigned_date": "2024-12-27"
}

]
```
## Company Drives Collection
```json
[
{
  "_id": 1,
  "company_name": "Zoho",
  "date": "2024-12-27",
  "students_appeared": [2]
},
{
  "_id": 2,
  "company_name": "Amazon",
  "date": "2024-12-28",
  "students_appeared": [3]
}

]
```
## Mentors Collection
```json
[
{
  "_id": 1,
  "name": "Sanjai",
  "email": "sanjai@gmail.com",
  "mentees": [1] 
},
{
  "_id": 2,
  "name": "Saravanan",
  "email": "saravana@gmail.com",
  "mentees": [2] 
}
]
```
# QUERIES

## 1) Find all the topics and tasks which are thought in the month of October.
`
db.topics.aggregate([
  { 
    $match: { 
      date: { 
        $gte: ISODate("2020-10-01"), 
        $lte: ISODate("2020-10-31") 
      } 
    } 
  }
]);

db.tasks.aggregate([
  { 
    $match: { 
      assigned_date: { 
        $gte: ISODate("2020-10-01"), 
        $lte: ISODate("2020-10-31") 
      } 
    } 
  }
]);
`