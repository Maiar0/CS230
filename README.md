# GameAuthApplication

## Purpose

The **GameAuthApplication** provides a secure RESTful API for managing game users within a multiplayer online game environment, specifically designed to support the backend infrastructure for the _Draw It or Lose It_ game. It offers functionality for basic authentication, authorization, and health monitoring, intended to integrate seamlessly into a web-based platform requiring secure user management across multiple teams and sessions.

This project is part of a broader effort to support multiplayer gaming scenarios, including enforcement of unique identifiers for users and ensuring robust, scalable security and service reliability.

## Implementation

This application is built using **Dropwizard**, a lightweight Java framework for developing high-performance RESTful web services. Key components include:

- **Authentication & Authorization**: Implemented using Dropwizard’s `BasicCredentialAuthFilter`, supporting user validation via `GameAuthenticator` and role-based access control through `GameAuthorizer`.
  
- **RESTful API Services**:
  - `GameUserRESTController`: Manages CRUD operations for game users.
  - `RESTClientController`: Demonstrates client-side HTTP interactions with external services.
  
- **Health Monitoring**:
  - `AppHealthCheck`: Actively verifies API responsiveness by querying the `/gameusers` endpoint.
  - `HealthCheckController`: Exposes all registered health checks via a JSON API at `/status`.

- **Data Representation**:
  - `GameUserInfo`: Represents user details with validation annotations.
  - `GameUserDB`: In-memory data source simulating persistence operations for users.

- **Security Context**:
  - `GameUser`: Wraps authenticated principal details, including user roles.

- **Dropwizard Configuration**:
  - `GameAuthConfiguration`: Currently extends default configuration; placeholder for future application-specific settings.

## Running the Application

To start the application:
```bash
java -jar target/GameAuthApplication.jar server config.yml
```
Ensure that the configuration file (`config.yml`) and all necessary dependencies are in place.

## Dependencies

- Java 8+
- Dropwizard (io.dropwizard:dropwizard-core)
- SLF4J for logging
- Jackson for JSON processing
- JAX-RS for REST API definitions
