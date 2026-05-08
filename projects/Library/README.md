# Library - Book Catalog and Lending System

Library is a PHP + MySQL web application for catalog search and lending management.

## Features

- Book search with filters
- Book detail pages by ISBN
- Multiple Dewey categories per book
- Authentication (sign up, log in, log out)
- Role-based access (admin, user)
- Lending requests with selectable duration
- Availability tracking through the BookAvailability view
- User dashboard for personal lendings
- Admin dashboard split into homepage, lendings, and book management
- Book management CRUD with cover upload support
- Overdue warning banner on user pages

## Project Structure

```
Library/
├── index.php                  # Homepage
├── assets/
│   └── media/
│       ├── book-images/       # Legacy/seeded cover files
│       └── images/            # General UI images
├── components/
│   ├── admin-sidebar.php      # Shared admin navigation
│   ├── header.php             # Shared header/navbar
│   └── footer.php             # Shared footer
├── admin/
│   ├── admin-dashboard.php    # Admin overview page
│   ├── book-management.php    # Admin catalog CRUD
│   └── lendings.php           # Admin lending actions
├── pages/
│   ├── config.php             # DB connection + setup
│   ├── fetch.php              # Catalog query endpoint
│   ├── checkAuth.php          # Login/signup handler
│   ├── search.php             # Catalog search page
│   ├── book-details.php       # Book details by ISBN
│   ├── advanced-search.php    # Advanced filtering page
│   ├── fetchJSON.php          # JSON import utility
│   ├── logIn.php              # Login page
│   ├── signUp.php             # Registration page
│   ├── logout.php             # Logout endpoint
│   └── private.php            # User dashboard
├── data.json                  # Seed data
├── styles.css                 # Global styles
├── script.js                  # Shared JS helpers
├── .htaccess                  # Rewrite rules (/search/...)
├── TECHNICAL_REPORT.md        # Technical documentation
└── README.md                  # Project overview
```

## Quick Start

1. Configure database credentials in pages/config.php.
2. Place Library in your web server root.
3. Open index.php in browser.
4. Run pages/fetchJSON.php to import publishers, books, categories, relations, and users.

## Database

Database name: malannino_db

Main tables:
- Publishers
- Books
- Dewey
- BookCategory
- Users
- Lendings

Notes:
- Lendings include dueDate, returnDate, and status.
- Book covers are stored in Books.imageData (LONGBLOB) with MIME in Books.imageMime.

## Usage

1. Import data from JSON.
2. Log in or sign up.
3. Search a book and open its ISBN page.
4. Request lending from the book page.
5. Check status in the user dashboard.
6. Use the admin homepage for overview, the lendings page to confirm requests and register returns, and the book management page for catalog CRUD.


Technical report: [TECHNICAL_REPORT.md](TECHNICAL_REPORT.md)

## Author

Leonardo Malannino