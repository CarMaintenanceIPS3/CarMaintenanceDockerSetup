## Docker Usage Guide

This project uses Docker and Docker Compose to simplify dependency management and deployment. Here's how to get started:

### Prerequisites

The repositories needed are: 
- API: [[https://github.com/CarMaintenanceIPS3/FaunaNetCoreAPI.git](https://github.com/CarMaintenanceIPS3/fauna_db_api)]([https://github.com/CarMaintenanceIPS3/FaunaNetCoreAPI.git](https://github.com/CarMaintenanceIPS3/fauna_db_api)) 
- Frontend: [https://github.com/CarMaintenanceIPS3/NextJS.git](https://github.com/CarMaintenanceIPS3/NextJS.git)

Then make sure you have the following

- Ensure that you have [Docker](https://docs.docker.com/get-docker/) and [Docker Compose](https://docs.docker.com/compose/install/) installed on your system.
- Clone the necessary repositories into the same directory. You should have the following structure:

```markdown
├── CarMaintenanceDockerSetup
│   ├── docker-compose.yml
│   ├── nginx
│   ├── FaunaNetCoreAPI
│   └── NextJS
```


### Starting the Application

1. **Build and run your containers**: Navigate to the directory containing the `docker-compose.yml` file and run the command `docker-compose up --build`. This will build your Docker images if they aren't already built and start your containers.

### Developing with Docker

While the containers are running, you can develop as usual. The application code is mounted into the containers as volumes, so your changes will be reflected in the running containers.

- For the Next.js application, Hot Module Replacement (HMR) is configured out of the box, so your changes will be immediately reflected in your running application.

- For the .NET Core API, you might need to restart the service if changes are not being picked up. You can do this by stopping the running services with `Ctrl+C` and then running `docker-compose up` again.

### Stopping the Application

1. **Stop your containers**: Use the command `docker-compose down` in the directory containing your `docker-compose.yml` file. This will stop and remove the containers, networks, and volumes defined in your Docker Compose file.

### Continuing Development

When you're ready to start development again, you can use the command `docker-compose up --build` to ensure that your images are up-to-date and start your containers.

## Additional Notes

Remember, if you're not seeing your changes reflected in your running containers, you might need to manually restart them or make sure that your applications are configured to automatically reload on changes to the source code.
