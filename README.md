# indycar-bc125at

## Joe's update of the scanner frequencies - each driver has a car #, a primary frequency, and a backup frequency. we want to input the values for each driver's primary (-P) and backup (-B) frequencies in the order of their cars' # per the PDF.
## NOTE: the first slot hould always be the frequency for IMS Radio 454.0000

```csv
Index,Name,Frequency (MHz),Modulation,CTCSS,Delay (sec),Lockout,Priority
1,IMS RADIO,454.0000,auto,none,2,locked,off
2,#2 NEWGARDEN P,464.9250,auto,none,2,locked,off
3,#2 NEWGARDEN B,469.6000,auto,none,2,locked,off
4,#3 MCLAUGHLIN P,466.8250,auto,none,2,locked,off
5,#3 MCLAUGHLIN B,464.6750,auto,none,2,locked,off
```



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
