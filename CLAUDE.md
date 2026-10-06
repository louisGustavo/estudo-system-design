# Estudo de System Design

Repositório de estudo diário de system design por meio de desafios curtos (15-20 min).
A ideia original completa está em `prompt.md`.

## Fluxo

1. `/criar-desafio-system-design [conceito]` → cria `desafios/NNN-slug/` com `desafio.md` e `solucao.md` (template).
2. O usuário escreve a solução em `desafios/NNN-slug/solucao.md`.
3. `/revisar-system-design [id]` → revisão preliminar socrática, grava `revisoes/revisao-NN.md` e snapshot `revisoes/solucao-vN.md`. Pode ser repetido.
4. `/avaliar-system-design [id]` → notas por critério, parecer final em `avaliacao.md` e atualização do `progresso.md`.

## Convenções

- **Idioma:** tudo em português, mas todo termo técnico aparece também em inglês na primeira menção de cada arquivo, no formato `termo em PT (term in EN)` — ex.: *fila (queue)*, *balanceador de carga (load balancer)*. Quando o termo é usado no dia a dia em inglês (cache, CDN, webhook), manter em inglês e explicar em PT.
- **Porquês:** sempre exigir do usuário a justificativa de cada escolha, com prós, contras e mitigação dos contras.
- **Não entregar a resposta** antes da avaliação final: criação e revisão fazem perguntas, só a avaliação apresenta uma solução de referência.
- **Pastas de desafio:** `desafios/NNN-slug/` com `NNN` sequencial de 3 dígitos e `slug` em kebab-case sem acentos.
- **Frontmatter do `desafio.md`** é a fonte de verdade do status: `aberto` → `em-revisao` → `avaliado`.
- **`progresso.md`** é a memória do aprendizado: só a skill de avaliação altera notas/matriz; a criação lê para personalizar.
- **Versionamento:** `desafios/*` e `progresso.md` são pessoais e ficam no `.gitignore`; cada desenvolvedor que clona o repositório gera os seus. O que é versionado é a estrutura: skills, `progresso.template.md` (matriz zerada, copiada para `progresso.md` no primeiro uso), `CLAUDE.md`, `README.md`. Novos conceitos genéricos podem ser adicionados também ao template.
- **Identificadores de conceito** (usados no frontmatter e no `progresso.md`): ver a matriz em `progresso.md`. Novos conceitos podem ser adicionados como novas linhas.
- Arquivos em UTF-8. Datas no formato `AAAA-MM-DD`.
