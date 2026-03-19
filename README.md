# Todo API

A simple Todo API built with Flask for CSSE6400 Practical 1.

## Features
- Health check: GET /api/v1/health
- Get all todos: GET /api/v1/todos
- Get a single todo: GET /api/v1/todos/<id>
- Create a new todo: POST /api/v1/todos
- Update a todo: PUT /api/v1/todos/<id>
- Delete a todo: DELETE /api/v1/todos/<id>

## Tech Stack
- Python 3.12+
- Flask
- Poetry

## How to run
1. Clone the repository
   git clone git@github.com:CSSE6400/2026-p1-guruolan18.git
   cd 2026-p1-guruolan18

2. Install dependencies
   poetry install

3. Run the server
   poetry run flask --app todo run -p 6400

## API Examples
### Health check
curl http://localhost:6400/api/v1/health

Response:
{"status":"ok"}

### Get all todos
curl http://localhost:6400/api/v1/todos

Response:
[{"id":1,"title":"Watch CSSE6400 Lecture","completed":true,"deadline_at":"2026-02-27T18:00:00","created_at":"2026-02-20T14:00:00","updated_at":"2026-02-20T14:00:00"}]

### Get a single todo
curl http://localhost:6400/api/v1/todos/1

Response:
{"id":1,"title":"Watch CSSE6400 Lecture","completed":true,"deadline_at":"2026-02-27T18:00:00","created_at":"2026-02-20T14:00:00","updated_at":"2026-02-20T14:00:00"}

### Create a new todo
curl -X POST http://localhost:6400/api/v1/todos \
  -H "Content-Type: application/json" \
  -d '{"title":"New task","description":"Task description"}'

Response:
{"id":1,"title":"Watch CSSE6400 Lecture","completed":true,"deadline_at":"2026-02-27T18:00:00","created_at":"2026-02-20T14:00:00","updated_at":"2026-02-20T14:00:00"}

### Update a todo
curl -X PUT http://localhost:6400/api/v1/todos/1 \
  -H "Content-Type: application/json" \
  -d '{"title":"Updated title"}'

Response:
{"id":1,"title":"Watch CSSE6400 Lecture","completed":true,"deadline_at":"2026-02-27T18:00:00","created_at":"2026-02-20T14:00:00","updated_at":"2026-02-20T14:00:00"}

### Delete a todo
curl -X DELETE http://localhost:6400/api/v1/todos/1

Response:
{"id":1,"title":"Watch CSSE6400 Lecture","completed":true,"deadline_at":"2026-02-27T18:00:00","created_at":"2026-02-20T14:00:00","updated_at":"2026-02-20T14:00:00"}

## Project Structure
2026-p1-guruolan18/
├── todo/
│   ├── __init__.py
│   └── views/
│       └── routes.py
├── pyproject.toml
├── poetry.lock
└── README.md

## Author
guruolan18

## License
Course practical for CSSE6400

