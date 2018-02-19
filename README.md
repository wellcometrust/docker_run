# docker_run.py

A simple python script for running Docker.

This script is intended to make running common Docker tasks less verbose with as few dependencies as possible.

## Example

This will run a Docker container exposing the host Docker socket and making the host AWS credentials available to the container. All arguments after the `--` will be passed to the `docker run` command.

```sh
wget https://raw.githubusercontent.com/wellcometrust/docker_run/master/docker_run.py
chmod u+x docker_run.py

./docker_run.py \
    --dind \
    --aws \ 
    -- \
    --volume /root/app/src:/data \
    --volume /root/lambda_conftest.py:/conftest.py \
    --env INSTALL_DEPENDENCIES=false \
    --env FIND_MATCH_PATHS="/data" --tty \
		wellcome/some_container:latest
 ```
