# Use Alpine Linux as base image
FROM alpine

# Install all the required packages
RUN apk add --update --no-cache git nodejs

# Download the sources
RUN git clone https://github.com/NefixEstrada/BackupProject

# Change directory to the cloned repository
WORKDIR /BackupProject

# Switch to the develop branch
RUN git checkout develop

# Copy the project settings
COPY conf/settings.json /BackupProject/

# Install all the dependencies
WORKDIR /BackupProject/website
RUN npm install --save

# Compile the website
RUN npm run build

# Copy the compiled code to the volume
CMD [ "cp", "-a", "/BackupProject/website/dist/.", "/website" ]
