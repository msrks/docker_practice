FROM python:3.6.2-alpine

ARG project_dir=/app/

ADD app.py $project_dir
ADD requirements.txt $project_dir

WORKDIR $project_dir
RUN pip install -r requirements.txt

ENV FLASK_APP=app.py

EXPOSE 5000

CMD ["flask", "run", "--host", "0.0.0.0"]
