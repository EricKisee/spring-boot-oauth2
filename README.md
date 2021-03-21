# Spring Boot and OAuth2


This project shows how to implement social login using OAuth 2.0 and Spring Boot.

It uses GitHub and Google as authentication providers with Spring Security on the back end.

## Before Running the Application
***

To use GitHub’s OAuth 2.0 authentication system for login, you must first [Add a new GitHub app](https://github.com/settings/developers).

Select "New OAuth App" and then the "Register a new OAuth application" page is presented. Enter an app name and description. Then, enter your app’s home page, which should be http://localhost:8080, in this case. Finally, indicate the Authorization callback URL as http://localhost:8080/login/oauth2/code/github and click Register Application.

To use Google’s OAuth 2.0 authentication system for login, you must set up a project in the Google API Console to obtain OAuth 2.0 credentials.
Follow the instructions on the [OpenID Connect page](https://developers.google.com/identity/protocols/OpenIDConnect), starting in the section, "Setting up OAuth 2.0".

After completing the "Obtain OAuth 2.0 credentials" instructions, you should have a new OAuth Client with credentials consisting of a Client ID and a Client Secret.

Set the redirect URI to http://localhost:8080/login/oauth2/code/google.

Then configure application.yml

    spring:
      security:
        oauth2:
          client:
            registration:
              github:
                clientId: github-client-id
                clientSecret: github-client-secret
              google:
                client-id: google-client-id
                client-secret: google-client-secret


## Running the Application
***
    .\mvnw spring-boot:run

