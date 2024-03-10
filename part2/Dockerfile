# Use the official Nginx image as the base image
FROM nginx:latest

# Copy custom configuration file from the local host into the container
COPY nginx.conf.template /etc/nginx/nginx.conf.template
COPY html/ /usr/share/nginx/html/

# Expose port 80 to allow outside access to the container
EXPOSE 80

# Define environment variables for configuration
ENV NGINX_WORKER_PROCESSES auto
ENV NGINX_WORKER_CONNECTIONS 1024

# Run a script to render the template and start Nginx
CMD /bin/bash -c "envsubst < /etc/nginx/nginx.conf.template > /etc/nginx/nginx.conf && nginx -g 'daemon off;'"