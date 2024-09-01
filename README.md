
# Minimal Environment for `pip-compile`

This work is forked from midnighter.

[![Docker image CI](https://github.com/saurabheights/pip-compile/actions/workflows/docker-image.yml/badge.svg)](https://github.com/saurabheights/pip-compile/actions)
[![Docker image pulls](https://img.shields.io/docker/pulls/saurabheights/pip-compile)](https://hub.docker.com/r/saurabheights/pip-compile)
[![License](https://img.shields.io/badge/license-Apache--2.0-blueviolet)](https://opensource.org/licenses/Apache-2.0)

A minimal Docker image that provides a Python environment with
[`pip-tools`](https://pypi.org/project/pip-tools/) in order to lock requirements files.

## Usage

Simply mount your requirements file to `/opt/requirements` and run the container.  The [Docker entrypoint]
(https://docs.docker.com/engine/reference/builder/#entrypoint) is
`pip-compile --generate-hashes`, for example,

```
docker run --rm \
    --mount "source=${PWD},target=/opt/requirements,type=bind" \
    saurabheights/pip-compile:3.8-alpine \
    --upgrade --verbose requirements.in
```

This will create a corresponding compiled `.txt` file in the mounted directory;
in this example `./requirements.txt`.

## Python Environments

Images are generated for the following environments. Please [open an
issue](https://github.com/saurabheights/pip-compile/issues/new) if you require
others.

| Tag             | Python | Distribution                                      |
|-----------------|--------|---------------------------------------------------|
| 3.8-alpine      |  3.8  | [Alpine Linux 3.12](https://www.alpinelinux.org/) |
| 3.8-bullseye    |  3.8  |                                                   |
| 3.8-bookworm    |  3.8  |                                                   |
| 3.9-alpine      |  3.9  |                                                   |
| 3.9-bullseye    |  3.9  |                                                   |
| 3.9-bookworm    |  3.9  |                                                   |
| 3.10-alpine     |  3.10 |                                                   |
| 3.10-bullseye   |  3.10 |                                                   |
| 3.10-bookworm   |  3.10 |                                                   |
| 3.11-alpine     |  3.11 |                                                   |
| 3.11-bullseye   |  3.11 |                                                   |
| 3.11-bookworm   |  3.11 |                                                   |
| 3.12-alpine     |  3.12 |                                                   |
| 3.12-bullseye   |  3.12 |                                                   |
| 3.12-bookworm   |  3.12 |                                                   |

## Copyright

* Copyright © 2024 Saurabh Khanduja.
* Free software licensed under the [Apache Software License 2.0](LICENSE).
