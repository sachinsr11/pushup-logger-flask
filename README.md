# Pushup Logger Flask App

A simple web application for logging push-up workouts, built with Flask.  
Features user authentication, CRUD operations for workouts, and a responsive UI.

## Features

- User registration and login (Flask-Login)
- Add, view, update, and delete push-up workouts
- Pagination for workout history
- Flash messages for user feedback
- SQLite database (via SQLAlchemy)
- Docker support for easy deployment

## Project Structure

```
pushup-logger-flask/
│
├── app.py                # Entry point for running the app
├── create_db.py          # Script to initialize the database
├── requirements.txt      # Python dependencies
├── dockerfile            # Docker build instructions
├── docker-compose.yaml   # Docker Compose configuration
├── pushup/               # Main application package
│   ├── __init__.py       # App factory and setup
│   ├── models.py         # Database models (User, Workout)
│   ├── main.py           # Workout CRUD routes
│   ├── auth.py           # Authentication routes
│   └── templates/        # HTML templates
│       ├── base.html
│       ├── index.html
│       ├── signup.html
│       ├── login.html
│       ├── profile.html
│       ├── all_workouts.html
│       ├── create_workout.html
│       ├── update_workout.html
│   └── static/           # CSS and images
│       ├── beauty.css
│       ├── extended_beauty.css
│       └── images/
│           ├── muscle.ico
│           └── pushup.png
├── instance/             # SQLite database (created at runtime)
├── .gitignore            # Git ignore rules
├── dockerignore          # Docker ignore rules
├── LICENSE
└── README.md
```

## Getting Started

### Prerequisites

- Python 3.9+
- pip

### Local Setup

1. **Clone the repository:**
   ```sh
   git clone https://github.com/your-username/pushup-logger-flask.git
   cd pushup-logger-flask
   ```

2. **Create a virtual environment and activate it:**
   ```sh
   python -m venv env
   source env/bin/activate  # On Windows: env\Scripts\activate
   ```

3. **Install dependencies:**
   ```sh
   pip install -r requirements.txt
   ```

4. **Initialize the database:**
   ```sh
   python create_db.py
   ```

5. **Run the app:**
   ```sh
   python app.py
   ```
   The app will be available at [http://localhost:5000](http://localhost:5000).

### Docker Setup

1. **Build and run with Docker Compose:**
   ```sh
   docker-compose up --build
   ```
   The app will be available at [http://localhost:5001](http://localhost:5001).

2. **Stop the containers:**
   ```sh
   docker-compose down
   ```

## Usage

- **Sign Up:** Create a new account.
- **Log In:** Access your workout dashboard.
- **Add Workout:** Log a new push-up session.
- **Edit/Delete Workout:** Manage your workout history.
- **View All Workouts:** Paginated list of your workouts.

## Environment Variables

- `DATABASE_URL`: Set in `docker-compose.yaml` for SQLite database location.

## Customization

- Update styles in `pushup/static/beauty.css` and `extended_beauty.css`.
- Change templates in `pushup/templates/`.

## License

This project is released under [The Unlicense](LICENSE).

## Contributing

Pull requests and suggestions are welcome!

## Troubleshooting

- If you see `__pycache__` files in your repo, update `.gitignore` and remove them from git history.
- For database issues, delete `instance/db.sqlite` and re-run `create_db.py`.

