---
id: "{{NNN}}"
titulo: "{{Título curto}}"
data: {{AAAA-MM-DD}}
status: aberto
conceitos: [{{conceito-principal}}, {{conceito-secundario-opcional}}]
nivel: {{1|2|3}}
tempo_estimado: "15-20 min"
revisoes: 0
nota_final: null
---

# Desafio {{NNN}} — {{Título}}

## Cenário

{{2 a 5 frases descrevendo o negócio e o problema concreto. Sem sugerir a solução.}}

## Requisitos

**Funcionais (functional requirements)**
- {{...}}

**Não funcionais (non-functional requirements)**
- {{números concretos quando fizer sentido: usuários, requisições por segundo (RPS), latência p99, disponibilidade, tamanho de dados}}

## Perguntas-guia

1. {{Pergunta que direciona para o conceito principal sem entregar a resposta}}
2. {{...}}
3. {{Pergunta sobre falha/edge case}}

## O que sua resposta deve conter

- Componentes e fluxo principal da solução
- **Por que** cada escolha foi feita, com **prós, contras** e como você mitiga os contras
- Como a solução se comporta em falhas e casos de borda (edge cases)
- {{Estimativa, se o desafio pedir}}

## Glossário (PT / EN)

| Português | English | Em uma frase |
|---|---|---|
| {{termo}} | {{term}} | {{definição curta}} |

> Escreva sua solução em `solucao.md` nesta mesma pasta e depois rode `/revisar-system-design`.
