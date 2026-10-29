# Member 4 - Sidharth

**Responsibility:** Admin panel (movies, screens, shows, bookings, reports)

## How to Open

Open `admin/login.html`. Login: `admin` / `admin123`

## Files

| File | Purpose |
|---|---|
| `admin/login.html` | Admin login |
| `admin/dashboard.html` + `js/admin-dashboard.js` | Stats, recent bookings, today's shows, demo bookings button |
| `admin/movies.html` + `js/admin-movies.js` | Add / edit / delete movies |
| `admin/screens.html` + `js/admin-screens.js` | Add / edit / delete screens (rows x seats) |
| `admin/shows.html` + `js/admin-shows.js` | Schedule shows, filter, delete |
| `admin/bookings.html` + `js/admin-bookings.js` | All bookings, search, filter, cancel, CSV export |
| `admin/reports.html` + `js/admin-reports.js` | Chart.js graphs + movie-wise summary + print |
| `js/admin.js` | Shared: login check, sidebar, demo data |

Shared files (identical across all members): `css/style.css`, `js/data.js`, `js/common.js`

## Features

- Admin pages cannot be opened without logging in (`requireAdmin()`)
- Dashboard: total movies, today's shows, tickets sold, revenue, and a progress bar showing seats filled for each show
- Movies: complete form validation, duplicate movies are prevented, and deletion is blocked if there are upcoming bookings
- Screens: rows 4-10, seats per row 6-14. Shrinking a layout is checked so that booked seats do not fall outside it
- Shows: time clashes on the same screen are prevented, and shows cannot be created on past dates
- Bookings: search by ID / name, movie and status filters, admin cancellation, **CSV export**
- Reports: Revenue by Movie (bar), Payment Mode (doughnut), Bookings in the last 7 days (line), Seat Type (doughnut)
- The **"Add Demo Bookings"** button creates 25 sample bookings (for the presentation), and "Clear Demo Data" removes them

## Main Functions

- `requireAdmin()`, `renderAdminSide()`, `generateDemoBookings()` (admin.js)
- `saveMovie()`, `deleteMovie()` (admin-movies.js)
- `addShow()` (admin-shows.js) - clash check
- `drawReports()` (admin-reports.js)

## Note

The admin panel works fully on its own within this folder. To view real user bookings, use the full project package (`CineBook_Full_Project.zip`).
An internet connection is required for the report charts (Chart.js CDN).
