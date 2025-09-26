# Projeto de Demonstração: CI/CD

Este é um projeto simples criado para demonstrar um fluxo de Integração Contínua (CI) e Entrega Contínua (CD) utilizando Spring Boot, Maven e GitHub Actions.

## 📚 Links Úteis

  - **Padrões de Commit:** Para manter um histórico de commits limpo e organizado, seguimos o guia do [Conventional Commits](https://github.com/iuricode/padroes-de-commits).
  - **GitHub Actions Marketplace:** Explore outras automações prontas para usar em seus workflows [aqui](https://github.com/marketplace?type=actions).

## 🌐 Endpoints da Aplicação

  - **Listar Cursos:** `http://localhost:8080/api/faculdade/cursos`
  - **Listar Alunos:** `http://localhost:8080/api/faculdade/alunos`
  - **Documentação (Swagger UI):** `http://localhost:8080/swagger-ui.html`

## 🚀 Etapas para Construir este Projeto do Zero


1.  **Acesse o [start.spring.io](https://start.spring.io) com as seguintes configurações:**

      - **Project:** `Maven`
      - **Language:** `Java`
      - **Spring Boot:** `3.5.6` (versão estável mais recente)
      - **Group:** `br.com.faculdade`
      - **Artifact:** `api-demo`
      - **Name:** `api-demo`
      - **Description:** `Projeto de demonstração para CI/CD`
      - **Package name:** `br.com.faculdade.apidemo`

2.  **Adicione as seguintes dependências (Dependencies) ao projeto:**

      - `Spring Web`
      - `Spring Boot DevTools`

3.  Clique em **GENERATE** para baixar o projeto em um arquivo `.zip` e descompacte-o.

4.  Crie o primeiro controller da aplicação no arquivo `FaculdadeController.java`.

5.  Adicionar a dependência do `springdoc-openapi` (Swagger) no arquivo `pom.xml`.

      - Para garantir que todas as dependências sejam baixadas, execute o comando:
        ```bash
        .\mvnw.cmd clean install
        ```

6.  Após o build, inicie a aplicação localmente com o comando:

    ```bash
    .\mvnw.cmd spring-boot:run
    ```

7.  No VS Code, instale a extensão `GitHub Actions`.

8.  Crie o primeiro arquivo de pipeline de CI no caminho `.github/workflows/ci.yml`.

9.  Adicione os primeiros testes unitários à aplicação.

      - Rode os testes localmente para garantir que estão passando:
        ```bash
        .\mvnw.cmd -B package
        ```
      - Simule um erro em um dos testes para ver o build falhar.
      - Faça o commit do código e visualize a execução (com sucesso ou falha) na aba "Actions" do seu repositório no GitHub.

10. Adicione a etapa de `upload-artifact` ao arquivo `ci.yml`.

      - Após a execução bem-sucedida do workflow no GitHub, localize e faça o download do artefato gerado.
      - Execute a aplicação diretamente a partir do arquivo `.jar` baixado:
        ```bash
        java -jar nomedoarquivo-0.0.1-SNAPSHOT.jar
        ```

11. Crie este arquivo `README.md` para documentar o projeto.

12. Faça um commit alterando **apenas** o `README.md` e observe que, com a regra `paths-ignore` no workflow, a pipeline não será executada.

13. Simule um erro nos testes novamente, faça o commit e veja o pipeline falhar no GitHub, demonstrando o funcionamento da Integração Contínua.