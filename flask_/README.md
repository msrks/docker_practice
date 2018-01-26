simple flask hello app

Usage

```bash
$ docker build -t flask_docker .
$ docker run -d -p 5000:5000 flask_docker
$ curl flask_docker
hello world 
```

Dockerfile

```dockerfile
FROM python:3.6.2-alpine

ARG project_dir=/app/

ADD app.py $project_dir
ADD requirements.txt $project_dir

WORKDIR $project_dir
RUN pip install -r requirements.txt

ENV FLASK_APP=app.py

EXPOSE 5000

CMD ["flask", "run", "--host", "0.0.0.0"]
```

app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return "hello world"
```
