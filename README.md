# Estudo de System Design

Desafios diários e curtos (15-20 min) para aprender system design na prática, com revisão e avaliação feitas pelo Claude Code.

## Começando

Pré-requisito: [Claude Code](https://claude.com/claude-code) instalado.

```bash
git clone <url-deste-repositorio> estudo-system-design
cd estudo-system-design
claude
```

Depois é só rodar `/criar-desafio-system-design`. No primeiro uso o `progresso.md` é criado a partir de `progresso.template.md`.

Seus desafios (`desafios/`) e seu histórico (`progresso.md`) **não são versionados** (estão no `.gitignore`): cada pessoa tem o seu próprio percurso. Se quiser guardar o seu, faça um fork e remova essas linhas do `.gitignore`.

## Como usar

| Passo | Comando | O que acontece |
|---|---|---|
| 1 | `/criar-desafio-system-design` | Cria um novo desafio em `desafios/NNN-slug/` personalizado pelo seu histórico. Opcional: passe um conceito, ex. `/criar-desafio-system-design idempotencia`. |
| 2 | — | Escreva sua solução em `desafios/NNN-slug/solucao.md`. |
| 3 | `/revisar-system-design` | Revisão preliminar: perguntas e pontos de atenção para você melhorar a solução. Repita quantas vezes quiser. |
| 4 | `/avaliar-system-design` | Avaliação final com nota 0-10 por critério, solução de referência e temas para estudar. Atualiza `progresso.md`. |

As skills de revisão e avaliação usam o último desafio não avaliado; para outro, passe o id: `/revisar-system-design 003`.

## Estrutura

```
desafios/NNN-slug/
├── desafio.md        # enunciado (status no frontmatter)
├── solucao.md        # sua solução
├── revisoes/         # revisões e snapshots da solução a cada revisão
└── avaliacao.md      # parecer final
progresso.md          # matriz de conceitos, histórico e observações (gerado, não versionado)
progresso.template.md # matriz zerada usada para criar o progresso.md
.claude/skills/       # skills de criar, revisar e avaliar desafios
```

## Dicas

- Sempre justifique **por que** escolheu cada componente, com prós, contras e como mitiga os contras.
- Os termos aparecem em português e inglês — use os termos em inglês para pesquisar mais.
- Veja `progresso.md` para acompanhar sua evolução por conceito.
