# RH-massages

Red Hat massages management site.

## Starting the application

1. Run `mvn clean install` to build your application
1. Populate DB schema with `java -jar target/Massages-1.0-SNAPSHOT.jar db config config.yml`
1. Start the server application with `java -jar target/Massages-1.0-SNAPSHOT.jar server config.yml`
1. To check that your server application is running enter url `http://localhost:8080`
1. Now go to `react-ui` folder
1. Start the UI application with `npm start`
1. To check that your UI application is running enter url `http://localhost:3000`

## DB environmental variables

The application supports these environmental variables for its database:

| VARIABLE        | MEANING                       | DEFAULT VALUE                             |
| --------------- |------------------------------ | ----------------------------------------- |
| RM_DB_USERNAME  | Database username             | postgres                                  |
| RM_DB_PASSWORD  | Database password             | postgres                                  |
| RM_DB_URL       | Database address              | jdbc:postgresql://localhost:5432/postgres |


## Keycloak setup

The application requires this Keycloak setup to work properly:

| VARIABLE        | VALUE                   |
| --------------- |-------------------------|
| Port            | 9090                    |
| Realm           | Massages                |
| Realm roles     | admin, user             |
| Realm clients   | api-client, ui-client   |

Client `api-client` should connect to the server (correct secret needs to be suplied) and should be set as `bearer-only`.
Client `ui-client` should connect to the ui and should be set as `public` with `http://localhost:3000/*` as its `Redirect URI`.


