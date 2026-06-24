# Protocolo do Super Cérebro Local para agentes de IA

Este computador possui um índice local compartilhado de contexto chamado **Super Cérebro Local**.
Todo agente de IA que roda nesta máquina deve consultar esse cérebro antes de pedir contexto repetido ao usuário, antes de assumir estado do ambiente e antes de trabalhar em projetos locais.

## Raiz

- Raiz do cérebro: `/home/canhete/.ai-brain`
- View executiva: `/home/canhete/.ai-brain/SUPER_CEREBRO.md`
- Banco FTS5: `/home/canhete/.ai-brain/context_index.sqlite`
- Manifesto JSONL: `/home/canhete/.ai-brain/manifest.jsonl`
- Índice humano: `/home/canhete/.ai-brain/INDEX.md`
- Script de busca: `/home/canhete/.ai-brain/scripts/search_ai_brain.py`
- Script de reindexação: `/home/canhete/.ai-brain/scripts/reindex_ai_brain.py`
- Script de view: `/home/canhete/.ai-brain/scripts/generate_super_brain_view.py`
- Cópia no Obsidian: `/home/canhete/Área de trabalho/Obsidian/40 - AI Brain/🧠 Super Cérebro Local.md`

## Regra principal

Antes de responder sobre qualquer um destes assuntos, consulte o Super Cérebro:

- Hermes Agent, Claude Code, Codex, Gemini, Cursor, Antigravity, Copilot ou outros agentes.
- Projetos locais, workspaces, repositórios, dashboards, Obsidian, organização do PC.
- Configurações, comandos, skills, AGENTS.md, CLAUDE.md, sessões e contextos anteriores.
- Qualquer pedido do usuário que soe como “você já sabe disso?”, “onde está?”, “organiza meu contexto”, “usa o cérebro”.

## Como buscar

Use um destes comandos:

```bash
python ~/.ai-brain/scripts/search_ai_brain.py 'termos de busca' 20
```

Exemplos:

```bash
python ~/.ai-brain/scripts/search_ai_brain.py 'hermes OR claude OR codex' 30
python ~/.ai-brain/scripts/search_ai_brain.py 'obsidian OR graph OR super cerebro' 30
python ~/.ai-brain/scripts/search_ai_brain.py 'AGENTS OR CLAUDE OR SKILL' 50
```

Consulta direta SQLite:

```bash
sqlite3 ~/.ai-brain/context_index.sqlite "select category,title,path from fts where fts match 'hermes OR obsidian' limit 30;"
```

## Como atualizar

Quando arquivos de contexto forem criados/movidos/alterados:

```bash
python ~/.ai-brain/scripts/reindex_ai_brain.py
python ~/.ai-brain/scripts/generate_super_brain_view.py
```

## Política de segurança

- O cérebro é um índice local, não uma cópia canônica dos projetos.
- Arquivos com nomes de segredo, token, auth, session, cookie e credential devem ficar apenas como metadados/redigidos.
- Não exponha chaves, tokens ou credenciais ao usuário nem a ferramentas remotas.
- Edite os arquivos originais quando necessário; depois reindexe.

## Como usar no raciocínio

1. Identifique palavras-chave do pedido do usuário.
2. Busque no Super Cérebro.
3. Abra apenas os arquivos relevantes encontrados.
4. Use o contexto encontrado para agir.
5. Se descobrir uma convenção durável, registre no mecanismo de memória/skill apropriado do agente.
6. Se gerar novo contexto importante, salve no lugar correto e rode a atualização do cérebro.

## Frase curta para lembrar

“Antes de perguntar, procure no `/home/canhete/.ai-brain`.”
