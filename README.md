# Montagem de Partição no Linux via Terminal

Este guia fornece instruções passo a passo sobre como montar uma partição no Linux usando o terminal.

## Passo 1: Identificar as Partições

Para identificar as partições disponíveis no seu sistema, utilize o comando `lsblk` no terminal.

```
lsblk
```
Este comando mostrará uma lista de todas as unidades e partições disponíveis, incluindo seus nomes e tamanhos.

## Passo 2: Criar um Ponto de Montagem
Antes de montar uma partição, você precisa criar um ponto de montagem.

```
sudo mkdir /mnt/minha_particao
```
Um exemplo:
```
sudo mkdir /mnt/sdb2
```
Substitua /mnt/minha_particao pelo caminho desejado para o ponto de montagem.

## Passo 3: Montar a Partição
Agora, você pode usar o comando mount para montar a partição no ponto que acabou de criar.

```
sudo mount /dev/sdXn /mnt/minha_particao
```
Um exemplo:
```
sudo  /mnt/sdb2 /mnt/sdb2
```
Substitua /dev/sdb2 pelo identificador da sua partição (por exemplo, /dev/sda1). Verifique o resultado usando o comando lsblk novamente.

## Passo 4: Automatizar a Montagem na Inicialização
Para garantir que a partição seja montada automaticamente durante a inicialização, adicione uma entrada no arquivo /etc/fstab.

```
echo "/dev/sdXn /mnt/minha_particao ext4 defaults 0 0" | sudo tee -a /etc/fstab
```
Substitua /dev/sdXn pelo identificador da sua partição e /mnt/minha_particao pelo caminho do seu ponto de montagem.

## Passo 5: Desmontar a Partição - extra (Caso queira desmontar a partição)
```
sudo umount /mnt/minha_particao
```