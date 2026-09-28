# CLAUDE.md — dev-ia-validacao

- Curso no `formato-curso-v6` (perfil técnico, módulos), molde `~/projetos/oswork-v62`. Leia `docs/ANALISE.md` e `context/curriculo.md` antes de escrever aula.
- Commits: autor `inematds <inematds@gmail.com>`. Publicar = commit + push (GitHub Pages na raiz).
- Cenas: sempre `gerar-cena.py ... --gerador flux --seed N`. Tradução EN/ES, HeyGen, Groq e Codex image_gen só com autorização explícita (tabela em `docs/ANALISE.md` §5).
- Afirmações seguem a síntese: concordância entre modelos não é prova; rota Claude→Codex não é ranking; OpenRouter e `/advisor` são "a conferir".
- Versão `vX.XX.YY` (semver da casa) no `VERSION`, no `curso.json` e nos rótulos do curso.

## Self-learning

When I correct you, or you catch yourself making a mistake: before continuing, add the lesson as a one-line rule under ## Lessons, so it never happens again.

## Lessons
- Comportamento de comando/atalho (código de saída, tecla, menu) só entra na aula depois de conferido; o leitor simulado pegou "timeout: zero = terminou antes" errado e "modo lista" no lugar de Detalhes no Windows. (28/09/2026)
- flux2-klein não desenha dois objetos idênticos (relógios iguais falharam em 3 seeds): trocar a metáfora da cena, não insistir no seed. (28/09/2026)
