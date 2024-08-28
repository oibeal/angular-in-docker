# AngularApp Docker Template

This project is a template for deploying Angular applications using Docker. It is set up for both development and production environments (with NGINX) using Docker and Docker Compose.


## Development Server

To start the development server, run the following command:
```bash
docker-compose -f docker-compose.dev.yml up --build
```

Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Production Server

To start the production server, run the following command:
```bash
docker-compose up --build
```

Navigate to `http://localhost`. This is a production environment, so automatic reloading is not applied.


## Environment Variables

- `NODE_VERSION`: The Node.js version to be used to build the application. Default: 22.

## Further Help

For more help on using Docker and Docker Compose, refer to the [official Docker documentation](https://docs.docker.com/).

This template is ideal for easily developing and deploying Angular applications using containers. You can customize the environment variables to suit your specific needs.