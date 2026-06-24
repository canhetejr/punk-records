# AI Brain local

Este diretório é um índice organizado dos contextos de IA encontrados neste PC.
Ele serve como ponto de entrada rápido para Hermes, Claude Code e as notas do cérebro local.

Privacidade:
- Não move nem altera contextos originais.
- Arquivos com nomes de segredo entram só como metadados.
- Textos indexados passam por redator simples antes de irem para o SQLite/manifesto.

Arquivos principais:
- `/root/.ai-brain/INDEX.md`: mapa humano rápido.
- `/root/.ai-brain/manifest.json` e `/root/.ai-brain/manifest.jsonl`: manifestos com metadados.
- `/root/.ai-brain/context_index.sqlite`: SQLite com FTS5 para busca textual local.
- `/root/.ai-brain/scripts/search_ai_brain.py`: busca simples.
- `/root/.ai-brain/scripts/rag_query.py`: pacote de contexto RAG com snippets e fontes.
- `/root/.ai-brain/scripts/ai_brain_mcp_server.py`: servidor MCP local via stdio.

Contagem por categoria:
- ai-brain-core: 10
- claude: 1
- hermes: 518

Como buscar:
```bash
python ~/.ai-brain/scripts/search_ai_brain.py 'hermes OR claude' 20
python ~/.ai-brain/scripts/rag_query.py 'RAG MCP Super Cérebro' --limit 8
```

Como atualizar:
```bash
python ~/.ai-brain/scripts/reindex_ai_brain.py
```
