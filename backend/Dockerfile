FROM python:3.11-slim 

WORKDIR /app

RUN apt-get update && apt-get install --no-install-recommends -y \
    libpq-dev python3-dev python3-opencv curl libglib2.0-0 build-essential && \
    curl -sSL https://install.python-poetry.org | python3 - && \
    pip install --upgrade pip 

COPY . .

ENV PATH=/root/.local/bin:$PATH

RUN poetry install 

EXPOSE 8000

CMD ["poetry", "run", "uvicorn", "--host", "0.0.0.0", "app.main:app", "--reload"]
