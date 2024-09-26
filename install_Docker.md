# Docker no Ubuntu 22.4

## 1 – Atualizar o Sistema
O primeiro passo é atualizar a lista de pacotes do Ubuntu. Para isso entre com o seguinte comando:

```
sudo apt update
```

## 2 – Instalar pré-requisitos
Instale pacotes de pré-requisitos para permitir ao APT o uso de pacotes seguros HTTPS.

```
sudo apt install apt-transport-https ca-certificates curl software-properties-common
```
## 3 – Adicionar chave GPG
Vamos adicionar a chave para garantir a validade dos pacotes vindos do repositório do Docker.

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```
## 4 – Adicionar repositório Docker ao Ubuntu
Vamos adicionar o repositório Docker as fontes de pacotes do Ubuntu.

```
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```
## 5 – Atualizar a lista de pacotes
Atualize novamente a lista dos pacotes.
```
sudo apt update
```
## 6 – Instalar o Docker
Vamos instalar o Docker no Ubuntu.
```
sudo apt install docker-ce
```
## 7 – Verificar a instalação
Para garantir que tudo deu certo vamos verificar se o Docker está em execução.
```
sudo systemctl status docker
```
```
docker --version
```

Por padrão o comando Docker só pode ser executado pelo usuário usando SUDO. Para facilitar o uso, vamos adicionar nosso usuário do sistema ao grupo docker, assim não precisamos usar SUDO e digitar senha as nossa execuções do comando.
```
sudo usermod -aG docker ${USER}
```
```
su - ${USER}
```
