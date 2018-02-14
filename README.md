# pymedia_systems
Steps to change from main branch of Robocomp to the experimental highly_unstable

## 1.- Deleting last 
	$ sudo rm -r /opt/robocomp
## 2.- Changing the Github branch to the experimental one
	$ cd ~/robocomp
	$ git checkout highlyunstable
	$ git pull #Pulling the new branch
	$ git branch #Checking if we are already on the new one
## 3.- Cleaning remnants of the first installation
	$ cd ~/robocomp
	$ make clean
	$ sudo rm -r build
## 4.- Installing 
	$ cd ~/robocomp
	$ cmake .
	$ cmake-gui .
	#We have to tick the checkbox that says PYTHON_BINDINGS or something along the lines
	make -j4 #4 jobs in parallel
	sudo make install 
##4.1.- If the boost python library is missing (cmake-gui gives away an error)
	$ sudo aptitude install libboost-python-dev
	//All the steps on the fourth step
Aaaaand you're done.

