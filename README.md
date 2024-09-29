# Desenvolvimento local do WordPress Docker

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

## Setup Instructions

1. **Clone o Repositório:**
- Abra um terminal ou prompt de comando.
- Execute o seguinte comando para clonar o repositório:
     ```
     git clone https://github.com/danmccrady/wordpress-docker-local-development.git
     ```

2. **Navegue até o Diretório do Repositório:**
- No terminal, mude para o diretório do repositório com:
     ```
     cd wordpress-docker-local-development
     ```

3. **Execute os comandos de configuração:**
- Defina as permissões de arquivo necessárias:
     ```
     sudo chmod -R 777 *
     ```
     (Este comando concede permissões de leitura, gravação e execução para todos os arquivos no diretório.)
- Inicie os contêineres Docker:
     ```
     docker-compose up -d
     ```
     (Este comando executa seus contêineres Docker em modo desanexado, permitindo que o terminal seja usado para outros comandos enquanto os contêineres são executados em segundo plano.)

4. **Acesse o WordPress:**
Quando os contêineres estiverem funcionando, acesse o assistente de configuração do WordPress navegando até `http://localhost` no seu navegador da web.

5. **Conclua a configuração do WordPress:**
Siga as instruções na tela no assistente de configuração do WordPress para concluir a instalação.

6. **Instruções pós-configuração:**
- Para parar os contêineres Docker, execute:
     ```
     docker-compose down
     ```
- Para visualizar os logs dos seus contêineres Docker, use:     ```
     docker-compose logs
     ```

## Trabalhando com temas e plugins

Após a configuração, você encontrará os temas e plugins padrão do WordPress instalados. Esta configuração permite que você crie ou modifique temas e plugins diretamente dentro dessas pastas. Quaisquer alterações que você fizer serão refletidas em tempo real no seu site de desenvolvimento local.

## Nota pessoal
With over a decade of experience in creating WordPress plugins, I've found this Docker-based environment to be my preferred setup. It's efficient, straightforward, and mirrors the production environment closely, making the development process much smoother.

I hope you find this setup as useful as I have. Happy coding!
