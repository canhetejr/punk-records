# HEADROOM_LOCAL — Estratégia de contexto para TanIA

> **Goal:** Usar o Super Cérebro + AI Brain como fonte principal
> e aplicar estratégia tipo *Headroom* para compressão de contexto
> em todas as tarefas.

## 1. Fontes de verdade

1. **Super Cérebro Local (MCP)**
   - Servidor: `super_cerebro_local`
   - Ferramentas: `brain_search`, `brain_read_file`, `brain_stats`
   - Raiz do índice: `/root/obsidian-vault/AI Brain/ai-brain`

2. **Espelho compartilhado (Nextcloud)**
   - Caminho canônico entre agentes:
     - `/home/canhete/Nextcloud/AI Brain/.ai-brain`
   - Papel: fonte de verdade compartilhada entre máquinas/agentes.

3. **Workspace local operacional**
   - `/home/canhete/.ai-brain` (lado do Jorge)
   - `/root/obsidian-vault/AI Brain/ai-brain` (lado TanIA/VPS)

## 2. Regra geral de uso de contexto

Sempre que o contexto começar a crescer ou envolver múltiplos arquivos:

1. **Buscar primeiro no Super Cérebro**
   - Usar `brain_search(query, limit)` para encontrar trechos relevantes.
   - Citar paths reais dos arquivos quando responder.

2. **Carregar só o mínimo necessário**
   - Usar `brain_read_file(path, max_chars)` quando realmente precisar ler o arquivo.
   - Evitar carregar vault inteiro ou diretórios grandes sem necessidade.

3. **Comprimir antes de continuar (Headroom-style)**
   - Quando houver muitos trechos/arquivos:
     - agrupar por tema
     - resumir em bullets curtos
     - manter só:
       - decisões
       - números/paths críticos
       - contratos/protocolos
   - Jogar detalhes de volta pro cérebro (não para a conversa) sempre que possível.

## 3. Padrão de resposta resumida

Quando responder usando o Super Cérebro / AI Brain, preferir formato curto:

```text
[PERGUNTA]
- resumo de 2–4 bullet points
- paths citados do índice
- próximos passos bem concretos
```

Exemplo:

```text
Resumo:
- O Super Cérebro tem 1.415 itens e ~6,78M caracteres indexados.
- A ponte com Nextcloud está simétrica via /home/canhete/Nextcloud/AI Brain/.ai-brain.
- O MCP super_cerebro_local está ativo com brain_search/brain_read_file/brain_stats.

Paths relevantes:
- /root/obsidian-vault/AI Brain/ai-brain/SUPER_CEREBRO.md
- /root/obsidian-vault/AI Brain/ai-brain/AGENT_PROTOCOL.md

Próximos passos:
- Rodar brain_search com o termo do usuário.
- Se necessário, ler 1–2 arquivos via brain_read_file.
```

## 4. Quando reindexar / sincronizar

Reindexar/sincronizar o cérebro quando ocorrer qualquer um destes:

- grandes mudanças em estruturas de projetos
- criação/edição de arquivos de protocolo (AGENT_PROTOCOL, BRIDGE-PROTOCOL, SUPER_CEREBRO)
- movimentação de diretórios inteiros no Obsidian ou Nextcloud

Regra:
- editar primeiro no workspace local (`.ai-brain`)
- garantir que o espelho Nextcloud está atualizado
- só então confiar na busca como representando o estado atual.

## 5. Limites / o que *não* fazer

- Não despejar arquivos enormes crus na conversa se puder buscar/resumir.
- Não ignorar o Super Cérebro quando o tema claramente já está indexado (AI Brain, agentes, projetos recorrentes).
- Não tratar o Nextcloud como fonte parcial: ou está sincronizado (confirmado) ou usar ponte por arquivo.

---

**TanIA:** sempre que o usuário pedir algo grande/recorrente, seguir este arquivo como referência
para decidir *quanto* contexto carregar e *como* resumir antes de continuar.
