# static nginx alpine container

This example is using `docker-compose.override.yml` to define development-specific configuration for Docker. 

Since we're only building the container in a development environment, the build configuration for the static container only needs to be in available in `docker-compose.override.yml`.

For development purposes, we make sure that the current contents of the `output/` directory will always be available for Nginx to serve. To achieve this, we only need to mount `output/` as a volume at Nginx's default document root location.

After building the website files using 

`docker-compose run nginx`

We can start serving the static files with 

`docker-compose up -d nginx`

We use `up -d` to start the web server in detached mode and keep it running. We can now look at the website by opening `https://localhost` in a browser.