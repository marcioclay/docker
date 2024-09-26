# Install Compose Ubuntu

## 1 – Criar um diretório para o Docker Compose
Primeiro vamos criar um diretório dentro da diretório do docker, lembrando que o o diretório do docker é oculto por padrão.
```
mkdir -p ~/.docker/cli-plugins/
```
## 2 – Baixar o Docker Compose
Baixe a versão mais recente do Compose diretamente do github.
```
curl -SL https://github.com/docker/compose/releases/download/v2.11.2/docker-compose-linux-x86_64 -o ~/.docker/cli-plugins/docker-compose
```
## 3 – Dar permissões de execução
Depois de baixar vamos dar as devidas permissões para que o Docker Compose seja executável.
```
chmod +x ~/.docker/cli-plugins/docker-compose
```
## 4 – Verificar a instalação
Para ter certeza que tudo deu certo basta entrar com o comando docker compose version.
```
docker compose version
```
Pronto agora você já tem seu ambiente de desenvolvimento com Docker e Compose pronto para trabalhar.
