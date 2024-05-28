# Parking Control API

[![Java](https://img.shields.io/badge/Java-17-blue)](https://www.oracle.com/java/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.5-brightgreen)](https://spring.io/projects/spring-boot)
![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)

## Descrição

A **Parking Control API** é uma aplicação RESTful criada para gerenciar vagas de estacionamento em prédios. O sistema permite a inserção, atualização, listagem e exclusão de registros de vagas, armazenando informações como placa do carro, bloco, apartamento, entre outros.

A aplicação foi desenvolvida utilizando:
- **Java 17**
- **Spring Boot 3.2.5**
- **Hibernate**
- **MySQL**
- **Lombok**

## Instruções de Instalação

### Pré-requisitos

- **Java 17** ou superior
- **Maven** instalado
- **MySQL** instalado e configurado

### Passos para Instalação

1. Clone o repositório:

    ```bash
    git clone https://github.com/seu-usuario/parking-control.git
    ```

2. Navegue até o diretório do projeto:

    ```bash
    cd parking-control
    ```

3. Configure o banco de dados no arquivo `application.properties`:

    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/parking_control_db
    spring.datasource.username=root
    spring.datasource.password=root
    ```

4. Execute a aplicação utilizando o Maven:

    ```bash
    mvn spring-boot:run
    ```

## Como Utilizar

### Endpoints

#### Adicionar Vaga (`POST /parking-spots`)

```json
{
    "parkingSpotNumber": "101",
    "licensePlateCar": "ABC1234",
    "brandCar": "Toyota",
    "modelCar": "Corolla",
    "colorCar": "Preto",
    "responsibleName": "João Silva",
    "apartment": "101",
    "block": "A"
}
```

## Listar Vagas (GET /parking-spots)
### Exemplo de resposta:
```bash
{
    "content": [
        {
            "id": "uuid-1234",
            "parkingSpotNumber": "101",
            "licensePlateCar": "ABC1234",
            "brandCar": "Toyota",
            "modelCar": "Corolla",
            "colorCar": "Preto",
            "registrationDate": "2023-05-27T14:32:00Z",
            "responsibleName": "João Silva",
            "apartment": "101",
            "block": "A"
        }
    ],
    "pageable": {
        ...
    },
    ...
}
```

## Buscar Vaga por ID (GET /parking-spots/{id})
### Exemplo de resposta:
```bash
{
    "id": "uuid-1234",
    "parkingSpotNumber": "101",
    "licensePlateCar": "ABC1234",
    "brandCar": "Toyota",
    "modelCar": "Corolla",
    "colorCar": "Preto",
    "registrationDate": "2023-05-27T14:32:00Z",
    "responsibleName": "João Silva",
    "apartment": "101",
    "block": "A"
}
```

## Atualizar Vaga (PUT /parking-spots/{id})
```bash
{
    "parkingSpotNumber": "102",
    "licensePlateCar": "DEF5678",
    "brandCar": "Honda",
    "modelCar": "Civic",
    "colorCar": "Branco",
    "responsibleName": "Maria Souza",
    "apartment": "102",
    "block": "B"
}
```

## Excluir Vaga (DELETE /parking-spots/{id})

## Exemplos com Curl
### Adicionar Vaga
```bash
curl -X POST "http://localhost:8080/parking-spots" -H "Content-Type: application/json" -d '{"parkingSpotNumber": "101", "licensePlateCar": "ABC1234", "brandCar": "Toyota", "modelCar": "Corolla", "colorCar": "Preto", "responsibleName": "João Silva", "apartment": "101", "block": "A"}'
```

## Listar Vagas:
```bash
curl -X GET "http://localhost:8080/parking-spots"
```

## Contribuição
### Contribuições são bem-vindas! Siga os passos abaixo para contribuir:
Fork o projeto.<br>
Crie uma branch para sua feature (git checkout -b feature/nova-feature).<br>
Commit suas mudanças (git commit -am 'Adiciona nova feature').<br>
Push para a branch (git push origin feature/nova-feature).<br>
Abra um Pull Request.<br>
