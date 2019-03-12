# Fenics_Tests

## Command for starting Fenics in docker 

	docker run -ti -e DISPLAY=$DISPLAY -p 127.0.0.1:8000:8000   -v  $(pwd):/home/fenics/shared  -v /tmp/.X11-unix:/tmp/.X11-unix   quay.io/fenicsproject/stable:latest

The local directory (cwd) is shared to home/fenics/shared by 

    -v  $(pwd):/home/fenics/shared


The graphics access works by:
    -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix (already included above)

In order for this to work, this command has to be executed before the docker command:

     xhost +

You can test it by viewing an image in the command line, the programm "feh" works perfectly for this task.

install it by typing

    sudo apt update

    sudo apt install feh

in the commandline.

Then you can view an image by using:

    feh /path/to/image.png

But remember: Firing up docker, you have to enter

    xhost +


## Further reading
Interesting resources regarding docker and Fenics:

https://bitbucket.org/fenics-project/docker
https://fenics.readthedocs.io/projects/containers/en/latest/work_flows.html
