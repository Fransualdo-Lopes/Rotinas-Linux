# Instalação do Python 3.12 no Ubuntu 20.04 com pip3

Este tutorial fornece instruções passo a passo para instalar o Python 3.12 no Ubuntu 20.04, incluindo a configuração do pip e a instalação da biblioteca pandas (extra). 

## Passo 1: Instalar dependência

```
sudo apt-get update
sudo apt-get install -y build-essential libssl-dev libffi-dev zlib1g-dev
```
  
## Passo 2: Baixar e instalar o Python 3.12

```
mkdir ~/python3.12
cd ~/python3.12
wget https://www.python.org/ftp/python/3.12.1/Python-3.12.1.tgz
tar -xzvf Python-3.12.1.tgz
cd Python-3.12.1
./configure --enable-optimizations
make -j$(nproc)
sudo make altinstall
```

## Passo 3: Verificar a instalação do Python 3.12

```
/usr/local/bin/python3.12 --version
```

## Passo 4: Baixar o 'get-pip.py' e instalar o 'pip' para o Python 3.12

```
cd ~
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
/usr/local/bin/python3.12 get-pip.py
```

## Passo 5: Verificar a versão do pip associado ao Python 3.12 

```
/usr/local/bin/python3.12 -m pip --version
```
apos estes comandos sua máquina estará com o Python3 e pip3 instalados. 


## EXTRA: Instalar o 'pandas' para o Python 3.12

```
/usr/local/bin/python3.12 -m pip install pandas

```
Este tutorial considerou as versoes mais atuais do momento consulte o site oficial e 
adapte para a versão que você deseja, consultando o site oficial: https://www.python.org/downloads/

