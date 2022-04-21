# custom_ee

**Update**
My quota for Git Large File Storage is exceeded, but you can still find these images on registry.redhat.io

This repo contains the builder image and base Ansible EE image for running ansible-builder in a disconnected environment.

- ansible-builder-rhel8.tar.gz
- ee-supported-rhel8.tar.gz

Also available is a customized Ansible EE image with Kerberos client installed.

- echong_custome_ee2.tar.gz

These tar.gz files are uploaded using Git Large File Storage [https://git-lfs.github.com/](https://git-lfs.github.com/)

The `disconnected_ee` directory contains necessary build files for disconnected environment.

**Noted** 

- `context/Containerfile` has been modifed after running `ansible-builder build`, make a backup copy before running `ansible-build` command again.
- The `context/pip.conf` is pointing PIP to another server hosting the Pypi repos. Update it with your local Pypi repo information. A temporary one can be created using `pypi-mirror` https://pypi.org/project/python-pypi-mirror/
- To create the context directory, run `ansible-builder create`
- To build a new image, run `podman build -f context/Containerfile -t disconnected_ee`

## Reference
[https://cloudautomation.pharriso.co.uk/post/ansible-builder-disconnected/](https://cloudautomation.pharriso.co.uk/post/ansible-builder-disconnected/)

