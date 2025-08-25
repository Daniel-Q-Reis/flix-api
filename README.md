# Flix-API 🎬

![Status](https://img.shields.io/badge/status-in%20development-yellow)

A RESTful API built with Django REST Framework, simulating a Netflix-like streaming service. This project is part of the PyCodeBR course curriculum.

## Core Features

* ✅ **User Authentication:** Complete authentication system using JWT (Access and Refresh Tokens).
* ✅ **Genre Management:** Full CRUD for movie categories.
* ✅ **Actor Management:** Full CRUD for actors and actresses.
* ✅ **Movie Management:** CRUD for movies, establishing relationships with Genres and Actors.
* ✅ **Review System:** Allows users to rate movies (from 0 to 5 stars) and add comments.
* ✅ **Platform Statistics:** An endpoint that returns key metrics, such as total movies, count by genre, and average ratings.
* ✅ **Data Import:** A custom management command to populate the actor database from a CSV file.

## Tech Stack

* **Backend:** Python
* **Framework:** Django & Django REST Framework
* **Authentication:** Simple JWT
* **Database:** SQLite3 (for development)
* **Linting:** Flake8

## API Endpoints (v1)

The base URL for all endpoints is `/api/v1/`.

| Method | Endpoint                    | Description                                         | Authentication |
| :------- | :-------------------------- | :------------------------------------------------ | :------------- |
| `POST`   | `/authentication/token/`    | Obtains a new token pair (access and refresh).      | N/A            |
| `POST`   | `/authentication/token/refresh/` | Refreshes an expired access token.                  | N/A            |
| `GET`, `POST` | `/genres/`                  | Lists all genres or creates a new one.            | Required       |
| `GET`, `PUT`, `DELETE` | `/genres/<id>/`             | Retrieves, updates, or deletes a specific genre.  | Required       |
| `GET`, `POST` | `/actors/`                  | Lists all actors or creates a new one.            | Required       |
| `GET`, `PUT`, `DELETE` | `/actors/<id>/`             | Retrieves, updates, or deletes a specific actor.  | Required       |
| `GET`, `POST` | `/movies/`                  | Lists all movies or creates a new one.            | Required       |
| `GET`, `PUT`, `DELETE` | `/movies/<id>/`             | Retrieves, updates, or deletes a specific movie.  | Required       |
| `GET` | `/movies/stats/`            | Returns statistics about movies and reviews.      | Required       |
| `GET`, `POST` | `/reviews/`                 | Lists all reviews or creates a new one.           | Required       |
| `GET`, `PUT`, `DELETE` | `/reviews/<id>/`            | Retrieves, updates, or deletes a specific review. | Required       |

## How to Run the Project Locally

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/your-username/flix-api.git](https://github.com/your-username/flix-api.git)
    cd flix-api
    ```

2.  **Create and activate a virtual environment:**
    ```bash
    # Windows
    python -m venv venv
    .\venv\Scripts\activate

    # macOS / Linux
    python3 -m venv venv
    source venv/bin/activate
    ```

3.  **Install the dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the database migrations:**
    ```bash
    python manage.py migrate
    ```

5.  **Create a superuser to access the Admin panel:**
    ```bash
    python manage.py createsuperuser
    ```

6.  **(Optional) Populate the database with initial actor data:**
    * Place the `actors.csv` file in the project's root directory.
    * Run the command:
    ```bash
    python manage.py import_actors actors.csv
    ```

7.  **Start the development server:**
    ```bash
    python manage.py runserver
    ```

The API will be available at `http://127.0.0.1:8000/`.

## Acknowledgements

This project was developed as part of the PyCodeBR Django REST Framework course. The initial codebase was provided by the instructor and can be found at the [original repository](https://github.com/pycodebr/flix-api).

My goal with this repository is to follow the course, understand the concepts presented, and document my learning process by adding my own features and modifications on top of this solid foundation.

## Next Steps (Future Enhancements)

- [ ] Containerize the application using Docker and Docker Compose.
- [ ] Add automated tests with Pytest.
- [ ] Set up a CI/CD pipeline for automated testing and deployment.