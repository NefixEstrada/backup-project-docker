# Use Alpine Linux as base image
FROM alpine

# Install all the required packages
RUN apk add --update --no-cache python3 git

# Download the sources
RUN git clone https://github.com/NefixEstrada/BackupProject

# Change directory to the cloned repository
WORKDIR /BackupProject

# Switch to the develop branch
RUN git checkout develop

# Install all the dependencies
WORKDIR /BackupProject/api
RUN python3 setup.py --path /backups

WORKDIR /BackupProject

# Expose the required ports
EXPOSE 5000

# Run the service
CMD [ "api/venv/bin/python", "run_api.py" ]
