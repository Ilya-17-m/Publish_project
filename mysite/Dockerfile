FROM python:3.12

WORKDIR /app

RUN pip install --uprade pip "poetry==2.2.1"
RUN poetry config virtualenvs.create false --local

COPY pyproject.toml poetry.lock ./

RUN poetry install
COPY mysite .

CMD ["gunicorn", "mysite.wsgi:application", "--bind", "0.0.0.0:8000"]

