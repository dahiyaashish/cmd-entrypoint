# Welcome to cmd v/s entrypoint module

## Docker CMD

    $ git clone git@github.com:dahiyaashish/cmd-entrypoint.git
    $ cd cmd-entrypoint/cmd
    $ docker build -t cmdimage . #You can change the cmdimage name to any name

### Running a Docker Container with CMD

To see CMD in action, we’ll create a container based on the image made in the previous step.  
Run the container with the command:

```output
sudo docker run [image_name]
```

![Starting a container to test Docker CMD instruction.](https://github.com/dahiyaashish/cmd-entrypoint/blob/main/assets/cmd1.png)

Since there is no command-line argument, the container will run the default CMD instruction and display the  `Hello World`  message. However, if you add an argument when starting a container, it overrides the CMD instruction.

```output
sudo docker run [image_name] hostname
```

Docker will run the container and the  `hostname`  command instead of the CMD’s echo command. You can see this in the output.

![Example of how to override Docker CMD when starting a container.](https://github.com/dahiyaashish/cmd-entrypoint/blob/main/assets/cmd2.png)

    
## Docker Entrypoint

    $ git clone git@github.com:dahiyaashish/cmd-entrypoint.git
    $ cd cmd-entrypoint/entrypoint
    $ docker build -t entrypointimage . #You can change the entrypointimage name to any name

### Running a Docker Container with ENTRYPOINT

The output should show you have successfully built the new image under a given name. Now let’s run it as a container without adding any command-line parameters:

```output
sudo docker run [image_name]
```

![Running a container using Docker Entrypoint.](https://github.com/dahiyaashish/cmd-entrypoint/blob/main/assets/entrypoint1.png)

The output will be the same as with CMD. This is because we haven’t added any arguments to the run command.

3. To see how ENTRYPOINT works, you need to add a parameter when starting a container. Use the same command as in the previous step and add something after the image name:

```output
sudo docker run [image_name] KnowledgeBase
```

![Example of how Docker override entrypoint by adding new parameters.](https://github.com/dahiyaashish/cmd-entrypoint/blob/main/assets/entrypoint2.png)

As you see, Docker did not override the initial instruction of echoing Hello World. It merely added the new parameter to the existing command.

## Docker Entrypoint with CMD

    $ git clone git@github.com:dahiyaashish/cmd-entrypoint.git
    $ cd cmd-entrypoint/common
    $ docker build -t cmdentrypointimage . #You can change the cmdentrypointimage name to any name


### Run a Container with Entrypoint and CMD

 Let’s test the container by running it without any parameters. Enter the command:

```output
sudo docker run [image_name]
```

![Docker ENTRYPOINT vs CMD instructions combined.](https://github.com/dahiyaashish/cmd-entrypoint/blob/main/assets/common1.png)

It will return the message  `Hello World`. However, what happens when we add parameters to the docker run command?

Use the same command again, but this time add your name to the run command:

```output
sudo docker run [image_name] [your_name]
```

![Adding parameters to a docker run command to run a container with ENTRYPOINT and CMD instructions.](https://github.com/dahiyaashish/cmd-entrypoint/blob/main/assets/common2.png)

The output has now changed to  `Hello [your_name]`(in my case, it’s  `Hello Ashish`). This is because you cannot override ENTRYPOINT instructions, whereas with CMD you can easily do so.
