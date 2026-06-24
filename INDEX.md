# Índice mestre do AI Brain

## Visão geral

- hermes: 518 itens -> contexts/hermes.md
- ai-brain-core: 10 itens -> contexts/ai-brain-core.md
- claude: 1 itens -> contexts/claude.md

## Rotas principais

- Hermes config/sessões/skills: `/root/.hermes` (existe)
- Claude Code config/plugins: `/root/.claude` (existe)
- OpenAI Codex config/sessões: `/root/.codex` (não encontrado)
- GitHub CLI: `/root/.config/gh` (não encontrado)
- Antigravity IDE: `/root/.antigravity-ide` (não encontrado)
- Workspace Antigravity: `/root/antigravity` (não encontrado)
- Vault Obsidian: `/root/Área de trabalho/Obsidian` (não encontrado)

## Consulta rápida

```bash
python ~/.ai-brain/scripts/search_ai_brain.py 'CLAUDE OR AGENTS OR SKILL' 30
python ~/.ai-brain/scripts/rag_query.py 'biblioteca enade instruções' --limit 6
```

## MCP local

Servidor stdio: `python ~/.ai-brain/scripts/ai_brain_mcp_server.py`

## Observação

Este é um índice, não uma cópia canônica. Edite os arquivos originais; depois rode o reindexador.
