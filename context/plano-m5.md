# Módulo 5 · Continuidade: handoff, prime e contexto portátil — plano

Objetivo: trocar de sessão ou de modelo sem explicar tudo de novo. Laboratório: handoff lido e verificado (aula 25).
Fontes: área Claude → Codex do Eventos (núcleo portátil, readback das 5 perguntas), kit agente-claude-codex
(skills `session-handoff` e `prime`: handoff é registro, não autorização; prime só lê), Use Both nível 6.

| Aula | Tópico | Tipo | Promessa | Prática | Visuais | Cena (flux) |
|---|---|---|---|---|---|---|
| 21 | Handoff: o estado num arquivo | ferramenta | escrever onde parou, decisões, pendências e próxima ação exata | tarefa, 10 min | tela 2 casos (sem/com handoff), janela latest.md, lado vaga×exata, tela pedido do handoff | Rafael deixa folha de anotações sobre o teclado no fim do dia (passagem de plantão) |
| 22 | Prime: ler e conferir antes de agir | ferramenta | pedir resumo com fontes e contradições antes de agir | prompt, 10 min | tela prime, janela 4 itens, lado "leu e saiu fazendo" × "leu e esperou", tela contradição | Carla, café, lê a folha deixada junto ao computador |
| 23 | O que importa mora no projeto | fundamento | montar os arquivos mínimos e a ordem de leitura | tarefa, 12 min | lado ferramenta×projeto, janela pasta do piloto, janela AGENTS.md + CLAUDE.md `@AGENTS.md`, lado donos | Carla e colega organizam pastas de papel num arquivo |
| 24 | Trocar de modelo sem recomeçar | fundamento | passar o piloto a outro assistente e conferir com 5 perguntas | prompt, 10 min | lado recomeçar×handoff+prime, janela 4 passos, terminal `codex exec --sandbox read-only -o prime.md`, janela 5 perguntas | Rafael fecha um notebook e trabalha no outro, pasta entre os dois |
| 25 | Segunda opinião e o ciclo + lab | ferramenta | fechar handoff → prime → conferência → crítica no piloto | tarefa, 12 min | tela crítica em conversa nova, lado "funciona em qualquer um" × "conferir no seu ambiente" (/advisor), janela ciclo diário, lado sem×com ciclo | Rafael e Carla: ela lê a folha, ele confere no notebook |

Termos novos (mesma definição em todas as aulas): `prime`, `agents-md` (AGENTS.md), `sandbox`.
`/advisor` tratado como "a conferir no seu ambiente" (síntese: não verificado). Migração completa → curso Claude → Codex.
