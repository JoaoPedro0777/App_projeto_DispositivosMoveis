# Proposta de Projeto: App GamerCatalog

## Título
**GamerCatalog - Aplicativo Mobile de Gerenciamento de Jogos**

## Equipe
- Ana Lia Afonso Gomides
- Charley Guimarães Marra da Silva Junior
- João Pedro de Queiroz Martins

## Objetivo
Desenvolver a interface móvel (front-end) utilizando o framework **Flutter** para consumir a API RESTful `gamercatalog_api` desenvolvida na disciplina de Web 2. O objetivo principal é fornecer uma plataforma intuitiva onde os usuários possam explorar catálogos de jogos, favoritar títulos, registrar conquistas e interagir com a comunidade através de avaliações e comentários.

## Público Alvo
Gamers, colecionadores e entusiastas de videogames que desejam centralizar o gerenciamento de suas bibliotecas digitais, acompanhar suas conquistas e avaliar jogos de diferentes estúdios, plataformas e publishers em um único aplicativo.

## Requisitos
Com base na estrutura da API existente, o aplicativo móvel em Flutter terá os seguintes Requisitos Funcionais (RF) e Não Funcionais (RNF):

*   **RF01 - Autenticação e Perfil:** O sistema deve permitir o cadastro, login e gerenciamento de perfil do usuário (módulo `Usuario`).
*   **RF02 - Catálogo de Jogos:** O sistema deve exibir uma listagem de jogos, incluindo detalhes sobre suas expansões (DLCs), plataformas disponíveis, estúdios desenvolvedores e publishers.
*   **RF03 - Interação Social (Avaliações e Comentários):** O usuário deve poder deixar comentários e notas (avaliações) nos jogos que possui ou jogou.
*   **RF04 - Gerenciamento de Favoritos:** O usuário deve poder adicionar e remover jogos de sua lista pessoal de favoritos.
*   **RF05 - Acompanhamento de Conquistas:** O sistema deve exibir as conquistas desbloqueadas ou disponíveis para o usuário vinculadas aos jogos.
*   **RNF01 - Portabilidade:** O aplicativo deve ser multiplataforma, sendo capaz de ser compilado e executado nativamente tanto em dispositivos Android quanto iOS, utilizando o framework Flutter.
*   **RNF02 - Usabilidade:** A interface de usuário (UI) deve ser responsiva, adaptando-se corretamente a diferentes tamanhos de telas e orientações (smartphones e tablets), seguindo as diretrizes do Material Design ou Cupertino.
*   **RNF03 - Desempenho:** As requisições HTTP para a `gamercatalog_api` devem ser tratadas de forma assíncrona para não travar a interface do usuário, utilizando indicadores de carregamento (loading/spinners) durante a busca de dados.
*   **RNF04 - Tolerância a Falhas:** O sistema deve tratar de forma amigável cenários de perda de conexão com a internet ou indisponibilidade da API, exibindo mensagens de erro claras para o usuário em vez de fechar o aplicativo (crash).

## Diagramas

Abaixo estão representados o Fluxo de Navegação das telas do aplicativo e a Arquitetura de comunicação com a API.

### Fluxo de Telas (Navegação)
<img width="1600" height="493" alt="image" src="https://github.com/user-attachments/assets/3d316b5f-10ee-4cf5-a9a6-21465530aba1" />
<img width="972" height="602" alt="image" src="https://github.com/user-attachments/assets/e86bd04d-0632-45d1-9f4e-2ba40e72e814" />

### Arquitetura de Comunicação
<img width="1207" height="92" alt="image" src="https://github.com/user-attachments/assets/ddcd389f-8f7b-4b07-8883-3310a667a109" />
graph LR
    App[Telas em Flutter] --> HTTP[Services HTTP / JSON]
    HTTP --> API[API RESTful Spring Boot]
    API --> BD[(Banco de Dados Relacional)]

## Organização da equipe para desenvolvimento

Para otimizar o tempo e manter a familiaridade com as regras de negócio construídas na etapa da API, a divisão de desenvolvimento das telas em **Flutter** e sua respectiva integração seguirá a mesma divisão adotada no back-end:

*   **Ana Lia:** Responsável pela criação das interfaces e integração (consumo da API) dos fluxos de **Favoritos**, **Comentários** e **Avaliações**.

*   **Charley:** Responsável pela criação das interfaces e integração dos fluxos de **Usuário** (telas de login, cadastro e perfil), **DLCs** e **Conquistas**.

*   **João Pedro:** Responsável pela criação das interfaces e integração dos módulos principais do catálogo: **Jogo**, **Plataforma**, **Estúdio** e **Publisher**.
