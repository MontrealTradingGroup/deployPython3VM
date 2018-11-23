# Setup your Ubuntu 18 Virtual Machine for python3

### Option A: Easy/Direct: 

Download our script designed to download and install `pip3` for `python3`:

```
mtg@mtgvb:~$ wget https://raw.githubusercontent.com/MontrealTradingGroup/deployPython3VM/master/python-pip3.sh

--2018-11-23 17:26:07--  https://github.com/MontrealTradingGroup/deployPython3VM/blob/master/python-pip3.sh
Resolving github.com (github.com)... 192.30.253.113, 192.30.253.112
Connecting to github.com (github.com)|192.30.253.113|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘python-pip3.sh’

python-pip3.sh                                         [ <=>                                                                                                             ]  52.60K  --.-KB/s    in 0.04s   

2018-11-23 17:26:10 (1.31 MB/s) - ‘python-pip3.sh’ saved [53858]
```
This command will automatically download [the script python-pip3.sh](https://github.com/MontrealTradingGroup/deployPython3VM/blob/master/python-pip3.sh) hosted in this repository.

Execute the script using:

```
mtg@mtgvb:~$ sh python-pip3.sh
```
You will be prompted for your root password. Once it is done, the Virtual Machine will reboot.

### Option B: Do It Yourself:

Update and upgrade the virtual machine, just in case some of your software is outdated:

```
sudo apt-get update && apt-get upgrade
```

Then, install the package (software) `python3-distutils` which will be necessary to install `pip3`:

```
sudo apt-get install python3-distutils
```

Download the `get-pip.py` script which will be used to install `pip3` automatically:

```
wget https://bootstrap.pypa.io/get-pip.py
```

Execute the script to install `pip3`:

```
python3 get-pip.py --user
```

Reboot your Virtual Machine for the changes to take effect:

```
sudo reboot
```

---

# Deploy your Python3 Virtual Environment

This repository contains the steps to deploy a Virtual Environment for Python3

Install Virtual Env using pip3:

```
mtg@mtgvb:~$ pip3 install virtualenv --user

Collecting virtualenv
  Using cached https://files.pythonhosted.org/packages/7c/17/9b7b6cddfd255388b58c61e25b091047f6814183e1d63741c8df8dcd65a2/virtualenv-16.1.0-py2.py3-none-any.whl
Installing collected packages: virtualenv
Successfully installed virtualenv-16.1.0
```

Create a folder in which the virtual environment will be hosted:

```
mtg@mtgvb:~$ mkdir .env
```

Initialize and install the virtual environment in the previously created folder:

```
mtg@mtgvb:~$ virtualenv .env/freqtrade

Using base prefix '/usr'
New python executable in /home/mtg/.env/freqtrade/bin/python3
Also creating executable in /home/mtg/.env/freqtrade/bin/python
Installing setuptools, pip, wheel...
done.
```

Load the virtual environment:

```
mtg@mtgvb:~$ source .env/freqtrade/bin/activate

(freqtrade) mtg@mtgvb:~$ 
```

It is possible to see that the virtual environment was successfully loaded by noticing the '(freqtrade)' written before the username in the command line prompt.

Exit the virtual environment:

```
(freqtrade) mtg@mtgvb:~$ deactivate
```
