FROM python:3.6.2-alpine

ARG project_dir=/app/

ADD app.py $project_dir
ADD requirements.txt $project_dir

WORKDIR $project_dir
RUN pip install -r requirements.txt

EXPOSE 5001

CMD ["gunicorn", "app:app", "-b", "0:5001"]
