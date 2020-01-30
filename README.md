# AWS_Jupyter

## 1.Install Jupyter & open file in virtual machine

## -Create a virtual machine
launch an instance using Ubuntu Server 18.04
![](https://github.com/Jinn42/AWS_Jupyter/blob/master/Utunbu%2018.04.png)
## -Check if python3 is installed
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
sudo apt-get install python3-pip
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

54.144.146.229:8888/?token=a64829c17a8243edec6f4b2bd32a8729e1328d3d3eed89ca

(IPv4 Public IP) : (gate address shown on terminal)

## 2.Create virtual environment(by pew or conda) and link it to jupyter

## Use conda

- create a new directory
```
mkdir tmp
```
- Logged into the Ubuntu 18.04 server as a sudo non-root user, move into the /tmp directory and use curl to download the link you copied from the Anaconda website:
```
cd tmp/
curl -O https://repo.anaconda.com/archive/Anaconda3-2019.03-Linux-x86_64.sh
```
- Check with 'ls'

- Run the Anaconda Script
```
bash Anaconda3-2019.03-Linux-x86_64.sh
```
- Create Anaconda Environment
```
conda create -n Jin python=3.7
```
- Activate the new environment
```
conda activate Jin
```
- Link to Jupyter
```
pip3 install --user ipykernel

python -m ipykernel install --user --name=Jin
```
- Remove virtual environment
```
conda env remove -n Jin
```
## Use pew

- Install pew and create a new pew environment
```
pip3 install pew
```
```
pew new Jin2
```
- Exit and go back to thecpew environment
```
exit
```
```
pew workon Jin2
```
- Check current virtual environment
```
pew ls
```
- install pandans and then list everything and store them
```
pip3 install pandas
```
```
pip3 freeze > myEnv.tx
```
- link to Jupyter
```
pip3 install ipykernel

python3 -m ipykernel install --user --name=Jin2
```
- remove the environment
```
pew rm Jin

exit
```
tips:
some codes to create a new environment and link it to Jupyter
```
pew new Jin2

pip3 install -r myEnv.txt

python3 -m ipykernel install --user=Jin2
```

