# Docker-Example-Wordpress


# Prerequisites
Install Docker: https://docs.docker.com/install/#server
Install Docker Compose: https://docs.docker.com/compose/install/


# Build the project
Now, run docker-compose up -d from your project directory.

This runs docker-compose up in detached mode, pulls the needed Docker images, and starts the wordpress and database containers, as shown in the example below.

$ docker-compose up -d
Creating network "my_wordpress_default" with the default driver
Pulling db (mysql:5.7)...
5.7: Pulling from library/mysql
efd26ecc9548: Pull complete
a3ed95caeb02: Pull complete
...
Digest: sha256:34a0aca88e85f2efa5edff1cea77cf5d3147ad93545dbec99cfe705b03c520de
Status: Downloaded newer image for mysql:5.7
Pulling wordpress (wordpress:latest)...
latest: Pulling from library/wordpress
efd26ecc9548: Already exists
a3ed95caeb02: Pull complete
589a9d9a7c64: Pull complete
...
Digest: sha256:ed28506ae44d5def89075fd5c01456610cd6c64006addfe5210b8c675881aff6
Status: Downloaded newer image for wordpress:latest
Creating my_wordpress_db_1
Creating my_wordpress_wordpress_1
Note: WordPress Multisite works only on ports 80 and/or 443. If you get an error message about binding 0.0.0.0 to port 80 or 443 (depending on which one you specified), it is likely that the port you configured for WordPress is already in use by another service.

# Bring up WordPress in a web browser
At this point, WordPress should be running on port 8000 of your Docker Host, and you can complete the “famous five-minute installation” as a WordPress administrator.

Note: The WordPress site is not immediately available on port 8000 because the containers are still being initialized and may take a couple of minutes before the first load.

If you are using Docker Machine, you can run the command docker-machine ip MACHINE_VM to get the machine address, and then open http://MACHINE_VM_IP:8000 in a web browser.

If you are using Docker Desktop for Mac or Docker Desktop for Windows, you can use http://localhost as the IP address, and open http://localhost:8000 in a web browser.

# Shutdown and cleanup
The command docker-compose down removes the containers and default network, but preserves your WordPress database.

The command docker-compose down --volumes removes the containers, default network, and the WordPress database.