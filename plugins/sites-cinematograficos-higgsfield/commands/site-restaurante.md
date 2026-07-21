---
description: Gera o prompt cinematografico Higgsfield para um restaurante.
---

Gere o prompt do Higgsfield para um RESTAURANTE.

Carregue a skill `gerador-prompt-cinematografico` e use o mapa de jornada "Restaurante" da
referencia `jornadas-por-nicho.md`. FORMATO padrao: CLIPES (4-5 clipes encadeados).

Pergunte apenas o essencial que faltar: nome do restaurante, nome do chef (se aparecer no
reveal), tipo de cozinha e cor de destaque.

Confirme sempre a FONTE do conteudo antes de gerar:
- `PASTA` — os arquivos do site ja estao na pasta do projeto; e
- `URL` — a pasta esta vazia e o conteudo vem de um site publicado (peca a URL; sem ela nao gere).

Se a FONTE for `URL`, o prompt NAO pode citar "site existente nesta pasta", "analise o projeto"
nem "backup" — e a URL precisa aparecer no prompt.

Entregue SOMENTE o prompt final, num unico bloco de codigo copiavel, salvo em outputs. Sem
roteiro, sem explicacao longa.
