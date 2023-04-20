# Rick and Morty API

### How to run
- Create & activate venv: 'python -m venv venv' and  'venv/Scripts/activate'
- Install requirements: 'pip install -r requirements.txt'
- Create new Postgres DB & user
- Copy .env.sample -> .env and populate with all required data
- Run migrations
- Run Redis Server: 'docker run -d -p 6379:6379 redis'
- Run Celery worker for tasks handling: 'celery -A rick_and_morty_api worker -l info -P eventlet'
- Run Celery beat for task scheduling: 'celery -A rick_and_morty_api beat -l INFO --scheduler django_celery_beat.schedulers:DatabaseScheduler'
- Create schedule for running sync in DB
- Run app