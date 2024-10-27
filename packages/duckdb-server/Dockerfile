# Use an official Python runtime as a parent image
FROM python:3.11-slim

# Set environment variables
ENV PYTHONUNBUFFERED 1

# Install necessary dependencies
RUN apt-get update && apt-get install -y \
    curl \
    && rm -rf /var/lib/apt/lists/*

# Install pipx and duckdb-server using pipx
RUN python3 -m pip install --no-cache-dir pipx && \
    pipx ensurepath && \
    pipx install duckdb-server

# Expose port 8000 for the server
EXPOSE 8000

# Run the server by default
ENTRYPOINT ["duckdb-server"]
