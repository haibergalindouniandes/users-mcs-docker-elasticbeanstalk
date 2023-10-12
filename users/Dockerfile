FROM python:3.10 AS base
LABEL author="h.galindos@uniandes.edu.co"
ENV FLASK_ENV=development
ENV FLASK_DEBUG=1
ENV DB_USER=postgres
ENV DB_PASSWORD=PgNube202314
ENV DB_HOST=34.41.162.119
ENV DB_PORT=5432
ENV DB_NAME=postgres
ENV TOKEN_DURATION_MIN=10
RUN apt-get update && apt-get install -y
RUN pip install --upgrade pip
RUN pip install pipenv
WORKDIR /home/appuser/app
COPY ["Pipfile", "Pipfile.lock", "./"]
COPY src/. /home/appuser/app
RUN pipenv install --system --deploy
EXPOSE 5000
CMD ["python", "main.py"]