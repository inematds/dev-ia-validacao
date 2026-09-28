# Leitor simulado — Módulo 1 (28/09/2026)

Personas: **Marcos**, 34, desenvolvedor de sites, usa só Claude Code, pouco Git, no celular; **Regina**, 57, analista de
operações, Windows, planilha + chat de IA + Codex, nunca abriu terminal.

## Rodada 1 (aulas 1–5)

| Aula | Marcos | Regina | Principais "travei" → correção |
|---|---|---|---|
| 1 | 7 | 8 | "modelo" sem definição → `.gterm` modelo em todas as aulas; gabarito ignorava o texto não lido → corrigido; card repetia a cola → trocado |
| 2 | 6 | 8 | só tem um assistente → "abra uma conversa nova" no step 1; conta do prazo invertida → "prazo de transporte, dois dias maior"; evidência da IA não provava a falha → aponta a seção do plano; gesto de anexar → clipe do chat / citar arquivo |
| 3 | 8 | 9 | critérios de celular não passavam no sim/não → "não rola para os lados"; Carla sem tela → 2º caso na tela; "modelo do relatório" → "formato" |
| 4 | 5 | 5 | "modo de meta", relato 3–5× e kit sem contexto → foram para o complementar; "zero = terminou antes" errado → corrigido; tudo dependia de Linux/terminal → alarme + botão de parar + página de uso no caminho principal, `timeout` num `details.mais`; tentativa × rodada → um nome só: tentativa |
| 5 | 7 | 7 | `.md` e `#` sem explicação; como entregar o arquivo (`@`); celular × arquivo contraditório; gesto de criar o arquivo |

## Rodada 2 (aulas 4 e 5, Regina)

| Aula | Nota | Correção |
|---|---|---|
| 4 | 6 | Windows: coluna de data aparece em **Detalhes**, não em Lista; limite no pedido (conferível) separado de trava (para na hora); página de uso = medida, teto = trava; alarme só com você por perto; botão de parar no app/extensão, Esc no terminal; cards 1, 3 e 4 reescritos |
| 5 | 7,5 | passo a passo de Windows (com Windows 10 e "Abrir com") e Mac tirados do bloco opcional e postos antes dos passos; `.txt` como saída; piloto = 1–2 h do seu trabalho, alarme por vez que a IA trabalha |

Pendente de confirmação humana: se o `@` para citar arquivo aparece igual no app/extensão do Codex; caminho exato da página de uso em cada conta (o texto ficou genérico: configurações › Uso).

## Módulos 2–6 (28/09/2026)

Escritos por um agente por módulo (com leitura própria), depois um leitor simulado independente por módulo
(Marcos + Regina) e um corretor por módulo. Notas da leitura independente, antes das correções: M2 5–8, M3 4–8,
M4 6–8, M5 4–7, M6 5–7. Erros técnicos pegos e corrigidos:
- M3: commit antes do diff deixava `mudanca.diff` vazio → fluxo `git status` → `git add -A` → `git diff --staged --output` → revisão → commit; `git diff` não mostra arquivo novo; `pattern` do telefone inválido com a flag `v` (aceitava letras); `.xlsx` sai como binário no diff.
- M2/M3/M5: `claude -p` sem trava → `--permission-mode plan`; `/claudex:plan --rounds 2` (padrão é 3); evidências da IA citando trechos que não estavam no plano mostrado.
- M4: caso da fórmula que não fechava (planilha apagada daria `#REF!`); `timeout` no Windows só pausa; limite × trava.
- M5: pedir handoff a um assistente sem limite (impossível); `/advisor` conferido no binário (existe no Claude Code, cobra à parte); `codex exec` fora de Git exige `--skip-git-repo-check`.
- M6: comparação de ferramentas tratada como de modelos; colunas da planilha inconsistentes; conta da empresa sem acesso à página de uso.
Depois das correções: auditor 30/30 em 10/10, motor 26/26.
