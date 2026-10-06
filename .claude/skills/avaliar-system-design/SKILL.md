---
name: avaliar-system-design
description: Faz a avaliação final de um desafio de system design — notas 0-10 por critério, parecer, solução de referência, temas para estudar — e atualiza progresso.md com observações para personalizar os próximos desafios. Use quando o usuário pedir avaliação final, nota ou fechamento de um desafio. Aceita opcionalmente o id do desafio (ex. "003").
argument-hint: "[id do desafio opcional]"
---

# Avaliar solução de System Design (avaliação final)

Siga as convenções do `CLAUDE.md` do repositório. Agora **pode** revelar a solução de referência.

Argumento recebido (id do desafio, pode estar vazio): `$ARGUMENTS`

## 1. Localizar o desafio

- Se `$ARGUMENTS` tiver um id, use `desafios/<id>-*/`; senão, o de maior id com `status` ≠ `avaliado`.
- Se já estiver `avaliado`, pergunte se quer reavaliar (nesse caso substitua a avaliação e **recalcule** o `progresso.md` sem contar a nota antiga duas vezes).
- Se `solucao.md` estiver vazio/template, peça para escrever e pare.
- Se não houve nenhuma revisão (`revisoes: 0`), pergunte se quer revisar antes; prossiga se ele confirmar.

Leia `desafio.md`, `solucao.md` (versão final) e todos os arquivos de `revisoes/`, para entender a evolução.

## 2. Pontuar (0 a 10, com meio ponto permitido)

| Critério | O que observar |
|---|---|
| Entendimento dos requisitos (requirements) | Cobriu requisitos funcionais e não funcionais, fez suposições explícitas e razoáveis |
| Escolha de componentes (components) | Componentes adequados ao problema, sem excesso (over-engineering) nem falta |
| Justificativas e trade-offs | Cada escolha com porquê, prós, contras e mitigação |
| Escalabilidade, disponibilidade e latência | Gargalos, pontos únicos de falha, comportamento sob carga |
| Falhas e casos de borda (failures & edge cases) | Concorrência, retries, duplicidade, timeouts, abandono, componentes fora do ar |
| Clareza da comunicação | Estrutura, fluxo compreensível, uso correto dos termos |

- **Nota geral** = média simples dos 6 critérios, com 1 casa decimal.
- **Nota por conceito**: para cada conceito do frontmatter, uma nota 0-10 de quão bem ele foi aplicado (é o que alimenta a matriz do `progresso.md`).
- Seja justo e calibrado: 10 = nível de entrevista sênior para o escopo do desafio; 7 = sólido com lacunas menores; 5 = entendeu a ideia mas com lacunas relevantes; < 4 = conceito central errado ou ausente.
- A nota é sobre a **versão final**; a evolução nas revisões aparece no parecer, não infla a nota.

## 3. Escrever `avaliacao.md`

```markdown
# Avaliação — Desafio <id>: <título>

_Data: AAAA-MM-DD · Revisões: N · Nota geral: X.X/10_

## Notas
| Critério | Nota | Justificativa |
|---|---|---|
...

| Conceito | Nota |
|---|---|

## Onde você foi muito bem
- ...

## Onde errou ou pode melhorar
- (específico, citando a solução, explicando o porquê do problema e a alternativa)

## Evolução ao longo das revisões
- ...

## Solução de referência (resumo)
- Componentes, fluxo e decisões-chave com seus trade-offs, em ~10-15 linhas. Mostrar que existe mais de uma resposta válida quando for o caso.

## Temas para estudar
| Tema (PT / EN) | Por quê | O que pesquisar |
|---|---|---|
(aprender algo novo ou aprofundar um conceito com pouca profundidade)

## Observações para os próximos desafios
- Pontos fracos a reforçar e conceitos a combinar em desafios futuros.
```

Atualize o frontmatter do `desafio.md`: `status: avaliado` e `nota_final: X.X`.

## 4. Atualizar `progresso.md`

Se `progresso.md` não existir, crie-o antes copiando `progresso.template.md`.

- **Matriz de conceitos**: para cada conceito do desafio, incrementar `Vezes`, atualizar `Última data`, recalcular `Média` (média de todas as notas daquele conceito nos desafios avaliados — recalcule a partir dos `avaliacao.md` se precisar) e `Domínio` conforme a legenda do arquivo. Conceito novo → nova linha.
- **Resumo**: total de desafios avaliados, média geral (média das notas gerais) e último desafio.
- **Histórico**: adicionar linha `| NNN — título | data | conceitos | revisões | nota |`.
- **Observações para próximos desafios**: adicionar as novas no formato `- [AAAA-MM-DD | desafio NNN] observação`; **remover** as antigas que este desafio mostrou superadas (ex.: nota ≥ 7 no ponto observado). Mantenha no máximo ~8 itens, os mais relevantes. Remova o placeholder "_Nenhuma observação ainda._" se houver itens.

## 5. Responder no chat

Mostre a nota geral, a tabela de notas, 2-3 destaques positivos, 2-3 pontos principais de melhoria e os temas para estudar. Sugira `/criar-desafio-system-design` para o próximo.
