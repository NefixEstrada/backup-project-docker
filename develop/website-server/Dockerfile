# Use Alpine Linux as base image
FROM alpine:3.7

# Install all the required packages
RUN apk add --update --no-cache nginx

# Create a folder for the nginx process
RUN mkdir -p /run/nginx

# Expose the required ports
EXPOSE 80
EXPOSE 443

# Run the service
CMD [ "nginx", "-g", "daemon off;" ]
