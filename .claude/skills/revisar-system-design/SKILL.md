---
name: revisar-system-design
description: Faz uma revisão preliminar (não final) da solução escrita pelo usuário para um desafio de system design, com perguntas instigantes, lacunas e pontos de atenção, sem entregar a resposta. Use quando o usuário pedir para revisar, dar feedback ou dicas sobre a solução de um desafio. Aceita opcionalmente o id do desafio (ex. "003").
argument-hint: "[id do desafio opcional]"
---

# Revisar solução de System Design (revisão preliminar)

Siga as convenções do `CLAUDE.md` do repositório. O objetivo é fazer o usuário **pensar e melhorar a própria solução** — atue como um entrevistador/mentor socrático, não como quem resolve.

Argumento recebido (id do desafio, pode estar vazio): `$ARGUMENTS`

## 1. Localizar o desafio

- Se `$ARGUMENTS` tiver um id, use `desafios/<id>-*/`.
- Senão, use o desafio de maior id com `status` ≠ `avaliado`. Se não houver, avise e sugira `/criar-desafio-system-design`.
- Se o desafio já estiver `avaliado`, avise e pergunte se quer mesmo revisar.

Leia: `desafio.md`, `solucao.md` e todos os arquivos de `revisoes/` (revisões anteriores e snapshots).

Se `solucao.md` estiver vazio ou só com o template, peça para o usuário escrever a solução e pare.

## 2. Salvar o snapshot

`N` = número desta revisão = `revisoes` do frontmatter + 1.
Copie o conteúdo atual de `solucao.md` para `revisoes/solucao-vN.md` (crie a pasta se preciso).

## 3. Analisar

Avalie a solução contra o cenário, os requisitos e as perguntas-guia, observando:
- **Requisitos:** algum funcional ou não funcional ignorado? Os números foram considerados?
- **Porquês:** cada escolha tem justificativa, **prós, contras e mitigação**? Aponte cada escolha que ficou sem porquê ou só com prós.
- **Falhas e edge cases:** concorrência, timeouts, retentativas (retries), duplicidade, abandono do fluxo, falha de um componente, dados inconsistentes, picos de carga.
- **Escala, disponibilidade, latência e custo:** gargalos (bottlenecks), ponto único de falha (single point of failure).
- **Uso correto dos conceitos:** algum conceito foi usado de forma equivocada? Aponte a confusão com uma pergunta, sem dar a correção pronta (ex.: "cache é compartilhado entre instâncias nessa sua proposta? O que garante atomicidade na verificação + reserva?").
- **Evolução:** se há revisões anteriores, compare com o snapshot anterior — o que foi resolvido e o que continua pendente.

Regras:
- **Não entregue a solução** nem nomeie diretamente a técnica que resolve a lacuna, a menos que o usuário já esteja na 3ª revisão ou mais travado no mesmo ponto — aí dê uma dica mais direta (ainda como pista, com o termo PT/EN para pesquisar).
- No máximo ~5 perguntas principais, priorizadas pelo impacto. Qualidade > quantidade.
- Seja específico: cite trechos da solução do usuário.
- Sempre use os termos em PT + EN.

## 4. Gravar a revisão

Crie `revisoes/revisao-NN.md` (NN com 2 dígitos) com:

```markdown
# Revisão NN — Desafio <id>

_Data: AAAA-MM-DD · Snapshot: solucao-vN.md_

## O que está bom
- ...

## Perguntas para você pensar
1. **<tema curto>** — pergunta concreta citando a solução
...

## Escolhas sem porquê completo
| Escolha | O que falta (porquê / prós / contras / mitigação) |
|---|---|

## Pontos de atenção
- ...

## Evolução desde a revisão anterior
- (omitir na primeira revisão)

## Termos para pesquisar (PT / EN)
- termo (term)
```

Atualize o frontmatter do `desafio.md`: `status: em-revisao` e `revisoes: N`.

## 5. Responder no chat

Resuma em poucas linhas o que está bom e liste as perguntas principais. Diga que ele pode ajustar `solucao.md` e rodar `/revisar-system-design` de novo, ou `/avaliar-system-design` quando estiver satisfeito.
