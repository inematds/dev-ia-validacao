# Módulo 6 · Modelos, esforço e orçamento — plano

Objetivo: escolher modelo e esforço por etapa e medir custo × resultado. Laboratório: relatório do piloto (aula 30).

| Aula | Título | Tipo | Prática | Cena (flux, seed) | Visuais |
|---|---|---|---|---|---|
| 26 | Escolha pela tarefa, não pelo ranking | fundamento | análise, 10 min | Rafael compara duas respostas impressas com a ficha de critérios (182) | tela 2 casos (pergunta geral × da tarefa), janela comparação justa, lado bonita × passou na régua, lado o que anotar × quando refazer |
| 27 | Esforço alto onde pesa, baixo onde é rotina | fundamento | análise, 8 min | Carla cola adesivos de 3 cores numa folha de 5 etapas (183) | lado modelo × esforço, janela esforço por passo, lado esforço máximo sem planilha × médio com planilha, terminal `-c model_reasoning_effort` / `--effort` |
| 28 | Custo sem resultado não diz nada | ferramenta | tarefa, 10 min | Rafael anota numa caderneta com cronômetro (184) | janela colunas da planilha, lado só espera × pedido à conferência, tela uso antes/depois, lado custo × resultado |
| 29 | Preço e limite mudam: confira na sua conta | fundamento | tarefa, 8 min | Carla, sozinha, confere as configurações da conta ao lado das faturas (211; seeds 185 e 205 descartadas: pessoa duplicada, texto legível) | lado assinatura × por uso, janela conta-ia.md, lado trocar pelo preço × conferir antes, lado previsão × medida |
| 30 | Ampliar, ajustar ou parar: a decisão do piloto | ferramenta | tarefa, 12 min | Rafael e Carla diante do relatório de uma página (186) | janela relatorio-piloto.md, janela 3 saídas, lado sem decisão × decisão escrita, janela próximos caminhos |

Termos novos: `esforco-de-raciocinio`, `api` (definição única no módulo). Fio do piloto: `escolhas.md` (26), tabela de esforço (27),
`piloto-custos` (28), `conta-ia.md` (29), `relatorio-piloto.md` (30).

Comandos conferidos em 28/09/2026 (`--help` local): `codex exec -c model_reasoning_effort=<low|medium|high>`;
`claude -p --effort <low|medium|high|xhigh|max>`. Não conferido: caminho exato da página de uso em cada conta (texto genérico:
configurações da conta › Uso/Usage) e seletor de esforço nos apps (texto: "quando a ferramenta oferece").
