![Sendero](http://sendero.uy/images/logo-white.png)

# Sendero Generic Client

Sendero Generic Client is a C++ project based on [OpenFrameworks](http://openframeworks.cc/) that works as a template to build client aplications for Sendero Project.

Sendero Clients are the entities that generate the lighting patterns of Sendero. All the clients running send the generated patterns to Sendero Server instance for it to blend and deliver them to the ArtNet device/s and Sendero Streaming Server.

This template makes easier the job of generating colour information through code.

Usage
------------
This project is developed to be compiled in Linux (for now). However, as OpenFrameworks is a cross-platform tool, it is possible to compile it in Windows and OS X with no major difficulties.

 1. Fork this repository and clone it into your `<OF_dir>/apps/myApps/` directory.
 2. Develop your custom behaviour in `SpecificBehaviour.cpp`file. Some guidelines are commented inside the file.

To develop a Web based interaction client (that uses RabbitMQ to receive data from [Sendero Interaction Server](https://github.com/LaboratorioDeMedios/SenderoInteractionServer)), we recommend using [SimpleAmqpClient](https://github.com/alanxz/SimpleAmqpClient) library to interact with RabbitMQ.

Configuration file
------------------
Configurations of the project are made in `bin/data/configuration.xml`. This commented fraction summarizes the configs that can be made:

```
<?xml version="1.0" ?>
<!-- Configuration attributes: -->
<!-- 'address':   IP address of Sendero Client instance -->
<!-- 'port':      TCP port used by Sendero Client instance -->
<!-- 'fps':       times per second that the update function is called. This setting is ignored if 'useServer' is true. In this case the client will use Sendero Server's FPS -->
<!-- 'useServer': 1 ? get 3D model from server + use server's FPS : use custom 3D model and FPS defined in 'fps' attribute.  -->
<Configuration address="localhost" port="5002" fps="24" useServer="1">

<!-- Here can be defined an optional 3D model in the same way as in Sendero Server configuration file. It will be used only if 'useServer' attribute is set to false. -->
   .
   .
   .
</Configuration>
```

--------

For more information about Sendero Project go to the [base repository](https://github.com/LaboratorioDeMedios/SenderoProject).

