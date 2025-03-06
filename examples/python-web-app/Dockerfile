FROM ubuntu

WORKDIR /app

COPY requirements.txt /app/
COPY devops /app/

RUN apt-get update && apt-get install -y python3 python3-pip python3-venv

SHELL ["/bin/bash", "-c"]

# Create and activate virtual environment
RUN python3 -m venv venv1 && \
    source venv1/bin/activate && \
    pip install --no-cache-dir -r requirements.txt

EXPOSE 8000

# Use absolute path for virtual environment activation
CMD ["/app/venv1/bin/python3", "manage.py", "runserver", "0.0.0.0:8000"]





