FROM python:3.8-slim

RUN python -m pip install rasa

WORKDIR /app
ENV HOME=/app
COPY . .

# Train model, If data remains same this will be skipped automatically.
RUN rasa train

# Set Entrypoint
ENTRYPOINT ["rasa"]
