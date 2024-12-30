Install [pipx](https://pipx.pypa.io/stable/installation/)

Install [Poetry](https://python-poetry.org/)
```
pipx install poetry
```

Installing packages with Poetry
```
poetry add fastapi gunicorn
```

Check poetry.lock and toml file to view the installed packages

View the virtual environment created by Poetry
```
poetry show -v
```
For the absolute path of virtual environment
```
poetry env info -p
```
To the result of above command, attach the below
```
/bin/python{your-python-version}
```

Then in your editor select the virtual environment. 

On gettting error when doing poetry shell, run the below command
```
poetry env use python3.12
```
And then rerun ```poetry shell```

To install already installed packages, run
```
poetry install
```

To run the app (development)
`poetry run dev`
```
poetry run uvicorn fastapi_notebook_starter.main:app --reload --host 127.0.0.1 --port 8000
```

To run the app (production)
`poetry run start`
```
poetry run gunicorn fastapi_notebook_starter.main:app --workers 4 --worker-class uvicorn.workers.UvicornWorker --bind 0.0.0.0:8500
```

For redoc docs
```
http://localhost:8500/redoc
```


Running lint check
```
tox -e lint
```