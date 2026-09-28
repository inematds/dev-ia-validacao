# Módulo 2 · Planejar e criticar — plano

Objetivo: plano em arquivo, criticado pelo outro modelo sobre o mesmo arquivo. Laboratório: `plan-v2.md` do piloto.

| Aula | Tópico | Tipo | Promessa | Prática | Cena / metáfora |
|---|---|---|---|---|---|
| 6 | O plano mora num arquivo | ferramenta | pedir `plan-v1.md` com escopo, suposições, critérios de aceite e riscos, sem implementar | prompt, 10 min | Rafael marca o desenho técnico azul de uma casa (planta antes da obra) |
| 7 | Crítica só leitura: achado com evidência | ferramenta | pedir crítica com falha, evidência, impacto, menor correção (+ gravidade) | prompt, 10 min | Carla anota a margem de um documento com caneta vermelha (revisor de contrato) |
| 8 | Ligar Claude e Codex: três caminhos | fundamento | receber a crítica em `review.md` por comando (`codex exec --sandbox read-only -o`, `claude -p >`) ou manual | tarefa, 12 min | Rafael passa uma folha do notebook para o monitor |
| 9 | Duas rodadas de revisão e ponto | fundamento | responder achados (aceito / rejeitado com evidência / em aberto), parar em 2 rodadas, em aberto vira teste, `claudex:plan` para plano grande | análise, 8 min | Carla fecha uma pasta com duas notas adesivas |
| 10 | Rota inicial, não ranking + lab | ferramenta | fechar `plan-v2.md` (arquivo irmão) com todo critério ligado a teste | tarefa, 12 min | Rafael e Carla comparam a versão rabiscada e a limpa |

Fios do piloto: Rafael = formulário de contato da clínica; Carla = rotina que junta as planilhas de entrega.
Termo novo: `rodada-de-revisao` (aula 9), `plugin`, `cli`, `sandbox`, `git` (aula 8).
Comandos conferidos com `--help` em 28/09/2026: `codex exec` (`--sandbox read-only`, `-o/--output-last-message`,
`--skip-git-repo-check`, `-c`), `claude -p` (`--model`, `--effort`).
