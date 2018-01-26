simple flask hello app

Usage

```bash
$ docker build -t msrks/flask_gunicorn .
$ docker run -d -p 5001:5001 msrks/flask_gunicorn
$ http localhost:5001
HTTP/1.1 200 OK
Connection: close
Content-Length: 11
Content-Type: text/html; charset=utf-8
Date: Fri, 26 Jan 2018 07:56:14 GMT
Server: gunicorn/19.7.1

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

EXPOSE 5001

CMD ["gunicorn", "app:app", "-b", "0:5001"]
```

app.py

```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def index():
    return "hello world"
```
