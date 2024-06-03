# The CROWler Docker Support

This repository contains the Dockerfile and the necessary files to build a Docker image for the CROWler tool.

## Prerequisites

To build the Docker image, you need to have Docker installed on your machine.

If you want to use Docker Compose, you'll need it to be installed as well.

## Building the Docker image

Clone this repository to your machine and navigate to the root directory of the repository.

Before you build the Docker image, you need to set some environment variables. You can do this by creating a `.env` file in the root directory of this repository. The `.env` file should contain the following variables:

- `DOCKER_CROWLER_DB_PASSWORD`, this is the password for the CROWler user in
the database (non-admin level).
- `DOCKER_POSTGRES_PASSWORD`, this is the password for the postgres user in
the database (admin level).
- `DOCKER_DB_HOST`, this is the hostname, IP or FQDN of the Postgres database.
You normally set this one with the IP of the host where you're running the
Postgres container.

You can configure more variables in the `.env` file to have more control over the Docker image. However the variables mentioned above are the minimum required to build the Docker image.

After setting the environment variables, you can rename the
`config.default` to `config.yaml` and configure the CROWler tool as you wish.

When done, you can build the Docker image by running the following command:

```bash
./docker-build.sh
```

ANd, if you need to rebuild from scratch, you can run:

```bash
./docker-rebuild.sh
```
