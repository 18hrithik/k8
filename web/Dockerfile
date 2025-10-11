# Use lightweight NGINX base
FROM nginx:alpine

# Remove default files
RUN rm -rf /usr/share/nginx/html/* \
    /etc/nginx/nginx.conf \
    /etc/nginx/conf.d/default.conf

# Copy custom NGINX config
COPY roboshop.conf /etc/nginx/nginx.conf

# Copy static frontend files
COPY static/ /usr/share/nginx/html/

# Expose port 80
EXPOSE 80

# Start NGINX in foreground (required for k8s)
CMD ["nginx", "-g", "daemon off;"]

ADD static /usr/share/nginx/html/