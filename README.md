# Event Management System

## Project Setup

### Prerequisites

- Python 3.8+
- Django 3.2+
- pip (Python package installer)

### Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/yourusername/event_management.git](https://github.com/KiranYarashi/Evobi_KiranYarashi_Event_Management.git
    cd event_management
    ```

2. Create and activate a virtual environment:
    ```sh
    python -m venv myenv
    source myenv/bin/activate  # On Windows use `myenv\Scripts\activate`
    ```

3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

4. Apply migrations to set up the database:
    ```sh
    python manage.py migrate
    ```

5. Create a superuser to access the Django admin:
    ```sh
    python manage.py createsuperuser
    ```

6. Run the development server:
    ```sh
    python manage.py runserver
    ```

7. Open your browser and navigate to [http://127.0.0.1:8000/admin](http://_vscodecontentref_/1) to access the admin panel.

## API Details

### Authentication

- **Login**
    - URL: `/api/auth/login/`
    - Method: [POST](http://_vscodecontentref_/2)
    - Description: Authenticates a user and returns a token.
    - Request Body:
        ```json
        {
            "username": "user",
            "password": "pass"
        }
        ```
    - Response:
        ```json
        {
            "token": "your_token"
        }
        ```

- **Logout**
    - URL: `/api/auth/logout/`
    - Method: [POST](http://_vscodecontentref_/3)
    - Description: Logs out the authenticated user.
    - Headers:
        ```json
        {
            "Authorization": "Token your_token"
        }
        ```

### Event Management

- **List Events**
    - URL: `/api/events/`
    - Method: `GET`
    - Description: Retrieves a list of all events.
    - Response:
        ```json
        [
            {
                "id": 1,
                "name": "Event 1",
                "description": "Description of Event 1",
                "location": "Location 1",
                "date": "2023-10-01",
                "attendees": [],
                "tasks": [],
                "created_by": 1,
                "created_at": "2023-09-01T12:00:00Z",
                "updated_at": "2023-09-01T12:00:00Z"
            },
            ...
        ]
        ```

- **Create Event**
    - URL: `/api/events/`
    - Method: [POST](http://_vscodecontentref_/4)
    - Description: Creates a new event.
    - Request Body:
        ```json
        {
            "name": "Event 1",
            "description": "Description of Event 1",
            "location": "Location 1",
            "date": "2023-10-01"
        }
        ```
    - Response:
        ```json
        {
            "id": 1,
            "name": "Event 1",
            "description": "Description of Event 1",
            "location": "Location 1",
            "date": "2023-10-01",
            "attendees": [],
            "tasks": [],
            "created_by": 1,
            "created_at": "2023-09-01T12:00:00Z",
            "updated_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Retrieve Event**
    - URL: `/api/events/{id}/`
    - Method: `GET`
    - Description: Retrieves details of a specific event.
    - Response:
        ```json
        {
            "id": 1,
            "name": "Event 1",
            "description": "Description of Event 1",
            "location": "Location 1",
            "date": "2023-10-01",
            "attendees": [],
            "tasks": [],
            "created_by": 1,
            "created_at": "2023-09-01T12:00:00Z",
            "updated_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Update Event**
    - URL: `/api/events/{id}/`
    - Method: `PUT`
    - Description: Updates details of a specific event.
    - Request Body:
        ```json
        {
            "name": "Updated Event",
            "description": "Updated Description",
            "location": "Updated Location",
            "date": "2023-10-02"
        }
        ```
    - Response:
        ```json
        {
            "id": 1,
            "name": "Updated Event",
            "description": "Updated Description",
            "location": "Updated Location",
            "date": "2023-10-02",
            "attendees": [],
            "tasks": [],
            "created_by": 1,
            "created_at": "2023-09-01T12:00:00Z",
            "updated_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Delete Event**
    - URL: `/api/events/{id}/`
    - Method: `DELETE`
    - Description: Deletes a specific event.
    - Response: `204 No Content`

### Attendee Management

- **List Attendees**
    - URL: `/api/attendees/`
    - Method: `GET`
    - Description: Retrieves a list of all attendees.
    - Response:
        ```json
        [
            {
                "id": 1,
                "name": "Attendee 1",
                "email": "attendee1@example.com",
                "phone": "1234567890",
                "created_at": "2023-09-01T12:00:00Z"
            },
            ...
        ]
        ```

- **Create Attendee**
    - URL: `/api/attendees/`
    - Method: [POST](http://_vscodecontentref_/5)
    - Description: Creates a new attendee.
    - Request Body:
        ```json
        {
            "name": "Attendee 1",
            "email": "attendee1@example.com",
            "phone": "1234567890"
        }
        ```
    - Response:
        ```json
        {
            "id": 1,
            "name": "Attendee 1",
            "email": "attendee1@example.com",
            "phone": "1234567890",
            "created_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Retrieve Attendee**
    - URL: `/api/attendees/{id}/`
    - Method: `GET`
    - Description: Retrieves details of a specific attendee.
    - Response:
        ```json
        {
            "id": 1,
            "name": "Attendee 1",
            "email": "attendee1@example.com",
            "phone": "1234567890",
            "created_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Update Attendee**
    - URL: `/api/attendees/{id}/`
    - Method: `PUT`
    - Description: Updates details of a specific attendee.
    - Request Body:
        ```json
        {
            "name": "Updated Attendee",
            "email": "updated@example.com",
            "phone": "0987654321"
        }
        ```
    - Response:
        ```json
        {
            "id": 1,
            "name": "Updated Attendee",
            "email": "updated@example.com",
            "phone": "0987654321",
            "created_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Delete Attendee**
    - URL: `/api/attendees/{id}/`
    - Method: `DELETE`
    - Description: Deletes a specific attendee.
    - Response: `204 No Content`

### Task Management

- **List Tasks**
    - URL: `/api/tasks/`
    - Method: `GET`
    - Description: Retrieves a list of all tasks.
    - Response:
        ```json
        [
            {
                "id": 1,
                "name": "Task 1",
                "description": "Description of Task 1",
                "deadline": "2023-10-01T12:00:00Z",
                "status": "pending",
                "event": 1,
                "assigned_to": 1,
                "assigned_to_name": "Attendee 1",
                "created_at": "2023-09-01T12:00:00Z",
                "updated_at": "2023-09-01T12:00:00Z"
            },
            ...
        ]
        ```

- **Create Task**
    - URL: `/api/tasks/`
    - Method: [POST](http://_vscodecontentref_/6)
    - Description: Creates a new task.
    - Request Body:
        ```json
        {
            "name": "Task 1",
            "description": "Description of Task 1",
            "deadline": "2023-10-01T12:00:00Z",
            "status": "pending",
            "event": 1,
            "assigned_to": 1
        }
        ```
    - Response:
        ```json
        {
            "id": 1,
            "name": "Task 1",
            "description": "Description of Task 1",
            "deadline": "2023-10-01T12:00:00Z",
            "status": "pending",
            "event": 1,
            "assigned_to": 1,
            "assigned_to_name": "Attendee 1",
            "created_at": "2023-09-01T12:00:00Z",
            "updated_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Retrieve Task**
    - URL: `/api/tasks/{id}/`
    - Method: `GET`
    - Description: Retrieves details of a specific task.
    - Response:
        ```json
        {
            "id": 1,
            "name": "Task 1",
            "description": "Description of Task 1",
            "deadline": "2023-10-01T12:00:00Z",
            "status": "pending",
            "event": 1,
            "assigned_to": 1,
            "assigned_to_name": "Attendee 1",
            "created_at": "2023-09-01T12:00:00Z",
            "updated_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Update Task**
    - URL: `/api/tasks/{id}/`
    - Method: `PUT`
    - Description: Updates details of a specific task.
    - Request Body:
        ```json
        {
            "name": "Updated Task",
            "description": "Updated Description",
            "deadline": "2023-10-02T12:00:00Z",
            "status": "completed",
            "event": 1,
            "assigned_to": 1
        }
        ```
    - Response:
        ```json
        {
            "id": 1,
            "name": "Updated Task",
            "description": "Updated Description",
            "deadline": "2023-10-02T12:00:00Z",
            "status": "completed",
            "event": 1,
            "assigned_to": 1,
            "assigned_to_name": "Attendee 1",
            "created_at": "2023-09-01T12:00:00Z",
            "updated_at": "2023-09-01T12:00:00Z"
        }
        ```

- **Delete Task**
    - URL: `/api/tasks/{id}/`
    - Method: `DELETE`
    - Description: Deletes a specific task.
    - Response: `204 No Content`

- **Update Task Status**
    - URL: `/api/tasks/{id}/update_status/`
    - Method: `PATCH`
    - Description: Updates the status of a specific task.
    - Request Body:
        ```json
        {
            "status": "completed"
        }
        ```
    - Response:
        ```json
        {
            "status": "task status updated",
            "event_progress": [
                {
                    "event": "Event 1",
                    "total_tasks": 10,
                    "completed_tasks": 5,
                    "progress_percentage": 50.0
                },
                ...
            ]
        }
        ```
