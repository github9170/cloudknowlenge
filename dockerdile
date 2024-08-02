FROM ubuntu:latest

MAINTAINER ajay1041999@gmail.com

# Install httpd, zip, and unzip
RUN yum install -y httpd zip unzip

# Download the zip file to /var/www/html/
ADD https://www.free-css.com/assets/files/free-css-templates/download/page247/kindle.zip /var/www/html/

WORKDIR /var/www/html

# Unzip the downloaded file
RUN unzip kindle.zip

# Move the contents of the unzipped folder to the current directory
RUN cp -rvf markups-kindle/. .

# Clean up unnecessary files
RUN rm -rf kindle.zip __MACOSX markups-kindle

# Start the Apache server in the foreground
CMD ["/usr/sbin/httpd", "-D", "FOREGROUND"]

# Expose port 88
EXPOSE 88
