Angry Hobo
============
This is a basic MEAN stack setup using Vagrant. There are a million ways out
there to do this, this is going to try and do it as cleanly as possible.

Directory structure

    angry-hobo: project root
      - bin: binaries directory containing www startup script
      - cookbooks: Contains all Vagrant cookbooks
      - node_modules: NodeJS modules directory
      - public: All public facing files, ie js, styles and images
      - routes: ExpressJS's route definitions
      - views: all ejs views


The Vagrantfile contains all the configurations for you machine, Vagrant needs this.

The app.js is the entrypoint into the NodeJS application.

Run `vagrant  up` to run the vagrant provision.

Add the following line to your hosts file:

`192.168.123.123 angry-hobo.local`

SSH into the Vagrant VM with `vagrant ssh` and then run the application by changing into the */home/vagrant/workspace/angry-hobo/bin/* directory with `cd ~/workspace/angry-hobo/bin` and running:

`DEBUG=angry-hobo && sudo ./www` (Replacing 'angry-hobo' with your project's name)

You can reach me at zahid@zmhr.me with questions and comments :)
