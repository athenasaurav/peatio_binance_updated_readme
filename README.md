# peatio_binance_updated_readme

# Arbitrage Trading Bot Between Binance and Open Source Peatio Deployed Exchange

## On Linux

If you are using Linux as your OS then you can follow the below-mentioned steps:-

Run ```pip install -r requirements.txt``` (Python 2), or ```pip3 install -r requirments.txt``` (Python 3)

Then Run ```pip freeze > requirments.txt```

Finally run ```python3 app.py``` (on Python 3)


## On Windows

If you are using Windows as your OS then use the following steps:-
```
python -m pip install -U pip setuptools
```

Run ```pip install -r requirments.txt``` (Python 2), or ```pip3 install -r requirments.txt``` (Python 3)

Finally run ```python3 app.py``` (on Python 3)


## On Ubuntu Server

If you are using Linux as your OS then you can follow the below-mentioned steps:-

Copy all the files on the server in a folder.

Enter into the folder.

# Installing requirments

Check first if Tmux is installed or not by trying to install tmux ```sudo apt-get install tmux```

Check also if Pyhton3 Pip is installed or not. To check run the command ```sudo apt-get install python3-pip```

To upgrade pip to latest version run the following command : ```pip3 install --upgrade pip```

NOTE: pip has dropped support for Python 2 and 3.5. You will need to use a version-specific branch.
Do the following steps if your python3 version is 2 or 3.5

Step 1: This PPA contains more recent Python versions packaged for Ubuntu. Install ppa by running the following command.

```sudo add-apt-repository ppa:deadsnakes/ppa```

Step 2: Now, update your packages by running the following command.

```sudo apt-get update```

Step 3: install Python version 3.7

```sudo apt-get install python3.7```

Step 4: Install pip by running the following command.

```sudo apt install python3-pip```

Step 5 : Check Pip3 version by ```pip3 --version``` if its latest skip Step 6

Step 6: To upgrade pip3 to latest

```sudo -H pip3 install --upgrade pip```

Step 7 : Set priority of the machine to Python 3.7 we installed

```sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.7 2```

Step 8: Run ```pip install -r requirments.txt``` (Python 2), or ```pip3 install -r requirments.txt``` (Python 3). Prefer to use Python3 always. 

# Change Config File

Update the Config file data as per this tutorial i.e [botdetails](https://github.com/athenasaurav/peatio_binance/blob/main/botdetails.md).


# STEPS to Copy on Same server and run a different Bot

Step 1: Copy the ```peatioeth``` folder using following command

```
cp -r /path/to/directory /path/to/location/new-name

```

Step 2: After copying the directory, get inside the new copied folder (for example : peatiobtc)
```
cd peatiobtc
```
Step 3 : Now we need to update some file names first :
a) Lets update the file name ethapp_1.py, ethapp_2.py, ethapp_3.py to btcapp_1.py, btcapp_2.py and finally btcapp_3.py using following command :
``` 
mv oldfilename.py newfilename.py 
```
            
b) Now lets change the file named eth_program_checker.py to btc_program_checker.py using the following command :
``` 
mv eth_program_checker.py btc_program_checker.py 
```
            
Step 4 : Next we update the ```config.py``` file according to currency we want to use. For this enter into ```config.py``` and then update it.
```
nano config.py
```
Step 5 : Finally lets update the ```btc_program_checker.py``` file to run the program. Enter into the ```btc_program_checker.py``` 
```
nano btc_program_checker.py
```
Next we Search for lines : 
```
    if not is_running("ethapp_3.py"):
```
replace it with 
```
    if not is_running("btcapp_3.py"):
```

Next we Search for lines :
```
        try:
            os.system("python3 ethapp_3.py")
```
replace it with 
```
        try:
            os.system("python3 btcapp_3.py")
```

Step 6 :  After everything is updated, we will use tmux for running this program forever.

# Deploying using Tmux

Firstly use command ```tmux``` to open a tmux screen. 

By default tmux start the screen numbering from 0. You can specify name parameter to name something different the screen which will be easy to remember.

To create a Tmux session with a custom name easy to remember use the following command ```tmux new -s <sessionname or sessionnumber>```

then in the new screen run ```python3 app.py``` (on Python 3)

Voila! you bot has started running.

You can now close the SSH window or come out of screen by pressing `ctrl`+`b` and then `d`

If you would like to see whats happening in your program you can write ```tmux attach -t <screenname or screennumber>```

NOTE: we have deployed with a name ```Bot```.

To kill the screen, run command ```tmux kill-session```

To see the list of all the session, run command ```tmux list-sessions```

You can check the Tmux commands cheatsheet [here](https://github.com/athenasaurav/peatio_binance/blob/main/tmux.md)


