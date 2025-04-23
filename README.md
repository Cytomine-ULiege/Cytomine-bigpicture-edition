# Cytomine BigPicture Edition

[![](https://img.shields.io/github/v/release/Cytomine-ULiege/Cytomine-bigpicture-edition)](https://github.com/Cytomine-ULiege/Cytomine-bigpicture-edition)
[![](https://img.shields.io/docker/pulls/cytomine/installer)](https://hub.docker.com/r/cytomine/installer/)

Cytomine Bigpicture Edition is an assemblage of modules from the [Cytomine Community Edition](https://github.com/cytomine/Cytomine-community-edition) and additional modules specific to the BIGPICTURE project (including libraries coming from https://github.com/imi-bigpicture).

This repository provides a way to install Cytomine based on Docker compose.

## Requirements

The requirements to install Cytomine BigPicture edition are:

* [Docker Engine](https://docs.docker.com/engine/install/)
* [Git](https://git-scm.com/)
* Have the **root** permissions on the machine where you want to install Cytomine

## Install

To install Cytomine BigPicture edition, follow the steps below:

1. Clone the repository on your machine:
```bash
git clone https://github.com/Cytomine-ULiege/Cytomine-bigpicture-edition.git
```

2. Enter the cloned repository:
```bash
cd Cytomine-bigpicture-edition/
```

3. Add your configurations in the `cytomine.template` file if you want to change default values (like URLs and/or SMTP setup).

4. Launch the Cytomine installer:
```bash
sudo docker pull cytomine/installer
sudo docker run -v $(pwd):/install --user "$(id -u):$(id -g)" --rm -it cytomine/installer:latest deploy -s /install
```
> This will create all the folders and files necessary to launch Cytomine with Docker Compose

5. Launch cytomine:
```bash
sudo docker compose up -d
```

Cytomine is now ready to be used!

If you have kept the default values in `cytomine.template`, Cytomine is available at <http://localhost>.

By default, an `admin` account has been created. To connect to Cytomine in your browser, retrieve the admin password by opening the generated `cytomine.yml` file and looking for the `ADMIN_PASSWORD` key, as shown in the snippet below:

```yaml
services:
  default:
    bioformat:
      constant:
        BIOFORMAT_PORT: 4321
    core:
      constant:
        ADMIN_PASSWORD: <generated-password>
```

or by running the following command:

```bash
cat cytomine.yml | grep ADMIN_PASSWORD:
```

> To follow the community edition installation procedure, the documentation is available at <https://doc.uliege.cytomine.org/admin-guide/bp/installation>

## Import BigPicture datasets

See the procedure to [import datasets](https://github.com/Cytomine-ULiege/Cytomine-bigpicture-edition/wiki/Procedure-to-import-local-BP-datasets-into-a-Cytomine-instance).
