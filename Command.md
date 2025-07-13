In this project, we will see how to build a docker image & push it to the docker hub using GitHub actions workflow.

Step 1: Create a dockerfile
To build the docker image we need to create a dockerfile.
For this tutorial, I will create a very basic dockerfile and build the image using that.


Create Dockerfile & add the below code to it.
# Use the official Apache HTTP Server image from the Docker Hub
FROM httpd:latest

# Copy a custom 'index.html' into the Apache server's root directory for hosting
COPY ./index.html /usr/local/apache2/htdocs/


The above code will build the image on top of the Apache image using our custom index.html which we will create in the next step

# Create index.html file
Create index.html file & add the below code to it.
<!DOCTYPE html>
<html>
<head>
    <title>Hello World</title>
</head>
<body>
    <h1>Hello, World!</h1>
    <p>This is a simple HTML page served from an Apache server in a Docker container.</p>
</body>
</html>

# Store the docker hub credentials
To push the docker image to docker hub we first need to log into docker hub so, for that we need to store the docker hub’s credentials in the secrets.
In your repository, store the credentials in the secrets.# 