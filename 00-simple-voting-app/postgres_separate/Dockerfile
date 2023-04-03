# Use the official Postgres image as the base image
FROM postgres:15-alpine

# Set environment variables for Postgres
ENV POSTGRES_USER=postgres
ENV POSTGRES_PASSWORD=postgres

# Copy healthcheck script
COPY ./healthchecks/postgres.sh /healthchecks/postgres.sh

# Set the healthcheck command
HEALTHCHECK --interval=5s CMD /healthchecks/postgres.sh || exit 1

# Set the volumes
VOLUME /var/lib/postgresql/data

# Expose Postgres default port
EXPOSE 5432