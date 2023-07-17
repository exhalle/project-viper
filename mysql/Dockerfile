# Use the official MySQL image as the base image
FROM mysql:8.0.33-debian

ARG MYSQL_HOST
ARG MYSQL_USER
ARG MYSQL_PASSWORD
ARG MYSQL_DATABASE

# Copy the SQL script to the docker-entrypoint-initdb.d directory
COPY ./initsql/init.sql /docker-entrypoint-initdb.d/
RUN chmod +rx /docker-entrypoint-initdb.d/init.sql
# Expose the MySQL port
EXPOSE 3306
# Set the default command using ENTRYPOINT
ENTRYPOINT ["docker-entrypoint.sh"]
# Append the initialization script as an argument to the ENTRYPOINT command
CMD ["--init-file", "/docker-entrypoint-initdb.d/init.sql"]