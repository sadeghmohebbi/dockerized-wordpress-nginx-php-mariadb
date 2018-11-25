#set nginx base image
FROM nginx:1.15-alpine
LABEL author="mohebbi.sadegh@gmail.com"

# copy nginx custom configuration file to nginx configs
COPY nginx.conf /etc/nginx/nginx.conf

# copy other configuration
ADD conf.d /etc/nginx/conf.d