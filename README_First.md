please take sometime to read the following carefully

# step by step process of running the program.

step 1: Download the zipped files from github, and extract them to your desktop.

in order to do that go to the code section and click on code and click download zip.

after the downloading of the zip file it will be found in downloads extract the file to your desktop. (keep the files in the directory)

cd into it using "cd vagrant-flask-exercise-main" (we have to do it twice, because the way the file is built)

step 2: Downloading vagrant and virtualbox, 

installing virtualbox:

open a new terminal type in,

sudo apt update

sudo apt install virtualbox virtualbox-ext-pack.

installing vagrant: run 3 lines of code

curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

sudo apt-get update && sudo apt-get install vagrant

before continuing to the next step make sure vagrant and virtualbox is installed correctly using the command, 

vagrant --version

virtualbox --version


step 3:


using the terminal cd into the file that was downloaded and extracted from github, and run the command "vagrant up"
the processes of the vm installation will start. (make sure it is extracted before cding into it as it has to be a directory) as mentioned in step 1.

the deployment script will be downloaded into the vm machine using an inline script, and from the deployment script itself the webapp.py will be downloaded. (i know i could also create a path script that doesn't ruquire any downloading that will use the file on the local host computer, that was downloaded from github, but i decided to go with a downloadable file scheme so in an a event that we don't have accsess to the webapp.py and deployment script, and only have accsess to the vagrant file, it will automaticly bring the files from github to the vm machine). (and i also thought that it's cool)

after the vm is brought up the flask web app will be hosted on a specific ip adress,
in order to accsess it you have to type into the web browser, "http://127.0.0.1:5000/hello"
debuging mode is enabled in order to identify any errors while trying to connect.




# running the program using only the terminal (without logging into github)

*another easy way to run the program without loging in into github and only using the terminal (as it was my intention behind why i used downloadable links and inline script instead of path script).

open the terminal

install curl using:

"sudo apt install curl"

then we need to download the vagrant file from github using the raw link,

type into the terminal:

"curl -LJO https://raw.githubusercontent.com/georgef21/vagrant-flask-exercise/main/Vagrantfile"

this will download the file on to the computer.

after downloading it, create a directory and move the file into it, using the commands

"mkdir test"

mv Vagrantfile test

after the file has been moved.

cd into the directory "test"
and run the command "vagrant up"

after the vm is brought up, the flask app will be ran on a specefic ip in order to accsess it type into the browser

"http://127.0.0.1:5000/hello"

to terminate the program type ctrl + c to exit the vm and then run "vagrant destoy" while still being in the test directory.

in order to test the program again run "vagrant reload --provision" in order to reload it and provision it again as i didn't specify for the program to provision everytime it is run. and only on the inetial vagrant up.

using only the terminal is easier and could get the app running in under a minute.


# automating everything

to save time i have created a bash script that will do everything starting from downloading the files and installing the required software to bringing the vm up to running the deployment script.

by runing this script it basicly will do all the steps mentioned in this README file.

the script was uploaded to github.

or you can download it using curl:

type into the terminal

curl -LJO https://raw.githubusercontent.com/georgef21/vagrant-flask-exercise/main/automate

and then type

chmod +x automate

to give it executable permission

to run it:

./automate

* the virtual box policy must be accepted in order to continue,
* to accept it press esc when prompted with the agreement





