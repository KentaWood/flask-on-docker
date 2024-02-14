# Flask Dockerized with Postgres, Gunicorn, and Nginx
# Description/Format Inspiration from https://github.com/testdrivenio/flask-on-docker 

## Overview
The repository contains a step-by-step tutorial detailing how to configure Flask to run on Docker with Postgres. For production environments, Nginx and Gunicorn are added. The tutorial also covers serving static and user-uploaded media files via Nginx. At the end, a website is created where users can upload images (http://localhost:1328/upload) and view the uploaded files (http://localhost:1328/media/file_name).

### Screenshot of Image Upload
<img width="708" alt="Screenshot 2024-02-13 at 5 37 07 PM" src="https://github.com/KentaWood/flask-on-docker/assets/115967095/e787d92b-c18b-4aac-a50a-4dc92b9ade95">

### Screenshot of Image Uploaded 
<img width="705" alt="Screenshot 2024-02-13 at 5 39 25 PM" src="https://github.com/KentaWood/flask-on-docker/assets/115967095/6f2dd389-3bac-421e-9431-f432b77b0ff9">

## Build Instructions

### DEVELOPMENT

#### Dockerizing Flask with Postgres, Gunicorn, and Nginx

Built from this tutorial: [Dockerizing Flask with Postgres, Gunicorn, and Nginx](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx).

1. Update the environment variables in the docker-compose.yml and .env.dev files.
2. Build the images and run the containers using the following command:
    ```bash
    $ docker-compose up -d --build
    ```
3. Test it out by visiting http://localhost:<Your_chosen_port> to see if the changes you made applied to the site.

### PRODUCTION

1. Add the environment variables and volumes to point to the file of the extra routes you have made.
2. Again, build the image and run the containers using the following command:
    ```bash
    $ docker-compose -f docker-compose.prod.yml up -d --build
    ```
3. Test out the http://localhost:<Your_chosen_port>/upload to upload the image you want the website to hold. Then visit http://localhost:<Your_chosen_port>/media/<file_name_uploaded> to see the file that you had uploaded earlier.
