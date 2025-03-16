# Banco de Dados Relacional (SQL) na AWS com Amazon RDS

Este projeto demonstra como configurar e interagir com um banco de dados MySQL hospedado no Amazon RDS, utilizando a AWS Lambda para realizar consultas SQL diretamente no banco de dados.

## Serviços Utilizados

- **Amazon RDS**: Serviço de banco de dados relacional gerenciado.
- **AWS Lambda**: Funções serverless para executar código sem precisar provisionar ou gerenciar servidores.
- **MySQL**: Banco de dados relacional para armazenamento de dados.

---

## Passo a Passo

### 1. Criando o Banco de Dados no Amazon RDS

1. Acesse o console AWS e vá para **Amazon RDS**.
2. Clique em **Criar banco de dados**.
3. Escolha a opção **Criação padrão**.
4. Selecione **MySQL** e a versão padrão.
5. Escolha a opção **Free Tier** para aproveitar o nível gratuito.
6. Configure as opções do banco de dados:
   - **Identificador da instância de banco de dados**: `dio-live-db`
   - **Nome de usuário mestre**: `admin`
   - **Senha mestre**: `sua_senha_forte`
   - **Tamanho da instância do banco de dados**: Padrão
   - **Armazenamento**: Configurações padrão
   - **Conectividade**: VPC padrão
   - **Acessível publicamente**: Sim
   - **Segurança VPC**: Padrão
   - **Autenticação de banco de dados**: Senha
7. Clique em **Criar banco de dados**.

---

### 2. Conectando ao Banco de Dados

1. Selecione o banco de dados criado no console AWS.
2. Vá para **Conectividade e segurança** e copie o **endpoint**.
3. No seu cliente MySQL (pode ser no terminal ou ferramenta como o MySQL Workbench), crie uma nova conexão:
   - **Nome da conexão**: `DioLive`
   - **Hostname**: Cole o endpoint copiado.
   - **Nome de usuário**: `admin`
   - **Senha**: A senha definida durante a criação do banco.

---

### 3. Configurando Regras de Segurança

1. Acesse o console AWS e vá para **Segurança** > **Grupos de segurança VPC**.
2. Selecione o grupo de segurança associado ao seu banco de dados.
3. Na seção **Entrada**, edite as regras e adicione uma nova regra:
   - **Tipo**: Todo o tráfego
   - **Origem**: Qualquer lugar
4. Salve as alterações para permitir conexões externas ao banco de dados.

