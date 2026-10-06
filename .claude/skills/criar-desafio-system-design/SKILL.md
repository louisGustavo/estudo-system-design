---
name: criar-desafio-system-design
description: Cria um novo desafio diário e curto (15-20 min) de system design, personalizado a partir do histórico em progresso.md e dos desafios anteriores. Use quando o usuário pedir um novo desafio, exercício ou problema de system design. Aceita opcionalmente um conceito como argumento (ex. "cache", "idempotencia").
argument-hint: "[conceito opcional]"
---

# Criar desafio de System Design

Você vai criar **um** novo desafio em `desafios/NNN-slug/`. Siga as convenções do `CLAUDE.md` do repositório (PT com termos também em EN, não entregar a resposta).

Argumento recebido (conceito desejado, pode estar vazio): `$ARGUMENTS`

## 1. Levantar o histórico

1. Se `progresso.md` não existir (primeiro uso após clonar o repositório), crie-o copiando `progresso.template.md`. Depois leia `progresso.md` (matriz de conceitos, histórico e **Observações para próximos desafios**).
2. Liste `desafios/*/desafio.md` e leia o frontmatter de cada um (`id`, `titulo`, `status`, `conceitos`, `nivel`, `nota_final`).
   Para os 3 desafios avaliados mais recentes, leia também a seção de observações/temas de `avaliacao.md`.
3. Se existir desafio com `status` diferente de `avaliado`, avise o usuário (id, título, status) e pergunte se quer criar outro mesmo assim ou continuar o pendente. Só prossiga se ele confirmar.

## 2. Escolher o(s) conceito(s)

Se `$ARGUMENTS` indicar um conceito, use-o como principal (mapeie para o `id` da matriz; se não existir, adicione uma nova linha à matriz no `progresso.md` com contadores zerados).

Caso contrário, escolha por esta ordem de prioridade:
1. Pontos das **Observações para próximos desafios** ainda não trabalhados.
2. Conceitos com média < 7.
3. Conceitos nunca praticados (`Vezes = 0`) — no começo, prefira fundamentos: `estimativas`, `cache`, `escolha-banco-de-dados`, `load-balancer`, `idempotencia`, `filas`.
4. Repetição espaçada (spaced repetition): conceitos com maior tempo desde a `Última data`.

Regras:
- **1 conceito principal + no máximo 1 secundário**, para caber em 15-20 min.
- **Nível** (1 a 3): 1 se não há histórico ou média geral < 6; 2 se média geral entre 6 e 7.9; 3 se ≥ 8. Para um conceito com domínio `iniciante` ou nunca praticado, use no máximo nível 2.
- **Não repita o cenário de negócio** dos últimos 5 desafios (varie: e-commerce, streaming, fintech, saúde, logística, rede social, jogos, IoT, SaaS B2B, mobilidade…).

## 3. Escrever o desafio

1. Calcule o próximo `NNN` (maior id existente + 1, com 3 dígitos; `001` se não houver) e um `slug` curto em kebab-case sem acentos.
2. Crie `desafios/NNN-slug/desafio.md` a partir de `templates/desafio.md` (nesta pasta da skill), preenchendo tudo e removendo os placeholders `{{...}}`. `data` = data de hoje.
3. Crie `desafios/NNN-slug/solucao.md` a partir de `templates/solucao.md`, trocando `{{NNN}}` pelo id.

Qualidade do enunciado:
- Cenário concreto e realista, problema claro; o usuário deve conseguir responder em 15-20 min.
- Não deve ser trivial: precisa exigir ao menos uma decisão com trade-off real (ex.: consistência vs disponibilidade, custo vs latência, simplicidade vs escala).
- Requisitos não funcionais com números quando ajudarem (usuários, RPS, latência p99, volume de dados) — obrigatório se `estimativas` for um dos conceitos.
- Perguntas-guia que levem ao conceito **sem citar a solução** (pergunte "o que acontece se dois usuários…?" em vez de "use lock distribuído").
- Pelo menos uma pergunta sobre falha ou caso de borda (edge case).
- Glossário PT/EN com 3 a 6 termos relevantes que **o usuário pode precisar**, sem revelar qual é a resposta (inclua também termos de alternativas).
- Se a escolha veio de uma observação do histórico, **não** diga isso no enunciado (evita enviesar); só mencione no chat.

## 4. Responder no chat

Mostre: o enunciado (cenário, requisitos, perguntas-guia), o caminho do `solucao.md` para escrever a resposta, e uma linha explicando por que esse conceito foi escolhido agora (ex.: "reforço de idempotência, nota 5 no desafio 002"). Lembre que o próximo passo é `/revisar-system-design`.
