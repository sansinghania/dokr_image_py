# dokr_image_py
Docker image for Python projects

Intention of this project is to create a docker image that I can use to quickly create a self contained container with Python runtime environnment. This can be used to do quick PoCs without a need to install all the dependecies on to the local machine.

Cammands on the host machine
------------------------------------

// Build the docker image.

docker image build -t <python-docker-image> .



// Create a detached, interactive container from the image.
// Map 'current' directory from host to '/app' directory in the container.
// This allows the code to be sitting on the host machine and accesible via IDE.
// It also starts a terminal session on the container that I can use to run the application inside the container.

docker run -i -t --rm -v "$(pwd)":/app/. --name <container-name> <python-docker-image> /bin/sh