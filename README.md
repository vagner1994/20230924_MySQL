# 20230924_MySQL
Configuração Detalhada do Ambiente Docker para MySQL, phpMyAdmin e Apache
Este guia detalhado descreve o processo de criação e execução de um ambiente Docker que inclui os serviços MySQL (ou MariaDB), phpMyAdmin e Apache (ou Nginx). Este ambiente é adequado para o desenvolvimento de aplicativos web que dependem de um banco de dados MySQL e permite o gerenciamento do banco de dados por meio do phpMyAdmin.

Pré-requisitos
Antes de começar, certifique-se de que você tenha o Visual Studio Code instalado em seu sistema, pois usaremos o terminal integrado para executar os comandos Docker. Além disso, certifique-se de ter o Docker e o Docker Compose instalados.

Configuração Passo a Passo
1. Clonar o Repositório
Primeiro, abra o Visual Studio Code e clone o repositório do projeto diretamente no ambiente de desenvolvimento. Isso pode ser feito usando a extensão "Git" ou executando o seguinte comando no terminal integrado:

git clone https://github.com/seu-usuario/seu-repositorio.git
Após o clone, navegue até o diretório do projeto:

cd seu-repositorio
2. Criar o Arquivo .
Dentro do Visual Studio Code, crie um arquivo chamado ".env" diretamente no diretório do projeto e defina as variáveis de ambiente necessárias. Você pode fazer isso usando o terminal integrado ou a interface gráfica. Inclua as seguintes variáveis de ambiente e substitua os valores com suas próprias informações:

MYSQL_ROOT_PASSWORD=sua_senha_root
MYSQL_DATABASE=seu_banco_de_dados
MYSQL_USER=seu_usuario
MYSQL_PASSWORD=sua_senha
PMA_HOST=db
PMA_USER=seu_usuario
PMA_PASSWORD=sua_senha

Certifique-se de substituir sua_senha_root, seu_banco_de_dados, seu_usuario e sua_senha pelos valores desejados.

3. Adicionar sua Aplicação Web
No Visual Studio Code, arraste e solte todos os arquivos da sua aplicação web para a pasta seu_projeto_web no diretório do projeto. Isso garantirá que sua aplicação esteja pronta para ser servida pelo Apache ou Nginx, dependendo da sua escolha.

4. (Opcional) Adicionar Dados Iniciais ao Banco de Dados
Se você precisar de dados iniciais em seu banco de dados MySQL, coloque os scripts SQL na pasta seeds usando o Visual Studio Code.

5. Personalizar o Arquivo docker-compose.yml
Agora, dentro do Visual Studio Code, abra o arquivo docker-compose.yml e personalize-o conforme necessário. Por exemplo, você pode alterar as portas mapeadas ou os nomes dos contêineres de acordo com as necessidades do seu projeto.

Executando o Ambiente
Agora que você configurou tudo, abra o terminal integrado no Visual Studio Code e execute o seguinte comando para iniciar os contêineres:

docker-compose up -d
Isso criará e iniciará os contêineres conforme definidos no arquivo docker-compose.yml.

Acesse o phpMyAdmin em http://localhost:8084 (ou a porta que você configurou) usando seu navegador para gerenciar o banco de dados MySQL. Utilize as credenciais definidas no arquivo .

Acesse sua aplicação web em http://localhost:8081 (ou a porta que você configurou) para visualizar e testar sua aplicação em execução.

Se você precisar de acesso direto ao servidor MySQL, use um cliente MySQL no terminal integrado com o seguinte comando:

mysql -h localhost -P 3307 -u seu_usuario -p
Substitua seu_usuario pelas credenciais definidas no arquivo .

Encerrando o Ambiente
Para parar e remover os contêineres e volumes, você pode usar o terminal integrado no Visual Studio Code e executar o seguinte comando:

docker-compose down
Isso encerrará os contêineres e limpará os volumes, garantindo que a próxima execução comece com um ambiente limpo. Seus arquivos de aplicação web no diretório local não serão afetados.

Personalização Adicional
Lembre-se de que este ambiente Docker pode ser personalizado ainda mais para atender às necessidades específicas do seu projeto. Consulte a documentação oficial do Docker e Docker Compose para obter mais informações sobre as opções de configuração disponíveis.
