Angry Hobo
============

This is a basic MEAN stack setup using Vagrant. There are a million ways out
there to do this, this is going to try and do it as cleanly as possible.

Directory structure

angry-hobo: project root
    - bin: binaries directory containing www startup script
    - cookbooks: contains all Vagrant cookbooks
    - node_modules: the node_modules directory
    - public: all public facing files, ie js, styles and images
    - routes: ExpressJS's route definitions
    - views: all ejs views


The Vagrantfile contains all the configurations for you machine, Vagrant needs this.

The app.js is the entrypoint into the NodeJS application.

`vagrant  up`
Done.
