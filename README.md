
# Requirements
Make sure that you have the following installed:
- [node](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-18-04) 
- npm 
- [MongoDB](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu/) and start the mongodb service with `sudo service mongod start`

## Navigate to the Client Folder 
 `cd client`

******** ************** ***********

### RUNNING THE APPLICATION WITHOUT DOCKER COMPOSE FILE
## Run the folllowing command to install the dependencies 
 `npm install`

## Run the folllowing to start the app
 `npm start`

## Open a new terminal and run the same commands in the backend folder
 `cd ../backend`

 `npm install`

 `npm start`

 ### Go ahead a nd add a product (note that the price field only takes a numeric input)

 ****** **************** *********** ***********

### RUNNING THE APPLICATION WITH DOCKER COMPOSE FILE
 ## Instructions
- Fork and Clone :  `https://github.com/ActuaryEmma/yolo`
- Change in to yolo directory :  `cd yolo`
- Add MongoDB configuration on server.js file
- Add `Dockerfile` 
- Add `docker-compose.yml` file (more details on `docker-compose.yml` and `docker file` are on `explanation.md` file)
- Run docker compose to install the image and create a container : `sudo docker compose up --build`
- Backend runs on port `5000` and Frontend runs on port `3000`.
- Push images to docker hub : `sudo docker compose push`
- Go ahead a nd add a product (note that the price field only takes a numeric input ) 


## Ansible
*** Installation ***
You need to install ansible, vagrant and virtualbox as per below instructions:
- Follow along with the instructions outlined here in order to install Ansible 
`https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html`
- Instruction to install virtualbox `https://www.virtualbox.org/wiki/Linux_Downloads`
- Instructions to install vagrant `https://developer.hashicorp.com/vagrant/downloads`

*** Create a development environment ***
 - Run `vagrant box add geerlingguy/ubuntu2004`
   Select the “virtualbox” option.
 - Run `vagrant init geerlingguy/ubuntu2004`  . This will create a `Vagrantfile`
 - To boot the server run `vagrant up`
 - Add hosts and ansible.cfg files

 Open the Vagrantfile that was created when we used the vagrant init command. Add the following lines just before the final ‘end’ (Vagrantfiles use Ruby syntax, in case you’re wondering):

  
   `# Provisioning configuration for Ansible.
  config.vm.provision "ansible" do |ansible|
  ansible.playbook = "playbook.yml"
  end `

*** Ansible playbook ***
- Create a file called `playbook.yml`
  Add name of the playbook, hosts, tasks as indicated on the playbook.yml file.

- To run the playbook on our VM. Make sure you’re in the same directory as the Vagrantfile and playbook.yml file, and enter `vagrant provision`

To  run the playbook : ` ansible-playbook playbook.yml`

The playbook has 3 roles:
 1). git : This is to install git .  Git is installed if you want to work on your project on your computer

 2). docker: This is to install docker and docker compose.This allow you to package your application in containers
 
 3). docker-compose: it installs/download the image and container of the application