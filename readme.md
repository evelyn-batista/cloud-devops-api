# API de Gestão Escolar

Uma API RESTful desenvolvida com FastAPI para gerenciar alunos, cursos e matrículas de uma instituição de ensino. O projeto demonstra práticas modernas de desenvolvimento de API em Python, incluindo o uso de ORM para interação com o banco de dados, validação de dados com Pydantic e containerização com Docker.

## ✨ Principais Funcionalidades

-   **Gestão de Alunos:**
    -   CRUD completo (Criar, Ler, Atualizar, Deletar) para alunos.
    -   Busca de alunos por ID, nome (parcial) e e-mail.
-   **Gestão de Cursos:**
    -   Operações de Criar, Ler e Atualizar para cursos.
    -   Busca de cursos por código único.
-   **Gestão de Matrículas:**
    -   Matricular um aluno em um curso.
    -   Listar todos os cursos em que um aluno está matriculado.
    -   Listar todos os alunos matriculados em um determinado curso.

## 🛠️ Tecnologias Utilizadas

-   **Backend:** Python
-   **Framework:** FastAPI
-   **Banco de Dados:** SQLite
-   **ORM:** SQLAlchemy
-   **Validação de Dados:** Pydantic
-   **Servidor ASGI:** Uvicorn
-   **Containerização:** Docker

## 🚀 Como Executar o Projeto

Siga os passos abaixo para configurar e executar o projeto em seu ambiente local.

## Pré-requisitos

- [Python 3.10+](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)
- [Docker](https://www.docker.com/get-started/) 

### Instalação

1.  **Clone o repositório:**
    ```sh
    git clone https://github.com/evelyn-batista/cloud-devops-api
    cd <NOME_DO_DIRETORIO>
    ```

2.  **Crie e ative um ambiente virtual:**
    ```sh
    # Criar o ambiente
    python -m venv venv

    # Ativar no Windows
    .\venv\Scripts\activate

    # Ativar no Linux/macOS
    source venv/bin/activate
    ```

3.  **Instale as dependências:**
    ```sh
    pip install -r requirements.txt
    ```

4.  **Execute a aplicação:**
    ```sh
    uvicorn app:app --reload
    ```
    O banco de dados `escola.db` será criado automaticamente no primeiro uso.

## 📄 Documentação da API

Com a aplicação em execução, acesse a documentação interativa (gerada pelo Swagger UI) no seu navegador:

----
http://127.0.0.1:8000/docs

Lá você poderá visualizar todos os endpoints, seus parâmetros e testá-los diretamente.

----
## 🐳 Executando com Docker

----
O projeto está configurado para ser executado em um contêiner Docker, garantindo um ambiente isolado e consistente.

1.  **Construa a imagem Docker:**  
    ```sh
    docker build -t gestao-escolar-api .
    ```

2.  **Execute o contêiner:**  
    ```sh
    docker run -p 8000:8000 gestao-escolar-api
    ```
    A API estará disponível em `http://127.0.0.1:8000`.

### Persistindo os Dados com Volumes

Para garantir que os dados do banco de dados SQLite (`escola.db`) não sejam perdidos ao remover o contêiner, você pode mapear um volume do seu host para o contêiner.

-   **Linux/macOS:**
    ```sh
    docker run -p 8000:8000 -v "$(pwd)":/app gestao-escolar-api
    ```
-   **Windows (CMD):**
    ```sh
    docker run -p 8000:8000 -v "%cd%":/app gestao-escolar-api
    ```
Isso fará com que o arquivo `escola.db` seja salvo no diretório do projeto em sua máquina local.

