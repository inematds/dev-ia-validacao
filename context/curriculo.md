# Dev com IA v6.2 — currículo

Formato: `formato-curso-v6` (skill hoje na 6.3.3) no molde do **OSWork v6.2**: `perfil: tecnico`, `modulos`,
glossário e material complementar. `<meta name="curso" content="devia62">`.

Fontes: `docs/sintese-executiva-2026-09-27.md` (base das afirmações — tem ressalvas e fontes),
`docs/mensagem-nei-2026-09-27.md` (tom e ênfase), e as páginas do Eventos
`~/projetos/inemaeventos/codex-claude/` e `~/projetos/inemaeventos/claude-codex/` (seis níveis do Use Both,
tabela de rotas, comandos `codex exec` / `claude -p`, handoff e prime, núcleo portátil).

## Passo 0 — descoberta (aprovado pelo Nei em 28/09/2026: propostas aceitas, 30 aulas, vídeos pelo explicavideos v2)

1. **Aluno (proposta):** quem já usa Claude Code ou Codex para produzir código ou automações e aceita o resultado
   "porque parece certo". Quer um método para conferir, gastar menos e não depender de um só modelo.
2. **Profissões-alvo (proposta):** **Rafael**, desenvolvedor freelancer que entrega sites e sistemas pequenos para
   clientes; **Carla**, analista de operações que monta automações e relatórios com IA sem ser programadora.
3. **Tecnologia:** usa um assistente de código no terminal ou no app; conhece pasta e arquivo; Git é ensinado do zero
   no módulo 3 (com `.gterm`), só o necessário para ver um *diff*.
4. **Sai fazendo (curso inteiro):** um piloto documentado numa tarefa pequena — briefing com critérios de aceite,
   plano criticado pelo outro modelo, implementação com *diff* revisado, testes, aceite humano, handoff, e uma
   planilha de tempo/consumo/problemas encontrados (a "decisão executiva" da síntese).
5. **Tempo:** aulas de ~15 min; aprofundamento no `details.complementar`.

## Tese do curso (uma frase)

> Gerar ficou fácil; o trabalho agora é **conferir**. Um modelo faz, o outro confere o artefato real, e os testes e
> você decidem.

Regras de conteúdo que o curso inteiro respeita (vindas da síntese, não negociáveis):
- Concordância entre modelos **não é prova**; testes, critérios de aceite e aceite humano fecham o ciclo.
- "Claude planeja / Codex critica" é **rota inicial**, não ranking de desempenho.
- "Pare em duas horas" é pedido, **não trava**: limite real = rodadas, arquivos, timeout, orçamento.
- OpenRouter, modelos abertos e `/advisor` entram como **orientação adicional a conferir no ambiente**.
- "IA vai ficar mais cara" é **hipótese de mercado**; o curso ensina medir custo × resultado por tarefa sem depender dela.
- Nomes de modelos (Claude Opus 5.5, GPT-6 Astra) aparecem com data; o fluxo é mais portátil que os nomes.

## Estrutura

6 módulos × 5 aulas = **30 aulas** (~7h30 de núcleo). Cada módulo fecha com um laboratório na última aula,
que vira uma peça do piloto final. Personagens fixos: Rafael e Carla.

## Módulo 1 · Validar é o trabalho

Objetivo: trocar "parece certo" por "conferi assim". Laboratório: o briefing do piloto.

| Aula | Tópico | Tipo | Promessa | Prática | Gancho |
|---|---|---|---|---|---|
| 1 | Gerar ficou fácil, conferir não | fundamento | apontar num resultado de IA o que você conferiu e o que só aceitou | análise, 8 min | se um modelo não se confere, quem confere? |
| 2 | Duas IAs concordando não é prova | fundamento | dizer o que fecha o ciclo além da opinião de outro modelo | análise, 8 min | então o que é "pronto"? |
| 3 | Critério de aceite antes do código | ferramenta | escrever 3 critérios verificáveis para uma tarefa real | tarefa, 10 min | critérios sem limite viram gasto sem fim |
| 4 | Limite de verdade: rodadas, arquivos, gasto | ferramenta | trocar "pare em 2h" por 3 limites que dá para conferir | prompt, 10 min | com tarefa e limites, falta o mapa |
| 5 | O ciclo em 5 passos + lab do briefing | ferramenta | montar o briefing do seu piloto (objetivo, escopo, aceite, limites) | tarefa, 12 min | módulo 2: um escreve o plano, o outro ataca |

## Módulo 2 · Planejar e criticar

Objetivo: plano em arquivo, criticado pelo outro modelo sobre o mesmo arquivo. Laboratório: `plan-v2.md` do piloto.

| Aula | Tópico | Tipo | Promessa | Prática | Gancho |
|---|---|---|---|---|---|
| 6 | Plano em arquivo, não na conversa | ferramenta | pedir um `plan-v1.md` com escopo, riscos e testes de aceite | prompt, 10 min | quem vai ler esse plano sem piedade? |
| 7 | Crítica só leitura: achado com evidência | ferramenta | pedir crítica com falha, evidência, impacto e menor correção | prompt, 10 min | como chamar o outro sem copiar e colar? |
| 8 | Ligar Claude e Codex: plugin, CLI, PR | fundamento | rodar `codex exec --sandbox read-only` (ou `claude -p`) e ler `review.md` | tarefa, 12 min | e se os dois discordarem para sempre? |
| 9 | Duas rodadas no máximo | fundamento | decidir quando parar o debate e quando usar `claudex:plan` | análise, 8 min | por que começar com Claude no plano? |
| 10 | Rota inicial, não ranking + lab do plano | ferramenta | fechar o `plan-v2.md` do piloto com as críticas resolvidas | tarefa, 12 min | módulo 3: agora alguém constrói |

## Módulo 3 · Construir e revisar o *diff*

Objetivo: um constrói em etapas; o outro revisa o *diff* com o briefing e os testes. Laboratório: primeira mudança revisada.

| Aula | Tópico | Tipo | Promessa | Prática | Gancho |
|---|---|---|---|---|---|
| 11 | Git só o necessário: branch e *diff* | fundamento | criar um branch e ler um `git diff` linha a linha | tarefa, 12 min | o que o revisor precisa receber? |
| 12 | Implementar em etapas com aceite | ferramenta | pedir a 1ª etapa com os critérios do briefing colados | prompt, 10 min | quem confere a etapa? |
| 13 | Revisão do *diff*: briefing + *diff* + testes | ferramenta | pedir ao outro modelo a revisão do *diff*, não do resumo | prompt, 10 min | e quando vale inverter os papéis? |
| 14 | Imagens: checar antes, inspecionar depois | fundamento | conferir ferramenta e cobrança, abrir no tamanho real, salvar versão irmã | análise, 8 min | revisão feita; falta provar |
| 15 | Inverter papéis + lab da mudança | ferramenta | entregar uma mudança do piloto com revisão cruzada registrada | tarefa, 12 min | módulo 4: comprovar e decidir |

## Módulo 4 · Comprovar e decidir

Objetivo: testes pertinentes, comportamento real, decisão humana. Laboratório: o aceite do piloto.

| Aula | Tópico | Tipo | Promessa | Prática | Gancho |
|---|---|---|---|---|---|
| 16 | Que teste prova o quê | fundamento | ligar cada critério de aceite a uma verificação | análise, 10 min | teste passou; o sistema funciona? |
| 17 | Rodar o sistema de verdade | ferramenta | conferir o comportamento real além do teste | tarefa, 10 min | achou problema: quanto corrigir? |
| 18 | A menor correção + uma linha no FALHAS.md | ferramenta | registrar data, falha, menor correção, prompt ou infra | tarefa, 8 min | e o bug que ninguém acha? |
| 19 | Bug difícil: meta com condição de parada | fundamento | escrever meta com sucesso observável e limite de rodadas/gasto | prompt, 10 min | quem aperta o botão final? |
| 20 | Você decide o que entra + lab do aceite | ferramenta | assinar o aceite do piloto com evidência de cada critério | tarefa, 12 min | módulo 5: amanhã, outro assistente continua |

## Módulo 5 · Continuidade: handoff, prime e contexto portátil

Objetivo: trocar de sessão ou de modelo sem explicar tudo de novo. Laboratório: handoff lido e verificado.

| Aula | Tópico | Tipo | Promessa | Prática | Gancho |
|---|---|---|---|---|---|
| 21 | Handoff: o estado num arquivo | ferramenta | escrever decisões, pendências e próxima ação em Markdown | tarefa, 10 min | quem lê isso amanhã? |
| 22 | Prime: ler e verificar antes de agir | ferramenta | pedir a uma sessão nova o resumo com fontes e contradições | prompt, 10 min | onde mora o que não muda? |
| 23 | O cérebro no projeto: AGENTS.md, tasks, context | fundamento | montar as 3 pastas mínimas e a ordem de leitura | tarefa, 12 min | e ao trocar de modelo? |
| 24 | Trocar de modelo sem recomeçar | fundamento | passar o piloto de Claude para Codex (ou o inverso) via prime | prompt, 10 min | segunda opinião dentro do mesmo runtime |
| 25 | Segunda opinião e /advisor (a conferir) + lab | ferramenta | fechar o ciclo handoff → prime no piloto | tarefa, 12 min | módulo 6: quanto isso custou? |

## Módulo 6 · Modelos, esforço e orçamento

Objetivo: escolher modelo e esforço por etapa e medir custo × resultado. Laboratório: relatório do piloto.

| Aula | Tópico | Tipo | Promessa | Prática | Gancho |
|---|---|---|---|---|---|
| 26 | Escolha por tarefa, não por ranking | fundamento | comparar 2 modelos numa tarefa concreta com a régua do módulo 1 | análise, 10 min | mesmo modelo, outro botão: esforço |
| 27 | Esforço de raciocínio por etapa | fundamento | marcar esforço alto/médio/baixo em cada passo do ciclo | análise, 8 min | e o que isso custa? |
| 28 | Medir custo e resultado por tarefa | ferramenta | preencher tempo, consumo e problemas achados do piloto | tarefa, 10 min | preço muda: onde conferir? |
| 29 | Preços, cotas e OpenRouter (a conferir) | fundamento | conferir na sua conta preço, cota e o que é assinatura × API | tarefa, 8 min | hora de decidir se amplia |
| 30 | Decisão executiva: ampliar ou não + lab final | ferramenta | entregar o relatório do piloto e a decisão de ampliar | tarefa, 12 min | continua: Use Both, claudex, Claude → Codex |

## Metáforas de abertura (a validar; inéditas no ecossistema v6)

Revisor de jornal que lê a prova impressa, não o rascunho (A1); dois relógios adiantados iguais (A2);
lista de conferência do piloto de avião (A3); cartão de débito com limite (A4); arquiteto × fiscal de obra (A6);
revisão de contrato por outro advogado (A7); planta × obra entregue (A13); vistoria antes das chaves (A20);
passagem de plantão no hospital (A21); taxímetro ligado (A28).

## Integração com o ecossistema

Continua em: área **Codex + Claude** (Use Both, claudex/iClaudeX) e área **Claude → Codex** (curso de migração,
kit agente-claude-codex). Este curso **não** repete a migração: aponta para lá na aula 23.
