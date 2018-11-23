# Deploy your Python3 Virtual Environment

This repository contains the steps to deploy a Virtual Environment for Python3

Install Virtual Env using pip3:

'''python
mtg@mtgvb:~$ pip3 install virtualenv --user
Collecting virtualenv
  Using cached https://files.pythonhosted.org/packages/7c/17/9b7b6cddfd255388b58c61e25b091047f6814183e1d63741c8df8dcd65a2/virtualenv-16.1.0-py2.py3-none-any.whl
Installing collected packages: virtualenv
Successfully installed virtualenv-16.1.0
'''

Create a folder in which the virtual environment will be hosted:

'''python
mtg@mtgvb:~$ mkdir .env
'''

Initialize and install the virtual environment in the previously created folder:

'''python
mtg@mtgvb:~$ virtualenv .env/freqtrade
Using base prefix '/usr'
New python executable in /home/mtg/.env/freqtrade/bin/python3
Also creating executable in /home/mtg/.env/freqtrade/bin/python
Installing setuptools, pip, wheel...
done.
'''

Load the virtual environment:

'''python
mtg@mtgvb:~$ source .env/freqtrade/bin/activate
(freqtrade) mtg@mtgvb:~$ 
'''

It is possible to see that the virtual environment was successfully loaded by noticing the '(freqtrade)' written before the username in the command line prompt.

Exit the virtual environment:

'''python
(freqtrade) mtg@mtgvb:~$ deactivate
'''
