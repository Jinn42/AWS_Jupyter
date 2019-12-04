# AWS_Jupyter
## Objective

## -Create a virtual machine
launch an instance using Ubuntu Server 18.04
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/Utunbu%2018.04.png)
## -Check if pthon3 is installed
```
python3
```
Result:
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/python3.png)

## -Open python file from local file to virtual machine in another terminal
```
cd Downloads
scp -i JB_keypair.pem asdfgh.py
ubuntu@ec2-54-144-146-229.compute-1.amazonaws.com:
```
## -Then check in virtual machine
```
ls
python3 asdfgh.py
```

## -Install pip
```
sudo apt-get update -y
sudo apt-get python3-pip
```
## -Install Jupyter
```
sudo pip3 install jupyter

```
## -Open Jupyter Notebook
```
nohup jupyter notebook - - ip=0.0.0.0 &
```
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/openjupyter.png)

## -edit security group inbound, add gate 8888
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/gate8888.png)
## -type site on browser
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/site.png)
