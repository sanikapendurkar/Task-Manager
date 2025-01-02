# Task Manager Application

## Overview

The Task Manager Application is a command-line tool that allows users to manage their tasks efficiently. Users can:

- Register and login using their email and password.
- Add, delete, modify, and view tasks.
- Email the list of tasks to the user.
- The tasks include details such as start date, start time, end date, end time, and status.

This project uses `pandas` to manage task data, `smtplib` for email functionalities, and regular expressions to validate inputs.

## Features

1. **User Registration and Login**:
   - Users can create a new account or log in with their existing credentials (email and password).

2. **Task Management**:
   - Users can add new tasks with start and end dates, times, and status.
   - Tasks can be deleted or modified after they are created.
   - Users can view a list of all their tasks.

3. **Task Reminders via Email**:
   - Users can email their task list to themselves, which includes task names, start and end dates, start and end times, and current status.

4. **Date and Time Validation**:
   - Dates and times are validated using regular expressions to ensure proper formats (e.g., YYYY-MM-DD for dates, HH:MM for times).

## Requirements

To run the application, you need the following Python libraries:
- `pandas` - for managing task and user data.
- `re` - for regular expression-based input validation.
- `datetime` - for date and time manipulation.
- `smtplib` - for sending emails.

You can install the required libraries using pip:

```bash
pip install pandas
```

## File Structure

```bash
├── task_manager.py         # Main task manager application code
├── users.csv               # CSV file to store user data
├── task_manager.csv        # CSV file to store task data
├── README.md               # This README file
```

## How to Use

1. **Run the Application:**
   Start the task manager by running the `task_manager.py` script.

   ```bash
   python task_manager.py
   ```

2. **User Registration/Authentication**:
   - The program will prompt you to enter your email address. If the email is not already registered, you will be asked to create a new account.
   - If the email is already registered, you will be asked to enter your password for authentication.

2. **Task Management**:
   After logging in, you will be presented with the following options:
   - Add a task: Create a new task with a name, start date, start time, end date, end time, and status.
   - Delete a task: Delete an existing task by providing its name.
   - Modify a task: Modify the details of an existing task (name, dates, times, or status).
   - View my tasks: View a list of all your tasks.
   - Email my tasks: Email a reminder of your tasks to your registered email.
   - Exit: Exit the application.
  
4. **Email Task List**:
   - When you choose the option to email your tasks, the application will send the list of your tasks to the email address associated with your account.
   - Please make sure your email provider allows SMTP access (Gmail, for example, requires you to enable "less secure apps").

## Code Explanation

**The program is divided into the following main sections**:
- **User Login/Registration** (`user_login()` function):
  - Takes user email and password, validates them, and either logs in or registers a new user.
- **Task Management** (`task_manager()` function):
  - Offers the user a menu to add, delete, modify, and view tasks.
  - It also includes an option to send tasks via email.
- **Date and Time Validation** (`validate_date_and_time()` function):
  - Ensures that the input for dates and times follows the correct formats (YYYY-MM-DD for dates, HH:MM for times).

## CSV Files

**The application relies on two CSV files to store data**:

1. **users.csv**: Stores user information (email, name, password).

2. **task_manager.csv**: Stores task details (task name, start date, start time, end date, end time, task status).

## Sample CSV File Formats

### users.csv Format:
```csv
user_email,user_password,user_name
example@example.com,secretpassword,John Doe
```

### task_manager.csv Format:
```csv
user_email,task_name,task_start_date,task_start_time,task_end_date,task_end_time,task_status
example@example.com,Task 1,2025-01-05,09:00,2025-01-05,11:00,Upcoming
```
