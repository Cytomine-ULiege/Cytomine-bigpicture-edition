# Cytomine BigPicture Edition

[![](https://img.shields.io/github/v/release/Cytomine-ULiege/Cytomine-community-edition)](https://github.com/Cytomine-ULiege/Cytomine-community-edition)
[![](https://img.shields.io/docker/pulls/cytomine/installer)](https://hub.docker.com/r/cytomine/installer/)

Cytomine BigPicture Edition is an assemblage of modules from the Cytomine ULiège Community Edition and additional modules specific to BigPicture (including libraries coming from https://github.com/imi-bigpicture). 

This repository provides way to install Cytomine based on Docker compose.

## Install

Follow the installation procedure described here where you replace all occurences of cytomine-community-edition by cytomine-bigpicture-edition:
https://doc.uliege.cytomine.org/admin-guide/ce/ce-install

## In all cases

The password of the `admin` account is available in the cytomine.yml file : `cat cytomine.yml | grep ADMIN_PASSWORD:`

To learn how to use Cytomine please refer to the [user guide in our documentation](https://doc.uliege.cytomine.org/user-guide/).

Note: All Cytomine data is now stored in docker volumes (Postgres, Mongo, images and download buffers) and no more in folders.

## Import BigPicture datasets

See the procedure to [import datasets](https://github.com/Cytomine-ULiege/Cytomine-bigpicture-edition/wiki/Procedure-to-import-local-BP-datasets-into-a-Cytomine-instance).
