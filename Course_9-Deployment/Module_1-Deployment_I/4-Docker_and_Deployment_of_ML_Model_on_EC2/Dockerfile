# Create the base image
FROM python:3.7-slim

# Install Dependency
RUN pip install flask==1.1.2

# Copy local folder into the container
COPY ./app.py /app/

# Change the working directory
WORKDIR /app/

# Set "python" as the entry point
ENTRYPOINT ["python"]

# Set the command as the script name
CMD ["app.py"]