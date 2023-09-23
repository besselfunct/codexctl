<p align="center">
<img src="media/demoLocal.gif">

# Codexctl
A utility program that helps to manage the remarkable device version utilizing [ddvks update server](https://github.com/ddvk/remarkable-update) 

### Installation & Use

This program can be directly ran on the ReMarkable device as well as from a remote device such as your computer, it currently only has support for **command line interfaces** but a graphical interface is soon to come. The steps to install are closely similar apart from the couple of extra depedancies needed for running on a remote device. 

## Downloading compiled binaries
Thanks to @Eeems, you can directly download the compiled binary from the [releases](https://github.com/Jayy001/codexctl/releases/) page! Just select your operating system & download the zip repo containing the binaries - then open up a terminal and run how you would from there. `./codexctl --help` 

## Building from source

```
git clone https://github.com/Jayy001/codexctl.git 
cd codexctl
pip install requests
```

Thats it for running it directly on the remarkable. If you are running on a remote device you will need to run the following too,

```
pip install wheel
pip install -r requirements.txt
```


The script is designed to have as little interactivity as possible, meaning arguments are directly taken from the command to run the script. 

## Usage 

```
❯ python codexctl.py  --help
usage: Codexctl app [-h] [--debug] {install,download,status,restore,list} ...

positional arguments:
  {install,download,status,restore,list}
    install             Install the specified version (will download if not available on the
                        device)
    download            Download the specified version firmware file
    status              Get the current version of the device and other information
    restore             Restores to previous version installed on device
    list                List all versions available for use

options:
  -h, --help            show this help message and exit
  --debug               Print debug info
```

# Examples
```
python codexctl.py install latest # Downloads and installs latest version
python codexctl.py download toltec # Downloads latest version that has full support for toltec
python codexctl.py download 3.0.4.1305 --rm1 # Downloads 3.0.4.1305 firmware file for remarkable 1
python codexctl.py status # Prints current & previous version (can only be used when running on device itself)
python codexctl.py list # Lists all available versions 
python codexctl.py restore # Restores previous version
```
