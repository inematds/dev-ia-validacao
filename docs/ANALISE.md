# Análise — como montar o projeto (28/09/2026)

## 1. O que as duas fontes dizem

| Arquivo | Natureza | Uso no curso |
|---|---|---|
| `docs/sintese-executiva-2026-09-27.md` | síntese com fluxo em 5 passos, ressalvas e fontes (áreas Codex + Claude e Claude → Codex do Eventos) | **base das afirmações** |
| `docs/mensagem-nei-2026-09-27.md` | mensagem curta, tom motivacional, fluxo em 4 passos | tom, ênfase em orçamento e no "saber validar" |

As duas convergem num ciclo: **definir tarefa → planejar e criticar → construir e revisar → comprovar → registrar a
continuidade**, com escolha de modelo e esforço por etapa. A síntese é mais rigorosa: marca como "orientação
adicional, não verificada" o OpenRouter, os modelos abertos e o `/advisor`, e trata "a IA vai ficar mais cara"
como hipótese. O curso adota essa régua (ver "Regras de conteúdo" em `context/curriculo.md`).

As fontes somam ~6 KB. O conteúdo das aulas vem também das páginas-fonte citadas, que já estão no disco:
`~/projetos/inemaeventos/codex-claude/index.html` (seis níveis do Use Both, tabela de rotas, comandos
`codex exec --sandbox read-only` / `claude -p`, "/goal caro", imagem com o Codex) e
`~/projetos/inemaeventos/claude-codex/index.html` (núcleo portátil, handoff/prime, audit antes de implement).

## 2. Posicionamento (não repetir o que já existe)

| Já existe | Foco | Este curso |
|---|---|---|
| `curso-claude-codex` (v2, 3 trilhas) + kit `agente-claude-codex` | migrar ou ficar agnóstico | só aponta (aula 23) |
| `use-both-claude-codex` (guia) | os 6 níveis, prompts | vira prática guiada, aula por aula |
| `claudex` / iClaudeX | debate automático de plano | citado na aula 9 como "plano grande" |
| `codexbasico`, `mastercodex` | a ferramenta Codex | pré-requisito opcional |

Lacuna que o curso cobre: **o método de validação e orçamento, ponta a ponta, num piloto do próprio aluno**, no
formato v6 (aulas de 15 min, visual real, prática que termina em algo conferível).

## 3. Formato escolhido: `formato-curso-v6` no molde OSWork v6.2

- Skill: `~/.claude/skills/formato-curso-v6` (6.3.3). Referência viva: `~/projetos/oswork-v62`.
- `curso.json` com `"perfil": "tecnico"` (há terminal: `codex exec`, `claude -p`, `git diff`), `"termos"` e
  `"modulos"` (landing mostra só módulos, fechados). Glossário gerado.
- 6 módulos × 5 aulas (proposta em `context/curriculo.md`). Cada aula: cena → promessa → 3–4 steps com visual real
  (`.tela` com pedido/resposta reais, `.lado` antes/depois, `.janela` de terminal) → 1 prática → fecho → cards.
- Versão no nome: **"Dev com IA v6.2"** no `<title>`, barra, kicker, landing e rodapé.

Estrutura do repo (já criada):

```
dev-ia-validacao/
  docs/            fontes + esta análise + plano de vídeos
  context/         curriculo.md (+ plano-mN.md / leitor-mN.md por módulo, como no OSWork)
  aulas/           aula-N.html (uma section por arquivo)
  assets/          aula.css e curso.js copiados da skill, sem editar; img/aula-N.webp
  curso.json       esqueleto com os 6 módulos
  curso.html       MONTADO (não editar)   landing.html (do template)
```

## 4. Pipeline (ordem fixa)

```bash
S=~/.claude/skills/formato-curso-v6/scripts
# por aula: escrever aulas/aula-N.html a partir de assets/aula-template.html da skill
python3 $S/gerar-cena.py assets/img/aula-N.webp "<cena>" --gerador flux --seed N   # SEMPRE flux local
python3 $S/montar-curso.py .
node $S/auditar-curso.cjs curso.html        # toda aula >= 9/10, sem falha em 7, 8 e 10
node $S/testar-motor.cjs curso.html         # todos OK, 0 erro JS
# leitor simulado (references/TESTE-HUMANO.md §1) por módulo -> context/leitor-mN.md
```

Ritmo sugerido: um módulo por vez, como no OSWork (M1 completo e publicado → M2…). Publicar = commit + push;
GitHub Pages na raiz; card no portal via skill `atualiza-portal` só quando o Nei pedir.

## 5. Etapas que dependem de autorização (regra dura de API, 26/09/2026)

| Etapa | O que chamaria | Padrão sem autorização |
|---|---|---|
| Cenas das aulas (`gerar-cena.py`) | padrão da skill = Codex image_gen (crédito) | `--gerador flux --seed N` (inemaimg local) |
| Tradução EN/ES (`traduzir-curso.py`) | OpenRouter (GPT-5.4 nano) | curso só em PT até autorizar |
| Capa (`capa-inema`) | modo auto pode chamar Codex | `--raw-in trilha.png` (arte já gerada no flux) |
| Vídeos explicavideos v1 | HeyGen Studio (crédito da assinatura) + API HeyGen de consulta | não gerar; pedir ok no momento |
| Transcrição dos vídeos | Groq (API) | `"transcriber": "whisper-local"` |
| `atualiza-portal` | `npm run gen:data` → Groq nos feeds | só `node tools/gen-courses-data.mjs` |

## 6. Riscos

- **Fonte fina:** 30 aulas a partir de ~6 KB + 2 páginas pode virar enchimento. Mitigação: cada aula tem uma prática
  sobre o piloto do aluno; se um tópico não sustentar 15 min, fundir (o currículo permite cair para 24 aulas).
- **Datas e nomes de modelo:** aparecem sempre com "em setembro de 2026" e sem ranking.
- **Terminal para iniciante:** perfil técnico exige `.gterm` em toda aula em que o termo aparece; o auditor cobra.
- **Idiomas:** versão PT primeiro; EN/ES só com autorização da API de tradução.
