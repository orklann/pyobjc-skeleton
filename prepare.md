# How to setup the environment for python-pyobjc project

1. Install virtualenv

	virtualenv is a tool to create isolated Python environments. virtualenv creates a folder which contains all the necessary 	executables to use the packages that a Python project would need.

	`pip install virtualenv`

	See - http://docs.python-guide.org/en/latest/dev/virtualenvs/

2. Active virtualenv in current project folder

    You can also use the Python interpreter of your choice (like python2.7).

    $ virtualenv -p /usr/bin/python2.7 my_project
    or change the interpreter globally with an env variable in ~/.bashrc:

    $ export VIRTUALENVWRAPPER_PYTHON=/usr/bin/python2.7

	```shell
	cd my_project_folder
	virtualenv my_project
	source my_project/bin/activate
    source my_project/bin/activate.fish for Fish shell
	```

3. Install PyObjc

	`pip install pyobjc` into current project

4. Install py2app for packaging python project into Mac app bundle

	See - https://allyourco.de/building-a-gui-application-with-pyqt-on-macos/

5. Let's start building app for Mac

    To build a standalone application you run it without the alias option.

    cd to your project directory

	`cd my project/`

    create setup.py project file

	`py2applet --make-setup myapp.py`

    build alias mode for development

	`python3 setup.py py2app -A`

    or build without alias

	`python3 setup.py py2app`

    clean between build

	`rm -rf build dist`

    build release

	`python3.5 setup.py py2app`
