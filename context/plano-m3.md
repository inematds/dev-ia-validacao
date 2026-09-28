# Módulo 3 · Construir e revisar o diff — plano

Objetivo: um constrói em etapas; o outro revisa o diff com o briefing e o que foi conferido. Laboratório: uma mudança do
piloto com a revisão registrada (`revisao-etapa-N.md`).

| Aula | Tópico | Tipo | Promessa | Prática | Cena (metáfora) |
|---|---|---|---|---|---|
| 11 | Git só o necessário: ver o que mudou | fundamento | criar um branch e ler um `git diff` (− saiu, + entrou) | tarefa, 12 min (terminal ou pedindo ao assistente) | Rafael marca em verde e vermelho as linhas que mudaram entre duas folhas quase iguais |
| 12 | Uma etapa por vez, com o critério colado | ferramenta | pedir a etapa 1 com contexto, critérios e parada; commit ao conferir | prompt, 10 min | Carla monta uma estante prateleira por prateleira, conferindo com um nível |
| 13 | O revisor recebe o diff, não o resumo | ferramenta | pedir revisão com briefing + mudanca.diff + testes.txt; achado em 4 partes | prompt, 10 min | Rafael entrega uma pasta com três folhas separadas por clipes |
| 14 | Imagens: checar antes, inspecionar depois | fundamento | ferramenta e cobrança antes, arquivo real, tamanho de uso, versão irmã | análise, 8 min | Carla compara a ilustração impressa com a miniatura no monitor |
| 15 | Inverter os papéis e registrar a revisão | ferramenta | mudança do piloto com `revisao-etapa-N.md` (corrigido / recusado com motivo) | tarefa, 12 min | Rafael e Carla à mesma mesa, revisando o trabalho um do outro |

Termos definidos no módulo (mesma `data-def` em todas as aulas): Git, branch, commit, diff (+ briefing, critério de aceite,
revisão cruzada, modelo, terminal, vindos do M1).

Comandos usados (conferidos com `--help` em git 2.43 / codex exec): `git switch -c`, `git status`, `git diff`,
`git diff > mudanca.diff`, `git add`, `git commit -m`, `codex exec --sandbox read-only -o review.md "…"`, `claude -p "…" > review-claude.md`.
