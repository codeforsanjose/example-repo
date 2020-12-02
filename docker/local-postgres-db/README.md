# Local PostgreSQL DB
This is a fast way to set up a good "plug and play" dev solution for projects that require a relational database.

Modify `init.sql` with customized SQL statements relevent to your database needs.

## Usage
*   These steps require the `make` utility. 
    *   Additional configuration for this is required on [Windows](https://vispud.blogspot.com/2019/02/how-to-run-makefile-in-windows.html)
1.  Install [Docker](https://www.docker.com/products/docker-desktop)
2.  Create the Docker image for the local DB
    * This only needs to be done once unless new modifcations have been made to `init.sql` since the last time the image was created. See notes below.
    1.  Navigate to `/backend/docker_for_local_dev_db`
    2.  Run command: 
        ```bash
        make image
        ```
3.  Spin up a corresponding Docker container ("Turn it on")
    1.  Navigate to `/backend/docker_for_local_dev_db`
    2.  Run command:
        ```bash
        make container
        ```


### Notes:
If changes are made to `init.sql`, the old docker image must be deleted, regenerated and containerized for the changes to take place.

The command for deleting the previous image is:
```bash
make rm-image
```

After deleting the image with that command, follow steps start from `2.  Create the Docker image for the local DB` again for your local DB to be updated and ready.