# Contract Monthly Claim System (CMCS)

## Project Overview
Contract Monthly Claim System (CMCS) is a role-based web application built with ASP.NET Core Razor Pages to manage lecturer claim submissions from start to finish. It allows lecturers to submit monthly claims with supporting documents, enables administrators to review and approve or reject claims, and gives HR users the ability to mark claims as paid and generate reports or invoices.

This project was designed to replace a manual claims process with a more organized digital workflow that is easier to track, approve, and report on.

## Main Features
- Lecturer registration and login
- Role-based dashboards for Lecturer, Admin, and HR users
- Monthly claim submission with course selection, hours worked, hourly rate, and description
- Supporting document uploads for each claim
- Claim review and status updates
- Rejection message support when a claim is declined
- HR payment tracking for approved claims
- PDF and Excel report generation
- Clean Bootstrap-based interface

## Technology Stack
- C#
- ASP.NET Core Razor Pages
- Entity Framework Core
- MySQL
- Bootstrap
- jQuery
- ClosedXML for Excel export
- iText 7 for PDF generation

## Requirements
Before running the application, make sure the following are installed:
- .NET 8 SDK
- MySQL Server 8.x or MySQLWorkbench 8.0
- Visual Studio 2022 or later
- Git

## Local Setup Instructions

### 1. Clone the repository
```bash
git clone https://github.com/your-username/your-repository-name.git
cd your-repository-name
```

### 2. Open the project folder
Open the folder that contains the `ContractMonthlyClaimSystem.csproj` file.

### 3. Restore dependencies
```bash
dotnet restore
```

### 4. Install the Entity Framework Core command-line tool
If you do not already have it installed, run:
```bash
dotnet tool install --global dotnet-ef
```

### 5. Create the MySQL database
Create a database in MySQL named `cmcs` or update the name to match your own connection string.

### 6. Update the connection string
Open `appsettings.json` and update the `DefaultConnection` value so it matches your MySQL server, username, password, and database name.

Example format:
```json
"ConnectionStrings": {
  "DefaultConnection": "Server=localhost;Port=3306;User=your-user;Password=your-password;Database=cmcs;"
}
```

### 7. Apply the database migrations
From the project directory, run:
```bash
dotnet ef database update
```
This creates or updates the database schema based on the EF Core migrations included in the project.

### 8. Run the application
```bash
dotnet run
```

### 9. Open the application in your browser
After the app starts, open the local URL shown in the terminal.

## Visual Studio Run Option
If you are using Visual Studio:
1. Open the `.sln` file.
2. Set the `ContractMonthlyClaimSystem` project as the startup project.
3. Update the connection string in `appsettings.json`.
4. Run the project using `F5` or the Start button.

## How the System Works
1. A lecturer signs up and logs in.
2. The lecturer submits a monthly claim with supporting documents.
3. The claim is saved with a `Pending` status.
4. An admin reviews the claim and either approves or rejects it.
5. If approved, HR can mark the claim as paid.
6. HR can generate downloadable reports and invoices for record keeping.

## Notes for Employers
- The system uses role-based access, so each user sees only the pages relevant to their role.
- The application supports database-backed claim storage and document tracking.
- The project demonstrates form validation, file handling, authentication, and reporting.
- Screenshots should be included in the repository to help viewers quickly understand the workflow.

## Repository Structure
- `Pages/` – Razor Pages for user login, sign-up, and dashboards
- `Models/` – Entity and view model classes
- `Data/` – Database context
- `Migrations/` – EF Core migration files
- `Services/` – Report generation logic
- `Middleware/` – Session-related middleware
- `wwwroot/` – Static files and uploaded supporting documents

## GitHub Link
`https://github.com/Jamie-LeeSimelane/your-contractmonthlyclaimsystem-cmcs-`

## Troubleshooting
- If the database does not update, confirm that MySQL is running and that the connection string is correct.
- If `dotnet ef` is not recognized, install the EF tool again.
- If files fail to upload, make sure the `wwwroot/uploads` folder is writable.
- If the application opens but pages redirect unexpectedly, check that the session and role values are being stored correctly after login.

## Future Improvements
- Add stronger server-side authorization checks
- Improve error handling and logging
- Add automated tests
- Add email notifications for claim approval and rejection
- Add audit logs for status changes

