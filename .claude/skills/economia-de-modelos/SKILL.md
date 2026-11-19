---
name: economia-de-modelos
description: Use em toda tarefa da Eletrohome. Delega trabalho simples a modelos mais baratos (Haiku/Sonnet) via subagentes e guarda o Opus para análise e decisões.
---

# Economia de modelos (roteamento por complexidade)

Objetivo: gastar menos tokens do modelo mais caro. O modelo principal coordena; o trabalho braçal vai para subagentes com modelo mais barato. Esta skill autoriza o uso de subagentes para isso.

## Como classificar cada etapa

**Haiku** — tarefas mecânicas, sem julgamento:
- ler/resumir arquivos, CSV e planilhas; extrair colunas
- converter formatos, limpar dados
- buscar produto, código, EAN ou preço em listas
- reescrever textos curtos (títulos, legendas, descrições)
- conferências simples ("tem estoque?", "está na lista?")

**Sonnet** — tarefas médias:
- planilhas com fórmulas, relatórios, tabelas de comparação
- escrever ou ajustar scripts/código (ex.: modelo de vídeo Remotion)
- roteiros de vídeo, anúncios e textos para Mercado Livre/TikTok
- análises de estoque, giro e promoções com regras já definidas

**Opus (modelo principal)** — só quando precisa de julgamento:
- estratégia (preço, qual produto anunciar, onde investir)
- interpretar resultados ambíguos
- revisar o que os subagentes entregaram
- ações irreversíveis (publicar, enviar, alterar preço/estoque), sempre com confirmação do usuário

## Regras
1. Divida o pedido em etapas e classifique cada uma.
2. Dê ao subagente um prompt completo: arquivos, formato de saída, idioma (português do Brasil).
3. Rode subagentes independentes em paralelo.
4. Não use subagente para o que se resolve em 1–2 chamadas de ferramenta.
5. Uso do computador (Sysemp, navegador) fica com o modelo principal.
6. Responda sempre em português e diga em uma linha o que foi feito por modelo mais barato.
