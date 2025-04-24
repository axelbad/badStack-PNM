# Docker Stack: PHP, MariaDB, and Nginx

This setup provides a containerized development environment for PHP applications using MariaDB and Nginx.

## System Components

The stack consists of three main services:

- **PHP-FPM (8.3)**: Handles PHP execution and processes requests from Nginx.
- **MariaDB (10.9)**: A relational database management system for data persistence.
- **Nginx (latest)**: A web server that acts as a reverse proxy for PHP-FPM and manages HTTP requests.

## Configuration and Mapping

- The source code in the main directory is mounted into the PHP container at `/var/www/html`.
- Nginx is configured to serve files from `/var/www/html`, with additional configurations stored in `./nginx-conf`.
- The MariaDB service is configured using environment variables specified in the `.env` file. Data is persisted using the `mysqldata` volume.
- By default, `index.php` provides a `phpinfo()` report to verify the PHP environment.

## Usage (Command Line)

To start the environment, follow these steps:

1. Navigate to the `docker` directory:
   ```sh
   cd docker
    ```
2. Start the services using Docker Compose:
    ```sh
   docker-compose up
    ```
## Accessing the Application

Accessing the Application
Once the containers are running, you can access the web application at:

http://127.0.0.1