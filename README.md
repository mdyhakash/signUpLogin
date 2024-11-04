# Django Signup/Signin Project

This project is a basic Django application for user authentication, including functionality for user signup, login, and logout. It also provides Bootstrap-styled alert messages for feedback.

## Features

- **User Registration (Signup)**: Allows users to create an account with a username, first and last name, email, and password.
- **User Login (Signin)**: Registered users can log in with their credentials.
- **Session Management**: After login, users can access protected pages and receive a personalized greeting.
- **Signout**: Authenticated users can log out, which ends their session.
- **Feedback Messages**: Bootstrap-styled alerts inform users of success or error messages during registration and login.
- **Responsive Design**: The project is built with responsive design practices, making it accessible on various devices.

## Prerequisites

- **Python 3.x**
- **Django 5.1.2**
- **Virtual Environment Setup**: It's recommended to use a virtual environment to manage dependencies (e.g., `virtualenv`).

## File Structure

The primary files and folders in this project:

## Setup and Installation

### Step 1: Clone the Repository

Clone this repository to your local machine:

```bash
git clone https://github.com/mdyhakash/signUpLogin.git
cd signUpLogin
```

## Step 2: Create a Virtual Environment

```bash
python -m venv venv
source venv/bin/activate  # For Linux/Mac
venv\Scripts\activate     # For Windows
```

## Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

## Step 4: Configure Django Settings

- **In the settings.py file, configure the following:**
- **Database:** If using a different database, update the DATABASES section.
- **Allowed Hosts:** Add localhost or your domain to ALLOWED_HOSTS.
- **Configure any other project-specific settings as needed.**

## Step 5: Run Migrations

```bash
python manage.py migrate
```

## Step 6: Create a Superuser (Optional)

```bash
python manage.py createsuperuser
```

## Step 7: Start the Server

```bash
python manage.py runserver
```

## How to Integrate This Project in Your Existing Django Project

- If you'd like to add this signup/signin functionality to another Django project, follow these steps:
- **Copy the authentication App:**

  - **1.Copy the authentication folder from this project into your existing Django project.**

  - **2.Add App to Installed Apps:**

    - In your existing project's settings.py, add the authentication app to INSTALLED_APPS:

    ```bash
    INSTALLED_APPS = [
    ...,
    'authentication',
    ]
    ```

  - **3.Update Project URLs:**

    - In your main urls.py file, include the authentication URLs:

    ```bash
    from django.urls import include, path
    urlpatterns = [
    path('', include('authentication.urls')),
    ...,
    ]
    ```

  - **4.Apply Migrations:**

    - Run migrations to create the necessary tables in your database:

    ```bash
    python manage.py migrate
    ```

  - **5.Templates and Static Files:**

    - Copy any template files from authentication/templates/ into your project's main templates folder if you wish to customize them. Ensure static files (e.g., Bootstrap or CSS) are properly linked.

  - **6.Customize as Needed:**
    - You can modify the views or templates in authentication to fit the design and requirements of your existing project.

## Usage Instructions

- **Sign Up:** Navigate to /signup to register a new user account by filling in the username, first name, last name, email, and password fields. The application checks for form validity and displays error messages for issues like mismatched passwords.
- **Sign In:** After registering, go to /signin and log in with your username and password.
- **Authenticated Home:** Logged-in users are redirected to a home page with a personalized greeting. From this page, they can also sign out.
- **Sign Out:** Clicking the "Sign Out" button ends the user’s session and redirects them to the home page.

## Example Code Snippets

- Signup Page Template (signup.html)
- Here's an example template snippet for the signup page:

```bash
    <form action="/signup" method="POST">
    {% csrf_token %}
    <input type="text" name="username" placeholder="Create username" required>
    <input type="text" name="fname" placeholder="First name" required>
    <input type="text" name="lname" placeholder="Last name" required>
    <input type="email" name="email" placeholder="Email" required>
    <input type="password" name="pass1" placeholder="Password" required>
    <input type="password" name="pass2" placeholder="Confirm Password" required>
    <button type="submit">Sign Up</button>
    </form>
```

- Signin Page Template (signin.html)

```bash
<form action="/signin" method="POST">
    {% csrf_token %}
    <input type="text" name="username" placeholder="Enter your username" required>
    <input type="password" name="pass1" placeholder="Enter your password" required>
    <button type="submit">Sign In</button>
</form>
```

## Dependencies

- The project dependencies are listed in requirements.txt:

```bash
asgiref==3.8.1
distlib==0.3.9
dj-database-url==2.3.0
Django==5.1.2
filelock==3.16.1
platformdirs==4.3.6
sqlparse==0.5.1
typing_extensions==4.12.2
tzdata==2024.2
virtualenv==20.27.1
```

## License

- This project is open-source and available under the MIT License.

```bash
This version now includes instructions on integrating the authentication functionality into other Django projects. Adjust as needed for additional customization options!
```
