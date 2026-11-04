# Activity Planner

Small web app for planning extracurricular activities on a weekly timetable. You add an activity with a name, a weekday, a start time and a duration, and it appears in a schedule table. Two activities cannot start at the same time on the same day. The interface is in Russian.

## Features

- Add and delete activities
- Weekly schedule table with time slots from 09:00 to 20:30 in 30-minute steps
- Conflict check: an activity that starts at an already used day and time is rejected by the server
- Falls back to data saved in the browser (localStorage) if the server cannot be reached
- Health check endpoint for hosting platforms

## Stack

Node.js, Express 5, plain HTML / CSS / JavaScript on the front end

## Run locally

```bash
git clone https://github.com/Pavel-Shcherbo/finance-app.git
cd finance-app
npm install
npm start
```

The app opens at http://localhost:3000 (set `PORT` and `HOST` to change it).

## API

| Method | Path | Description |
| --- | --- | --- |
| GET | `/api/activities` | list all activities |
| POST | `/api/activities` | add an activity (`name`, `day`, `time`, `duration`) |
| DELETE | `/api/activities/:id` | delete an activity |
| GET | `/health` | status and uptime |

## Notes

- Activities are kept in server memory and are lost when the server restarts. Mongoose is listed in `package.json` but is not used yet.
- Deployed on TimeWeb Cloud Apps (Backend, Express).

## Author

Pavel Shcherbo
