# Plano de vídeos — explicavideos v2 (animação explicativa)

Motor: `~/projetos/explicavideos` (README 2.2.3, `engine/v2/AUTHORING.md`). Referência de produção:
`~/projetos/output/oswork-v62/m*-v2` e o player `~/projetos/oswork-v62/videos/`.

## O que se entrega

- **1 vídeo por módulo** (6 vídeos), ~15–17 min cada, com capítulos por aula, legenda (SRT/VTT) e player em
  `videos/index.html` do curso. MP4/SRT em GitHub Release (`video-v2.0.0`), como no OSWork v6.2.
- PT primeiro. EN/ES só depois do curso traduzido (tradução é API → exige autorização).

## Cadeia de dependências (nada pula etapa)

1. **Aulas do módulo prontas** (auditor ≥ 9/10) — o vídeo narra o curso; sem aula não há roteiro.
2. **Roteiro de cenas** `~/projetos/output/dev-ia-validacao/roteiro/mN-pt.json` (title, chapter, speech, labels,
   source, kind, takeaway), revisado pelo Nei antes do `start`.
3. **v1 = avatar do Nei no HeyGen Studio** pela assinatura (template TEMPLATE-AVATAR16, voz INEMATIME, Avatar III),
   blocos de até 4.400 caracteres. **Consome crédito HeyGen → só com ok explícito no momento, nunca em background.**
4. **Transcrição com tempo por palavra:** config com `"transcriber": "whisper-local"` (sem Groq) e
   `"balanced_blocks": true`.
5. **Roteiro visual v2** `visual-v2/pt-bNN.json` por bloco: shots dos 21 primitivos (`flow`, `compare`,
   `lanes`, `statement`, `terminal`…), toda deixa é trecho literal da fala, nenhuma moldura vazia > 3 s,
   nada parado > 10 s. Depois de revisar, criar `visual-v2/READY`.
6. **Build e render local:** `setup_output.py` → `build_block.py N --strict` → `run_lane.sh` (HyperFrames 25 fps)
   → `assemble_languages.py` → `publish_finished.py`.

Configs a criar em `~/projetos/explicavideos/examples/` (copiando os do OSWork v6.2):

```json
{"id":"devia62-m1","title":"Dev com IA v6.2 · Módulo 1","source_repo":"/home/nmaldaner/projetos/dev-ia-validacao",
 "output":"/home/nmaldaner/projetos/output/dev-ia-validacao/m1","languages":["pt"],
 "scene_files":{"pt":"/home/nmaldaner/projetos/output/dev-ia-validacao/roteiro/m1-pt.json"},
 "github_repo":"inematds/dev-ia-validacao","release_tag":"video-v1.0.0","template":"TEMPLATE-AVATAR16",
 "profile":"/home/nmaldaner/.cache/inemaccbot/perfil-heygen","max_chars":4400,
 "transcriber":"whisper-local","balanced_blocks":true}
```
e o `devia62-m1-v2.json` com `"engine":"v2"`, `"v1_output"` apontando para o de cima e `"release_tag":"video-v2.0.0"`.

## Mapa visual por módulo (primitivos que explicam cada ideia)

| Módulo | Ideias-chave | Primitivos |
|---|---|---|
| M1 Validar | parece certo × conferi; concordância ≠ prova; ciclo em 5 passos | `compare`, `statement` (mito riscado), `steps` |
| M2 Planejar e criticar | plano em arquivo; crítica com evidência; 2 rodadas | `flow` (plan-v1 → review.md → plan-v2), terminal `codex exec`, `podium` desmontado ("qual é o melhor?") |
| M3 Construir e revisar | branch, *diff*, revisão cruzada, imagem conferida | terminal `git diff`, `lanes` (constrói × revisa), `compare` |
| M4 Comprovar | critério → teste; sistema real; menor correção; meta com parada | `radar` de critérios, `bullets`, `statement` ("pare em 2h" riscado → limite real) |
| M5 Continuidade | handoff, prime, núcleo portátil | árvore de pastas, `flow` sessão A → handoff → sessão B |
| M6 Orçamento | modelo por tarefa; esforço por etapa; custo × resultado | `orbs` (modelos), `lanes` (esforço alto/médio/baixo), `bullets` com números do piloto |

## Custo e alternativa sem crédito

- Único custo externo: **HeyGen (avatar v1)**, ~16 min de avatar por módulo × 6 módulos. Conferir saldo antes.
- **Alternativa local, sem avatar e sem crédito:** skill `video-explicativo` (HyperFrames + voz inemavox local),
  um vídeo curto por módulo (~2 min, 16:9 + 9:16) — serve de trailer/divulgação do curso, não substitui a vídeo-aula.
