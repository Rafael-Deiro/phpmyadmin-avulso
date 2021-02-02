# PHPmyAdmin Avulso

## Instalação do Docker e Docker Compose
### Docker
[Documentação de Instalação](https://docs.docker.com/engine/install/ubuntu/)<br>
[Documentação de Pós Instalação (executar sem sudo)](https://docs.docker.com/engine/install/linux-postinstall/)
- Remover versões antigas com `sudo apt-get remove docker docker-engine docker.io containerd runc`
- Atualizar o APT
    + `sudo apt-get update`
    + `sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common`
- Configurar a chave GPG do Docker com `curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -`
- Verificar a fingerprint da chave `sudo apt-key fingerprint 0EBFCD88`
    + Deve retornar dados de publicação (pub) e uid
- Configurar o repositório do APT `sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"`
- Instalar o Docker com `sudo apt-get update` e `sudo apt-get install docker-ce docker-ce-cli containerd.io`
- Criar o grupo 'docker' com `sudo groupadd docker`
- Entrar no grupo 'docker' com `sudo usermod -aG docker $USER`
- Atualizar os grupos com `newgrp docker`
- Testar o Docker sem sudo `docker run hello-world`

### Docker Compose
[Documentação de Instalação](https://docs.docker.com/compose/install/)
- Baixar a versão mais recente com `sudo curl -L "https://github.com/docker/compose/releases/download/1.28.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose`
- Deixar o arquivo executável com `sudo chmod +x /usr/local/bin/docker-compose`
- Testar a instalação com `docker-compose --version`
    + Caso não funcione, executar `sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose`

---

## Com o Docker e o Docker Compose instalados
- Configurar a senha do usuário root no docker-compose.yml
- Configurar o host do banco de dados no docker-compose.yml
- Executar o comando `docker-compose up -d` no terminal
- O PHPMyAdmin está disponível em [localhost:8080](localhost:8080)