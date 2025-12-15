# NextCar - Plataforma de Anúncio de Veículos

Bem-vindo ao repositório oficial do projeto NextCar. Este projeto consiste em uma plataforma completa para compra e venda de veículos, desenvolvida como requisito para a competência acadêmica de desenvolvimento Web e Mobile. 

## Índice

- [Visão Geral do Projeto](#visão-geral-do-projeto)
- [Arquitetura](#arquitetura)
- [Tecnologias Utilizadas](#tecnologias-utilizadas)
- [Como Executar](#como-executar)
  - [Pré-requisitos](#pré-requisitos)
  - [Backend (Spring Boot)](#backend-nextcar-back-spring)
  - [Frontend (React)](#frontend-nextcar-front)
  - [Mobile (React Native)](#mobile-nextcar-app)
- [Funcionalidades](#funcionalidades)
- [Autores](#autores)

## Visão Geral do Projeto

O NextCar foi projetado como uma solução de software completa, abrangendo as três principais frentes do desenvolvimento moderno: um servidor robusto, uma interface web e um aplicativo móvel.

O projeto é composto por:

-   **`NextCar-Front`**: Aplicação web (frontend) desenvolvida em React, onde os usuários podem navegar, pesquisar e anunciar veículos.
-   **`NextCar-App`**: Aplicativo móvel para Android e iOS, construído com React Native e Expo, oferecendo uma experiência de usuário nativa e portátil.
-   **`NextCar-Back-Spring`**: O componente central da aplicação (backend). Trata-se de uma API RESTful desenvolvida em Spring Boot que gerencia a lógica de negócios, autenticação de usuários e os dados dos anúncios.
-   **`Banco de Dados`**: Utiliza o MongoDB, um banco de dados NoSQL, escolhido por sua flexibilidade e escalabilidade para gerenciar os dados dos veículos e usuários.

## Arquitetura

A arquitetura do projeto segue um modelo desacoplado, permitindo que os componentes (frontend, backend, mobile) sejam mantidos e atualizados de forma independente.

```mermaid
graph TD
    A[Aplicação Móvel <br> (React Native)] --> C{API RESTful};
    B[Aplicação Web <br> (React)] --> C;
    C --> D[Banco de Dados <br> (MongoDB)];

    subgraph "Backend (Servidor)"
        C[NextCar API <br> (Spring Boot)]
    end

    style A fill:#61DAFB,stroke:#333,stroke-width:2px
    style B fill:#61DAFB,stroke:#333,stroke-width:2px
    style C fill:#6DB33F,stroke:#333,stroke-width:2px
    style D fill:#47A248,stroke:#333,stroke-width:2px
```

-   O **Frontend (Web)** e o **Mobile (App)** atuam como clientes, consumindo os endpoints da API.
-   O **Backend (API)** centraliza todas as regras de negócio, validações e a comunicação com o banco de dados.
-   O **MongoDB** armazena todas as informações de forma persistente.

## Tecnologias Utilizadas

As seguintes tecnologias foram empregadas no desenvolvimento do NextCar:

### Frontend (Web)

-   **React**: Biblioteca para construção de interfaces de usuário.
-   **Vite**: Ferramenta de build e desenvolvimento.
-   **TypeScript**: Superset do JavaScript que adiciona tipagem estática.
-   **CSS**: Para estilização dos componentes.

### Mobile (App)

-   **React Native**: Framework para desenvolvimento de aplicações móveis nativas.
-   **Expo**: Plataforma para simplificar o desenvolvimento e deploy de apps React Native.
-   **TypeScript**: Para garantir a qualidade e manutenibilidade do código.

### Backend (Server)

-   **Java 21**: Linguagem de programação principal do backend.
-   **Spring Boot 3**: Framework para criação de APIs REST.
-   **Maven**: Ferramenta para gerenciamento de dependências e build do projeto.

### Banco de Dados

-   **MongoDB**: Banco de dados NoSQL orientado a documentos.

## Como Executar

Para executar o projeto em um ambiente de desenvolvimento local, siga as instruções abaixo.

### Pré-requisitos

Antes de prosseguir, certifique-se de que os seguintes componentes estejam instalados em sua máquina:

-   [Node.js (versão 18 ou superior)](https://nodejs.org/)
-   [JDK 21 (Java Development Kit)](https://www.oracle.com/java/technologies/downloads/#jdk21)
-   [Maven](https://maven.apache.org/download.cgi) (ou utilize o wrapper `mvnw` incluso no projeto)
-   Uma instância do [MongoDB](https://www.mongodb.com/try/download/community) ativa (local ou em nuvem).

---

### Backend (NextCar-Back-Spring)

1.  **Acesse o diretório do backend:**
    ```bash
    cd NextCar-Back-Spring
    ```

2.  **Configure a conexão com o banco de dados:**
    -   No arquivo `src/main/resources/application.properties`, edite a propriedade `spring.data.mongodb.uri` com a URI de conexão do seu MongoDB.
    ```properties
    spring.data.mongodb.uri=mongodb://localhost:27017/nextcar
    ```

3.  **Inicie o servidor:**
    ```bash
    # Windows
    .\mvnw spring-boot:run

    # Linux / macOS
    ./mvnw spring-boot:run
    ```

    O servidor estará em execução no endereço `http://localhost:8080`.

---

### Frontend (NextCar-Front)

1.  **Acesse o diretório do frontend:**
    ```bash
    cd NextCar-Front
    ```

2.  **Instale as dependências do projeto:**
    ```bash
    npm install
    ```

3.  **Execute a aplicação em modo de desenvolvimento:**
    ```bash
    npm run dev
    ```

    A aplicação web estará acessível em `http://localhost:5173`.

---

### Mobile (NextCar-App)

1.  **Acesse o diretório do aplicativo:**
    ```bash
    cd NextCar-App/nextCarApp
    ```

2.  **Instale as dependências do projeto:**
    ```bash
    npm install
    ```

3.  **Inicie o servidor de desenvolvimento Expo:**
    ```bash
    npx expo start
    ```

4.  **Acesse o aplicativo:**
    -   Um QR Code será exibido no terminal.
    -   Utilize o aplicativo **Expo Go** (disponível para Android e iOS) para escanear o QR Code.
    -   O NextCar App será carregado em seu dispositivo móvel.

    > **Nota**: O dispositivo móvel e o computador devem estar conectados à mesma rede local.

## Funcionalidades

-   [x] Autenticação de Usuários (Cadastro e Login)
-   [x] Visualização de Catálogo de Veículos
-   [x] Funcionalidade de Busca e Filtros
-   [x] Publicação de Novos Anúncios
-   [x] Interface Web e Mobile

## Autores

Este projeto foi desenvolvido por:

-   **[Ítalo de Farias Costa]** - `[https://github.com/ItaloFRS]`
