# Use Ubuntu as the base image
FROM ubuntu

# Set the working directory
WORKDIR /app

# Copy the application files
COPY requirements.txt /app/
COPY devops /app/devops

# Install Python and tools
RUN apt-get update && \
    apt-get install -y python3 python3-pip python3-venv && \
    python3 -m venv /app/venv && \
    /app/venv/bin/pip install --upgrade pip && \
    /app/venv/bin/pip install -r requirements.txt

# Add the virtual environment to PATH
ENV PATH="/app/venv/bin:$PATH"

# Set the entry point and command
ENTRYPOINT ["python3"]
CMD ["/app/devops/manage.py", "runserver", "0.0.0.0:8000"]