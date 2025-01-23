# DadGpt-py
Web application written mostly in Python that will generate Dad jokes given a topic.
To run front end:
```
docker build -t dadgpt-frontend .
docker run -p 8080:80 dadgpt-frontend
```

## Structure
### Docker
We will have services dockerized so that this applicaiton can run on both Windows and Linux based systems.

### Flask
The server will be brought up using the Python package, Flask. This will allows us to bring up the server locally quickly
and effectively.

### Database
We will start the project out with a SQLite database since it is the most simple and quickest to bring up.
After prototyping, we plan to reevaluate this decision.

### Frontend
We would like to use Vue with Typescript as our frontend framework.
