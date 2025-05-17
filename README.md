# indycar-bc125at

## *_do all of this on your Raspberry Pi device which you ssh into. plug the BC125AT into the pi's usb port_* 

1. update and upgrade APT packages on pi, then install python3 requirements
```shell
sudo apt update
sudo apt full-upgrade -y
sudo apt install python3 python3-venv python3-pip python3-dev
```
2. clone repo *on Raspberry Pi device you can ssh into*
```shell
git clone git@github.com:neherdata/indycar-bc125at
```
3. cd into repo
```shell
cd indycar-bc125at
```
4. create new virtual environment
```shell
python3 -m venv .venv
```
5. activate virtual environment
```shell
source .venv/bin/activate
```
6. install requirements
```shell
sudo python3 -m pip install -r requirements.txt --break-system-packages
```
7. confirm install worked
```shell
sudo bc125py -h
```
8. test connection to radio
```shell
sudo bc125py test
```
