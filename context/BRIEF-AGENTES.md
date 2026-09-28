# Brief para escrever um módulo (M2–M6) — Dev com IA v6.2

Molde: as aulas 1–5 do M1 (`aulas/aula-1.html` … `aula-5.html`), já aprovadas (auditor 10/10, leitor simulado
2 rodadas). Leia `aula-4.html` e `aula-5.html` inteiras antes de escrever: mesma estrutura, mesmo tom, mesmo markup.
Skill: `~/.claude/skills/formato-curso-v6` — leia `references/CONTEUDO-INICIANTE.md`, `V6-DESIGN.md`, `CHECKLIST-V6.md`.

## O que entregar (só nos SEUS arquivos)

- `aulas/aula-N.html` das 5 aulas do seu módulo (tabela em `context/curriculo.md`: tópico, tipo, promessa, prática, gancho).
- `assets/img/aula-N.webp` — `python3 ~/.claude/skills/formato-curso-v6/scripts/gerar-cena.py assets/img/aula-N.webp "<cena>" --gerador flux --seed <N*7>`
  **sempre `--gerador flux`** (Codex image_gen é API, proibido). Uma de cada vez. Olhe cada imagem (converta para jpg e leia);
  se sair errada, troque a cena (não insista no seed). Nada de texto legível, nada de dois objetos idênticos, nada de robô.
  Personagens: **Rafael** (desenvolvedor autônomo, ~40, barba curta, camiseta verde) e **Carla** (analista de operações, ~50,
  cabelo grisalho curto, blusa verde clara). Estilo editorial fixo do script.
- `context/plano-mN.md` — tabela das 5 aulas + metáfora/cena de cada.
- `~/projetos/output/dev-ia-validacao/roteiro/mN-pt.json` — roteiro de vídeo do módulo, no formato de `roteiro/m1-pt.json`
  (abertura "Olá, eu sou Nei Maldaner, e este é o módulo N do curso Dev com IA…", 3–4 cenas por aula, fechamento; ~14.000
  caracteres no total; `kind` ∈ flow|compare|steps|terminal; números e siglas por extenso na fala; "Pause o vídeo e faça a
  prática da aula N" no fim de cada aula). A fala segue o texto da aula, sem fato novo.

NÃO edite `curso.json`, `curso.html`, `landing.html`, aulas de outro módulo, nem faça commit/push. O orquestrador monta tudo.

## Como auditar sozinho (sem conflitar com os outros)

```bash
D=/tmp/claude-1000/-home-nmaldaner-projetos-wifi/c91fb82a-1307-42a7-b54f-9dd798803f45/scratchpad/mN   # seu N
rm -rf $D && mkdir -p $D && cp -r ~/projetos/dev-ia-validacao/{aulas,assets,curso.json,landing.html} $D/
# no curso.json da CÓPIA: modulos = [{"titulo":"Módulo N · …","aulas":[suas 5 aulas]}] e apague os aula-*.html que não são seus
S=~/.claude/skills/formato-curso-v6/scripts; python3 $S/montar-curso.py $D && node $S/auditar-curso.cjs $D/curso.html && node $S/testar-motor.cjs $D/curso.html
```
Meta: toda aula 10/10 (mínimo 9, sem falha em 7, 8, 10). O motor exige uma `.tela` com 2 `.tela-caso` na PRIMEIRA aula da cópia.

Depois, faça você mesmo a leitura como as duas personas (Marcos, 34, só Claude Code, pouco Git, celular; Regina, 57,
Windows, planilha + chat de IA + Codex pelo app, nunca abriu terminal) e corrija todo "travei". Reaudite.

## Regras aprendidas no M1 (obrigatórias)

- Kicker `Módulo N · Aula k de 5`; rodapé `Aula N · Dev com IA v6.2 · INEMA.CLUB`; nav anterior/próxima; a última aula do
  módulo aponta "voltar à trilha →" (`#trilha`); a aula 30 idem.
- Termos: em CADA aula, a 1ª ocorrência de modelo, critério de aceite, revisão cruzada, briefing, handoff, token, terminal
  (e qualquer termo da lista-sentinela ou de `termos`: diff, briefing, handoff, prime, sandbox, token) leva `.gterm` com
  EXATAMENTE a mesma `data-gl`/`data-def` usada nas aulas 1–5 (copie de lá). Termo novo: defina uma vez, em ≤2 frases, e
  use a mesma definição em todas as aulas do seu módulo. Evite jargão que não precise ensinar.
- Um nome por conceito: **tentativa** (não "rodada") para o assistente recomeçar; **rodada de revisão** só para o debate
  plano ↔ crítica (M2: máximo 2). "Fora" = o que não pode mudar.
- Quem só tem um assistente: sempre dizer que uma conversa nova dele serve de segundo olhar.
- Caminho principal sem terminal quando der; terminal (perfil técnico) com o comando exato, o que conferir, e alternativa
  para quem usa o app. Windows: Explorador em modo **Detalhes**. Botão de parar no app/extensão; Esc no terminal.
- **Só afirme comportamento de comando que você conferiu** (rode `--help` localmente: `codex exec --help`, `claude --help`,
  `git …`). Comandos de referência já conferidos: `codex exec --sandbox read-only -c model_reasoning_effort=medium --output-last-message review.md '<pedido>'`;
  `claude -p --model opus --effort medium '<pedido>' > review-claude.md`; `timeout 30m …` (124 = tempo acabou).
- Tela "boa" da IA nunca inventa fato ausente do pedido. Rotas (Claude planeja / Codex critica) = rota inicial, não ranking.
  OpenRouter, modelos abertos e `/advisor` = orientação a conferir no ambiente. "IA vai encarecer" = hipótese.
- Nunca "à direita/esquerda", nem "os dois lados/cartões" como referência espacial; refira-se pelo rótulo.
- Alterne Rafael (site de clínica, cliente) e Carla (relatório/planilhas de entrega) nos exemplos; o piloto do aluno é o
  fio: briefing (M1) → plan-v1/plan-v2 (M2) → mudança revisada (M3) → aceite (M4) → handoff (M5) → relatório de custo (M6).
- Cada aula se sustenta sozinha: diga onde está o que veio antes ("o briefing.md da aula 5, na pasta do piloto") e dê saída
  para quem pulou.
- Cards: 3–4, terminam em "?", decisão/diagnóstico/aplicação, sem repetir ≥6 palavras da cola.
- Material complementar opcional, com fonte (páginas do Eventos: `~/projetos/inemaeventos/codex-claude/index.html`,
  `claude-codex/index.html`; kit Use Both `~/projetos/use-both-claude-codex/GUIDE.md`, `PROMPTS.md`; kit
  `~/projetos/agente-claude-codex`; síntese `docs/sintese-executiva-2026-09-27.md`).

Ao terminar, responda: notas do auditor por aula, motor, os "travei" que achou e corrigiu, imagens refeitas, e qualquer
afirmação técnica que você NÃO conseguiu conferir.
