# Introdução ao GraphQL - GraphQL Go

Este repositório contém uma implementação de exemplo de uma API GraphQL utilizando Go (Golang). Aqui, você encontrará exemplos práticos de como construir e utilizar uma API GraphQL com a linguagem Go.

## Tecnologias Utilizadas

- **Go (Golang)**: Linguagem de programação utilizada para construir a API.
- **GraphQL**: Linguagem de consulta para APIs.
- **Gqlgen**: Ferramenta utilizada para gerar código GraphQL em Go.

## Vantagens do GraphQL

1. **Consulta flexível**: Os clientes podem especificar exatamente quais dados precisam, reduzindo o volume de dados transferidos.
2. **Single Endpoint**: Diferentemente do REST, onde diferentes recursos podem ter endpoints separados, o GraphQL utiliza um único endpoint para interagir com a API.
3. **Tipos Fortes**: GraphQL utiliza um sistema de tipos para definir a forma dos dados que podem ser consultados, garantindo que as consultas são validadas antes de serem executadas.
4. **Documentação Automatizada**: A descrição do esquema de tipos serve como documentação automática da API.

## Conceitos Básicos

### Schema

O schema é o coração de uma API GraphQL. Ele define a forma dos dados que podem ser consultados e como esses dados estão relacionados. Um schema é composto por tipos, que definem a estrutura dos objetos e as operações que podem ser realizadas.

### Tipos

- **Query**: O ponto de entrada para ler dados.
- **Mutation**: O ponto de entrada para modificar dados.
- **Subscription**: Permite que os clientes recebam dados em tempo real.

### Exemplos de Tipos

```graphql
mutation createCategories {
  createCategory(input: {name: "Test", description: "Test"}) {
    id
    name
    description
  }
}

mutation createCourse {
  createCourse(input: {name: "Test", description: "Test", categoryId: "7bf7cdea-1f85-43d0-aabe-38238188f0bd"}) {
    id
    name
  }
}

query queryCategories {
  categories {
    id
    name
    description
  }
}

query queryCategoriesWithCourses {
  categories {
    id
    name
    courses {
      id
      name
    }
  }
}

query queryCourses {
  courses {
    id
    name
  }
}

query queryCoursesWithCategory {
  courses {
    id
    name
    category {
      id
      name
      description
    }
  }
}
```

### Resolvers

Os resolvers são funções que lidam com as operações definidas no schema. Cada campo no schema tem um resolver correspondente que fornece os dados para aquele campo.

## Ferramentas e Ecossistema

- **Gqlgen**: Ferramenta que facilita a criação de servidores GraphQL em Go.
- **GraphiQL**: Uma ferramenta de interface de usuário para testar e explorar APIs GraphQL.

## Como Começar

1. **Definir o Schema**: Crie um arquivo para definir os tipos e as operações que sua API irá suportar.
2. **Implementar Resolvers**: Desenvolva as funções que retornam os dados solicitados pelos clientes.
3. **Configurar o Servidor**: Use o gqlgen para configurar e iniciar o servidor GraphQL.
4. **Explorar e Testar**: Utilize ferramentas como GraphiQL para testar e validar suas consultas e mutações.

## Conclusão

GraphQL é uma poderosa alternativa ao REST, oferecendo consultas flexíveis, um esquema tipado e um ecossistema robusto. Com uma boa compreensão de seus conceitos e ferramentas, você pode criar APIs eficientes e bem documentadas que atendem às necessidades específicas de seus clientes.

## Repositório

Para mais detalhes e exemplos de implementação, consulte o repositório [graphql-go](https://github.com/arthurlopesr/graphql-go).

