# BRIDGE-PROTOCOL — AI Brain

## Objetivo
Conectar agentes ao mesmo cérebro Obsidian/Nextcloud sem conflito e sem duplicar fonte de verdade.

## Canais
1. **Grupo Telegram**: coordenação rápida entre humanos/agentes.
2. **Nextcloud/Obsidian**: fonte persistente de arquivos.
3. **Arquivos de ponte**: handshake, resposta, status e decisões.

## Formato obrigatório de resposta de agente
```text
status:
caminho_local:
cérebro_completo:
diferenças:
sugestão_de_conexão:
```

## Regras
- Não inventar status de sync.
- Não criar arquivo fora de `.ai-brain/` ou `Agentes/` sem necessidade.
- Antes de editar conteúdo central, registrar intenção em `.ai-brain/outbox/` ou no grupo.
- Se houver conflito, citar caminho e tipo de conflito.
- Preferir mensagens curtas e verificáveis.

## Modos possíveis
- **espelho**: todos leem/escrevem o mesmo vault sincronizado.
- **master/replica**: um lado é fonte principal; demais replicam.
- **ponte por arquivo**: agentes trocam pedidos/respostas por Markdown.

## Modo inicial recomendado
Começar com **ponte por arquivo + leitura do grupo**, até todos confirmarem caminho local e integridade.
