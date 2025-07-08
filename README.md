# Tallying App

A web-based election tallying system built with PHP and PostgreSQL. The app enables administrators to manage constituencies, polling stations, candidates, and users (agents and administrators), while agents can securely submit and manage vote tallies.

## Features

- **User Authentication**: Secure login and logout for admins and agents.
- **Role Management**: Admins can manage users, assign roles, and stations.
- **Constituency & Station Management**: Admins can create, edit, and delete constituencies and polling stations.
- **Candidate Management**: Admins can add, edit, and remove candidates.
- **Tally Submission**: Agents can submit, edit, and delete their vote tallies.
- **Profile Management**: Users can update their profile and upload a profile image.
- **Dark Mode**: Toggleable dark/light theme.
- **CSV Export**: Admins can export tally results as CSV.
- **Responsive UI**: Built with Tailwind CSS for modern, mobile-friendly design.

## Project Structure

```
.
├── admin/                  # Admin dashboard and management pages
├── profile_images/         # Uploaded user profile images
├── votes.db                # (If using SQLite, otherwise PostgreSQL)
├── db.php                  # Database connection
├── init_db.php             # Database initialization script
├── index.php               # Main landing page
├── login.php               # Login page
├── logout.php              # Logout handler
├── profile.php             # User profile page
├── profile_api.php         # Profile AJAX API
├── register.php            # Registration page
├── tally.php               # Agent tally submission page
├── tally_api.php           # Tally AJAX API
└── ...                     # Other supporting files
```

## Getting Started

### Prerequisites

- PHP 7.4+
- PostgreSQL
- Composer (optional, if you want to manage dependencies)

### Installation

1. **Clone the repository:**
    ```sh
    git clone https://github.com/alfredcurl/tallying-app.git
    cd tallying-app
    ```

2. **Configure the Database:**
    - Ensure PostgreSQL is running and a database named `tallying_app` exists.
    - Update database credentials in [`db.php`](db.php) and [`init_db.php`](init_db.php) if needed.

3. **Initialize the Database:**
    ```sh
    php init_db.php
    ```
    This will create tables and insert sample data, including default users:
    - **Admin:** `superadmin` / `superadmin123`
    - **Admin:** `admin` / `admin123`
    - **Agent:** `agent1` / `agent1pass`
    - **Agent:** `agent2` / `agent2pass`

4. **Set Up Web Server:**
    - Place the project in your web server's root directory (e.g., `/var/www/html/tallying-app` for Apache).
    - Ensure the `profile_images/` directory is writable by the web server.

5. **Access the App:**
    - Open your browser and navigate to `http://localhost/tallying-app/`.

## Usage

- **Admins:** Log in with an admin account to manage users, candidates, stations, and view tallies.
- **Agents:** Log in with an agent account to submit and manage vote tallies for assigned stations.
- **Profile:** All users can update their profile and upload a profile image.

## Security Notes

- Passwords are hashed using PHP's `password_hash`.
- Sessions are used for authentication.
- Input validation and prepared statements are used to prevent SQL injection.

## Customization

- **Add/Remove Roles:** Modify the `users` table and related PHP logic.
- **Styling:** Tailwind CSS is used for easy customization.
- **Database:** The app is designed for PostgreSQL but can be adapted for other databases.

## License

This project is provided as-is for educational purposes. Please review and adapt for production use as needed.

---

**Default Admin Login:**  
Username: `superadmin`  
Password: `superadmin123`

**Default Agent Logins:**  
Username: `agent1` / Password: `agent1pass`  
Username: `agent2` /
