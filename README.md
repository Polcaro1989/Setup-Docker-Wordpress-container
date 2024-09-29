# Desenvolvimento local do WordPress Docker


O servidor está configurado com muitos complementos, sendo grande parte deles necessários para o pleno funcionamento.  
Obs: Esse projeto é bom para personalizar outros projetos web também. 
  
<img src="https://github.com/abraao69/abraao69/blob/main/Navy%20Blue%20Geometric%20Technology%20LinkedIn%20Banner%20(2).png" alt="Logo">
<img src="https://tse1.mm.bing.net/th?id=OIP.4PW5fnl8ImR2VRSTIWzz7gHaCm&pid=Api&P=0&h=180" alt="Logo">

## Introdução
Bem-vindo ao repositório de desenvolvimento local do WordPress Docker! Esta configuração foi projetada para desenvolvedores que buscam um método simplificado e eficiente para estabelecer um ambiente de desenvolvimento local do WordPress. Utilizando o Docker, esta configuração ignora a necessidade de instalações tradicionais de pilha WAMP ou LAMP, oferecendo um processo de configuração rápido e direto.

Nossa configuração Docker-compose mapeia exclusivamente os diretórios de temas e plugins para sua máquina local. Isso permite edição imediata e direta, tornando o ciclo de desenvolvimento significativamente mais rápido e intuitivo.

## Pré-requisitos
Antes de começar, certifique-se de ter o Docker e o Docker-compose instalados em sua máquina. O Docker é uma plataforma para desenvolver, enviar e executar aplicativos dentro de contêineres, e o Docker-compose é uma ferramenta para definir e executar aplicativos Docker de vários contêineres.

### Para Windows:
1. **Docker Desktop para Windows:**
   - Visite o [Docker website](https://www.docker.com/products/docker-desktop) para baixar o Docker Desktop para Windows.
- Execute o instalador e siga as instruções na tela.
- O Docker Desktop inclui o Docker-compose, então nenhuma instalação separada é necessária.

### Para Mac:
1. **Docker Desktop para Mac:**
- Navegue até o [Docker website](https://www.docker.com/products/docker-desktop) para baixar o Docker Desktop para Mac.
- Abra o arquivo `.dmg` baixado e arraste o ícone do Docker para a pasta Applications.
- Abra o Docker na pasta Applications, e o Docker-compose será incluído na instalação.

### Para Linux:
1. **Docker:**
- Para a maioria das distribuições Linux, o Docker pode ser instalado com um gerenciador de pacotes. Por exemplo, no Ubuntu, use: `sudo snap install docker`.
2. **Docker-compose:**
- Instale o Docker-compose usando o gerenciador de pacotes. Por exemplo, no Ubuntu, use: `sudo apt install docker-compose`.

## Instalação do ambiente de desenvolvimento
### Instalação de algumas dependências
```
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```
  

### 
### Instalação do Docker
Para instalação no linux mint segue a url:
https://linuxiac.com/how-to-install-docker-on-linux-mint-21/

```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

```
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

```
sudo apt-get update
```

```
sudo apt-get install docker-ce docker-ce-cli containerd.io
```

Depois de instalado e configurado rode o Docker:
```
sudo service docker start
```

Testar se o serviço Docker está rodando corretamente:
```
sudo docker run hello-world  
```


##
### Docker-Compose - Instalação e configuração:
OBS: EM ALGUNS CASOS PODE ESTAR NO /usr/bin/docker-compose
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

```
sudo chmod +x /usr/local/bin/docker-compose
```

```
docker-compose --version  
```
  
##
### Para usar o Docker sem usar sudo
https://docs.docker.com/engine/install/linux-postinstall/
  
##  
### Configurar para o fuso horário de São Paulo
```
sudo timedatectl set-timezone America/Sao_Paulo
```
  
##
### Adicionar o repositório do PHP:
```
sudo add-apt-repository ppa:ondrej/php
```

##
### Instalar os pacotes do PHP instalado. Verificar com php version.
```
sudo apt-get install -y php8.2-cli php8.2-common php8.2-pgsql php8.2-zip php8.2-gd php8.2-mbstring php8.2-curl php8.2-xml php8.2-bcmath
```

##
### Install Composer
```
curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer
```

```
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php -r "if (hash_file('sha384', 'composer-setup.php') === 'dac665fdc30fdd8ec78b38b9800061b4150413ff2e3b6f88543c636f7cd84f6db9189d43a81e5503cda447da73c7e5b6') { echo 'Installer verified'; } else { echo 'Installer corrupt'; unlink('composer-setup.php'); } echo PHP_EOL;"
php composer-setup.php
php -r "unlink('composer-setup.php');"
```

```
sudo apt-get install composer
```

## 
     ```

## Trabalhando com temas e plugins

Após a configuração, você encontrará os temas e plugins padrão do WordPress instalados. Esta configuração permite que você crie ou modifique temas e plugins diretamente dentro dessas pastas. Quaisquer alterações que você fizer serão refletidas em tempo real no seu site de desenvolvimento local.

