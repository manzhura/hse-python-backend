FROM ubuntu:22.04

RUN apt-get update && \
    apt-get install -y --no-install-recommends \
    gcc \
    python3-dev \
    python3-pip
#     make \
#     wget \
#     ffmpeg \
#     libsm6 \
#     libxext6 \
#     libpq-dev


WORKDIR $APP_ROOT/src
COPY . ./

ENV VIRTUAL_ENV=$APP_ROOT/src/.venv \
    PATH=$APP_ROOT/src/.venv/bin:$PATH

RUN pip install -r requirements.txt
COPY . .

CMD ["uvicorn", "main:app", "--port", "8080", "--host", "0.0.0.0"]