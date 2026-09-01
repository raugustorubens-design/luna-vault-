# LUNA Vault

Vault Obsidian da LUNA — **nunca é ponto de entrada de ação**, só onde o resultado das notas
que ela cria e organiza aparece. Rubens não digita comandos aqui; ele fala com a LUNA (chat,
futuramente voz), e é ela quem cria, edita, move e organiza as notas. Este repositório é
**público**.

Especificação completa: `Luna-context.md` → `GENESIS/pacotes/2026-08-22-obsidian-bridge.md`
(arquitetura e sincronização via Obsidian Git) e `GENESIS/pacotes/2026-08-23-vault-publico-e-anonimizacao.md`
(regra de anonimização — leia antes de publicar qualquer nota real aqui).

## Regra que nunca muda

Nenhuma nota com dado real (nome completo, empresa, local identificável) entra neste
repositório. Toda nota nasce na tabela `luna_nota_candidata` (Supabase, interna, uso do
Arquiteto), com o conteúdo completo. Publicar aqui é um ato **manual e seletivo**, disparado
pelo Arquiteto, que troca nome/empresa/local pela etiqueta fixa `RRRJR · Mogi Guaçu` antes de
qualquer commit — nunca automático, nunca por prazo, nunca "tudo que está pronto".

O comando de publicação (que lê `luna_nota_candidata`, aplica a etiqueta e chama
`vault.write_note`) ainda não foi construído — é o próximo passo real deste pacote, não a
estrutura de pastas abaixo.

## Estrutura

- `Inbox/` — notas novas, ainda não classificadas
- `Areas/` — espelha os organs/frentes da LUNA
- `Reference/` — conhecimento consolidado
- `Daily/` — notas diárias (se e quando fizer sentido)
- `_templates/` — templates de nota (frontmatter padrão)

## Frontmatter padrão

```yaml
---
created_by: luna
created_at: YYYY-MM-DD
source: chat | reporter | guardian
status: rascunho | revisado
tags: []
---
```

`status: rascunho` é o padrão em toda nota criada pela LUNA. Nenhuma nota vira memória
permanente automaticamente só por existir aqui — isso passa pelo Guardian, com revisão do
Arquiteto.
