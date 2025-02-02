FROM python:3.12-slim-buster

WORKDIR /app

# Instala dependências do sistema (git, etc.)
RUN apt-get update && apt-get install -y \
git \
build-essential \
&& rm -rf /var/lib/apt/lists/*

# Instala Poetry
RUN curl -sSL https://install.python-poetry.org | python3 -

ENV PATH="/root/.local/bin:$PATH"

# Copia arquivos do projeto
COPY pyproject.toml poetry.lock ./
COPY . .

RUN poetry install --no-interaction --no-ansi --no-root



# Define o comando para iniciar a aplicação FastAPI
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "80"]