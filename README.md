# SUS

This project encompasses four main components: Frontend, Authentication, Software Update Service, and Database. This `README` provides instructions for dockerizing each component, how developers should proceed through each phase, and how to set up a local instance for development.

## Dockerization

### Frontend
1. Navigate to the frontend directory: `cd frontend/`
2. Build the Docker image: `docker build -t project-frontend -f Dockerfile.dev .`
3. Run the container: `docker run -p 3000:3000 project-frontend`

### Authentication
1. Navigate to the authentication directory: `cd authentication/`
2. Build the Docker image: `docker build -t project-auth -f Dockerfile.dev .`
3. Run the container: `docker run -p 5000:5000 project-auth`

### Software Update Service
1. Navigate to the software update service directory: `cd software-update/`
2. Build the Docker image: `docker build -t project-update-service -f Dockerfile.dev .`
3. Run the container: `docker run -p 4000:4000 project-update-service`

### Database
1. Navigate to the database directory: `cd database/`
2. Build the Docker image: `docker build -t project-database -f Dockerfile.dev .`
3. Run the container: `docker run -p 5432:5432 project-database`

## Developer Guide

### Development Phase
1. Always work on the `dev` branch for new features or bug fixes.
2. Once your changes are complete and tested locally, push to the remote `dev` branch.
3. Update the Azure DevOps ticket status to "Ready for Testing".

### GitLab CI/CD Integration
1. On pushing changes to the `dev` branch, GitLab CI will automatically run unit and integration tests.
2. If tests pass, a merge request can be created to merge changes into the `test` branch.
3. Once changes are merged to `test`, GitLab CI triggers deployment to the staging environment.
4. After successful QA verification in the staging environment, another merge request can be created for the `production` branch.

## Setting Up Locally for Development

1. Clone the GitLab repository: `git clone <repository-url>`
2. Navigate to the project directory: `cd project-directory/`
3. Set up environment variables, if any are required.
4. Use Docker Compose to spin up all services: `docker-compose -f docker-compose.dev.yml up`
5. Once all services are running, you can access the application on `http://localhost:<PORT>` (replace `<PORT>` with the port number you've configured).

## Conclusion

By following these guidelines and instructions, developers can ensure a smooth development process, right from local setup to production deployment. Please reach out to the project maintainers if you have any questions or issues.

