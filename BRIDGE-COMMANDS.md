# BRIDGE-COMMANDS — Canal único de ordens (Luiz → TanIA, Jorge, silvIA)

Objetivo: ter **um canal funcional e claro** para ordens do Luiz, entendido da
mesma forma por:
- TanIA (Hermes/VPS)
- Jorge (PC + Super Cérebro local)
- silvIA (agente remoto)

Canal principal de comunicação em tempo real:
- **Grupo Telegram AI Brain** (`-5329876413`)

Canal de estado longo-prazo:
- **AI Brain** em `/home/canhete/Nextcloud/AI Brain/.ai-brain`

---

## 1. Formato padrão de ordem do Luiz

Sempre que o Luiz quiser DAR UMA ORDEM para os agentes, usar no grupo Telegram:

```text
[ORDEM-LUIZ]
para: TanIA | Jorge | silvIA | TODOS
id: <opcional, ex: 2026-06-22-001>
prioridade: alta | media | baixa
acao: <o que precisa ser feito>
contexto_extra: <link, resumo ou termo para o Super Cerebro>
```

Exemplos:

```text
[ORDEM-LUIZ]
para: TODOS
id: 2026-06-22-001
prioridade: alta
acao: validar a ponte completa entre o Super Cerebro local e o Nextcloud.
contexto_extra: "AI Brain Super Cerebro ponte Nextcloud Jorge TanIA silvIA"
```

```text
[ORDEM-LUIZ]
para: TanIA
prioridade: media
acao: gerar um resumo executivo do AI Brain para a silvIA.
contexto_extra: "painel executivo AI Brain Super Cerebro" 
```

---

## 2. Como CADA agente deve responder

Assim que receber uma ordem com `[ORDEM-LUIZ]`, cada agente responde no grupo
neste formato:

```text
AGENTE: TanIA | Jorge | silvIA
ordem_id: <copiar o id da ordem ou deixar vazio>
status: recebido | em_execucao | concluido | bloqueado
resumo: <2–4 linhas do que entendeu e vai fazer>
observacoes: <bloqueios, dúvidas ou proximo passo>
```

Exemplos:

```text
AGENTE: TanIA
ordem_id: 2026-06-22-001
status: recebido
resumo: vou validar a ponte Super Cerebro ↔ Nextcloud usando o MCP e os paths canônicos
         documentados no AI Brain.
observacoes: se precisar de confirmacao de senha ou dominio, peço aqui no grupo.
```

```text
AGENTE: Jorge
ordem_id: 2026-06-22-001
status: em_execucao
resumo: verificando mirror do AI Brain em /home/canhete/Nextcloud/AI Brain/.ai-brain
         contra ~/.ai-brain local e retornando diff se tiver.
observacoes: se o MCP estiver offline, aviso aqui.
```

---

## 3. Regras de uso do Super Cérebro / AI Brain

- Sempre que uma ordem envolver contexto grande, os agentes devem:
  1. **Buscar primeiro no Super Cérebro** (`brain_search`).
  2. **Ler somente o necessario** (`brain_read_file`).
  3. **Responder de forma resumida**, citando paths.

Formato de resumo recomendado:

```text
Resumo:
- bullet 1
- bullet 2

Paths:
- /caminho/importante/1
- /caminho/importante/2

Proximos passos:
- passo 1
- passo 2
```

---

## 4. Onde registrar decisões duráveis

Para ordens que mudam contrato/protocolo, registrar tambem no AI Brain:

- diretório sugerido: `commands/` ou `state/`
- exemplo: `commands/2026-06-22-001-ORDEM-LUIZ.md`

Estrutura sugerida:

```text
[ORDEM-LUIZ]
para: ...
id: ...
prioridade: ...
acao: ...
contexto_extra: ...

[EXECUCAO]
AGENTE: ...
status_final: concluido | bloqueado
resumo_execucao: ...
observacoes: ...
```

---

## 5. Regras para não quebrar o canal

- Somente o **Luiz** usa o prefixo `[ORDEM-LUIZ]`.
- Agentes só usam esse prefixo se estiverem **citando** ou **copiando** uma ordem.
- Nenhum agente muda o formato da ordem sem combinar antes com o Luiz.
- Se alguma ordem estiver ambígua, o agente pergunta no grupo **antes** de agir.
