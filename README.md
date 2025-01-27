# | Projeto Intensivão DevSuperior
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/MathCouti/DevSuperior-dslist-intensivao/blob/main/LICENSE)

## | Sobre o projeto
O projeto foi desenvolvido durante um intensivão de 1 semana da DevSuperior, onde construimos uma API de lista de jogos, onde também é possivel mover a posição dos games na lista

## | Modelo de domínio do projeto
![modelo de dominio](https://github.com/MathCouti/Assets/blob/main/Intensivao-java-devsuperior-2025/modelo%20de%20dominio.png)

## | Tecnologias utilizadas
### BACK-END
- Java
- Spring Boot
- JPA / Hibernate
- Maven
- Postgres

## | Como executar o projeto
### Pré-requisitos
- **Java 21** ou superior instalado
- **Maven** instalado
- **Postman** (ou similar) para testar os endpoints
- Banco de dados (no projeto temos o perfil test usando banco h2 e o perfil prod usando o banco POSTGRES)

### Como executar o projeto
1. Clone o projeto
   ```bash
   git clone https://github.com/MathCouti/DevSuperior-dslist-intensivao.git
   ```
2. Entre na pasta do projeto
   ```bash
   cd DevSuperior-dslist-intensivao
   ```
3. Execute o projeto
   ```bash
   ./mvnw spring-boot:run
   ```

## | Endpoints da API
### [GET] /games
Retorna a lista de todos os jogos.

#### Exemplo de resposta:
```json
[
  {
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 2,
    "title": "Red Dead Redemption 2",
    "year": 2018,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/2.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  }
]
```
### [GET] /games/1
Retorna um jogo específico pelo id.

#### Exemplo de resposta:
```json
[
  {
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  }
]
```
### [GET] /lists
Retorna as listas de jogos

#### Exemplo de resposta:
```json
[
  {
    "id": 1,
    "name": "Aventura e RPG"
  },
  {
    "id": 2,
    "name": "Jogos de plataforma"
  }
]
```
### [GET] /lists/1/games
Retorna uma lista especifica de jogos

#### Exemplo de resposta:
```json
[
  {
    "id": 1,
    "name": "Aventura e RPG"
  }
]
```

### [POST] /lists/1/replacement
Atualiza a posição dos jogos na lista.
### Exemplo do Body:
```json
{
	"sourceIndex": 5,
  "destinationIndex" : 0
}
```

#### Exemplo de resposta antes da mudança: 
```json
[
  {
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 2,
    "title": "Red Dead Redemption 2",
    "year": 2018,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/2.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 3,
    "title": "The Witcher 3: Wild Hunt",
    "year": 2014,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/3.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 4,
    "title": "Sekiro: Shadows Die Twice",
    "year": 2019,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/4.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 5,
    "title": "Ghost of Tsushima",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/5.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  }
]
```


#### Exemplo de resposta depois da mudança: 
```json
[
  {
    "id": 5,
    "title": "Ghost of Tsushima",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/5.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 1,
    "title": "Mass Effect Trilogy",
    "year": 2012,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/1.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 2,
    "title": "Red Dead Redemption 2",
    "year": 2018,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/2.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 3,
    "title": "The Witcher 3: Wild Hunt",
    "year": 2014,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/3.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  },
  {
    "id": 4,
    "title": "Sekiro: Shadows Die Twice",
    "year": 2019,
    "imgUrl": "https://raw.githubusercontent.com/devsuperior/java-spring-dslist/main/resources/4.png",
    "shortDescription": "Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit esse officiis corrupti unde repellat non quibusdam! Id nihil itaque ipsum!"
  }
]
```

# | Autor
Matheus Coutinho de Paula
[Linkedin](https://www.linkedin.com/in/matheus-coutinho-de-paula-pcd-804197287/)
