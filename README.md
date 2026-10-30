# Lost & Found

A web app for discovering and sharing places worth visiting. Users pin places of interest on a world map, review them, and link them together into travel routes for others to follow.

Built by a student team for the first-year team project (COMP10120) at the University of Manchester, Nov 2023 – Apr 2024.

## Features

- **Accounts:** sign up and log in, with salted password hashes stored in the database
- **Add places:** search the map to autofill a place's details, or click the map to set its location, then add a description and a tag such as nature or museum
- **Browse places:** search for places by name, view them on the map, and read their details
- **Reviews:** leave a star rating and written review on any place
- **Routes:** build a route by clicking places on the map, add a description and tag, and save it for others to browse
- **Browse routes:** search saved routes and see their places on the map
- **Landing page:** an interactive 3D globe built with Three.js

## Tech Stack

| Area | Tools |
| --- | --- |
| Frontend | HTML, CSS, JavaScript, jQuery, Three.js |
| Maps | Google Maps JavaScript API |
| Backend | PHP |
| Database | MySQL |
| Version control | Git (GitLab, with feature branches and merge requests) |

## Project Structure

```
├── front-page/          # Landing page with the 3D globe
├── signup/              # Account creation
├── authenticate/        # Login
├── home-page/           # Main app: map, places, reviews and routes
│   ├── classes/         # JavaScript Place and Route classes, and scripts to save routes
│   └── *.php            # Backend scripts that read from and write to the database
├── inputting-places/    # Standalone place-submission page
├── reviews/             # Review form
└── other-stuff/         # Early tests, project ideas and the team's code style guide
```

The frontend sends requests to small PHP scripts, which query the MySQL database and return text or JSON. The main tables are `User`, `Place`, `PlaceReview`, `Route` and `PlaceRoute`, which links places to routes in order.

## Running Locally

The app was hosted on the university's servers and isn't currently deployed. To run it yourself you'll need:

1. A web server with PHP, such as XAMPP or PHP's built-in server
2. A MySQL database containing the tables above
3. Your own database credentials in the PHP scripts, which currently point at the university database server
4. A Google Maps JavaScript API key

## Known Limitations

This was a first-year project and isn't production-ready. In particular:

- Database queries build SQL from user input directly, which leaves them open to SQL injection. Prepared statements would fix this.
- Logged-in users are identified by cookies the browser can edit, rather than server-side sessions.
- Database credentials are hardcoded in the source.

## Team

Saul Fileen-Orchover, Leonhard Olaye-Felix, Samuel Auterson, Louie O'Brien, Samar Yadav, James Cheung-McMullan, Christian Lumbantoruan
