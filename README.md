# techos-core-Rayara-Bianca-Duarte-de-Souza
# TechOS Core (Sprint Express)

Repositório criado para o desafio prático individual do Encontro 17, aplicando Git, Requisitos e Programação Orientada a Objetos (POO)[cite: 1].

---

## 1. User Stories (INVEST)

* **US01:** "Como técnico, quero abrir uma Ordem de Serviço para registrar um conserto."[cite: 2]
  * **C.A.01:** Deve validar o ID do cliente[cite: 2].
  * **C.A.02:** O status inicial deve ser sempre 'ABERTA'[cite: 2].

* **US02:** "Como cliente, quero visualizar o status do meu equipamento."[cite: 2]

---

## 2. Requisitos Não-Funcionais (RNF)

* **RNF01 (Segurança):** Sanitização de inputs contra XSS/OWASP no cadastro[cite: 2].
* **RNF02 (Desempenho):** Tempo de resposta na criação de chamados < 2s[cite: 2].

---

## 3. Diagrama de Classes (Mermaid)

```mermaid
classDiagram
    class Usuario {
        <<Abstrata>>
        # int id
        # string nome
        # string email
        + getId() int
        + getNome() string
        + getEmail() string
    }

    class Cliente {
        - string telefone
    }

    class Tecnico {
        - string especialidade
    }

    class OrdemServico {
        - int id
        - Cliente cliente
        - string status
    }

    Usuario <|-- Cliente : Herança
    Usuario <|-- Tecnico : Herança
    OrdemServico --> Cliente : Associa
