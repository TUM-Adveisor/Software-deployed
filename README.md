# Adveisor Software
Software running on the raspberry Pi 4 of the remote controlled board game
## Dependencies
Require Python, Kivy (UI Library), pyserial, Stockfish (Chess engine) and its API for Python

## Current Feature
- A working chess display with drag and drop piece movement
- Start a new game with human vs human

## Required steps 
### Getting started
* Install Tools for creating a virtual environment for python  
	```
	python -m pip install --upgrade pip setuptools virtualenv
	```
* Create a new folder on raspbian desktop named adveisor and download the code / clone the repository to the folder and activate the python virtual environment
	```
	python -m virtualenv kivy_venv
	source kivy_venv/bin/activate
	```
* Install [Kivy](https://kivy.org/doc/stable/gettingstarted/installation.html) 
	```
	python -m pip install "kivy[base]" kivy_examples
	sudo apt install libsdl2-dev libsdl2-image-dev libsdl2-mixer-dev libsdl2-ttf-dev
	```
* Install [Stockfish](https://stockfishchess.org/), [Stockfish API for Python](https://pypi.org/project/stockfish/)  and [pyserial](https://pyserial.readthedocs.io/en/latest/pyserial.html)
	```
	sudo apt-get install stockfish
	pip install stockfish==3.21.0
	pip install pyserial
	```
* Follow [3.5 Inch RPI display installation](http://www.lcdwiki.com/3.5inch_RPi_Display) guide to finish the LCD setup (Optional)
	```
	sudo rm -rf LCD-show
	git clone https://github.com/goodtft/LCD-show.git
	chmod -R 755 LCD-show
	cd LCD-show/
	sudo ./LCD35-show 270
	```
* To return to hdmi:
	```
	cd LCD-show/
	 ./LCD-hdmi
	```
### Executing program
* run program by entering 
	```
	python gui.py
	```
#### Please ensure: 
* Path of files are correctly included (kivyLib.py, gui.py)
* Correct serial port (Commonly "/dev/ttyUSB0" or "/dev/ttyACM0") in test.py
* When running without motion system as stand alone: set enable in test.py to False
## Features
- Fully functional chess logic powered by Stockfish with en passant, castling and pawn promotion Implemented
- Fully custom written graphical interface for controlling and visualizing the game board
- Automatically linked reset, newgame, and move function
- Support Human VS Human, Human VS Human (only software), Human VS AI, AI VS AI (POG)
- Support board side switching 

## To be implemented
* Ladders and snake and monopoly game option
* drunk chess
* Integration of visual recognition model to reach autonom chesspiece position and movement detection


## Documentation and further readings 
See [Kivy examples](https://kivy.org/doc/stable/examples/gallery.html) and [Kivy Documentation](https://kivy.org/doc/stable/api-kivy.html)
