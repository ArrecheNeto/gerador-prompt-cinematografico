---
name: gerador-prompt-cinematografico
description: >-
  Gera prompts completos e prontos para colar no Claude que criam sites e landing pages
  cinematograficos com efeito de "rolagem 3D" usando o Higgsfield MCP. Use SEMPRE que o
  usuario pedir "prompt de site cinematografico", "site com Higgsfield", "prompt Higgsfield",
  "site com rolagem 3D", "landing cinematografica", "site scrollytelling", "site premiado com
  IA", ou pedir para transformar/criar um site premium com video e imagem gerados por IA para
  qualquer nicho (tatuagem, cafeteria, restaurante, imobiliaria, academia, barbearia, pet shop,
  clinica, etc.). Cobre dois modos: transformar um site existente ou criar do zero a partir de
  uma URL. A saida e SOMENTE o prompt do Higgsfield, pronto para colar.
---

# Gerador de prompt cinematografico (Higgsfield)

Transforma um pedido simples ("quero um site cinematografico para uma cafeteria") num prompt
longo, tecnico e testado, pronto para colar no Claude com o Higgsfield MCP conectado. O
diferencial nao e o texto do site — e a **engenharia visual**: gerar imagem/video no Higgsfield
e amarrar tudo numa jornada de rolagem consistente.

## O que esta skill entrega

**Somente o prompt final do Higgsfield**, num bloco de codigo copiavel (arquivo `.md` salvo em
outputs). Nao gera roteiro de video, nao gera o site aqui — so o prompt que o usuario vai colar.

## Passo 1 — Detectar FONTE e FORMATO (duas escolhas independentes)

**FONTE do conteudo** — de onde vem o texto real do site:

- `PASTA` — os arquivos do site ja estao na pasta do projeto. O prompt manda analisar o projeto,
  fazer backup e reunir tudo numa `index.html`.
- `URL` — a pasta esta vazia e o conteudo vem de um site publicado. O prompt manda ler a URL e
  criar uma landing nova e original.

**FORMATO visual** — como o video e gerado:

- `CLIPES` — 4 a 5 clipes encadeados (o ultimo quadro de um vira o `start_image` do proximo).
  Melhor para nichos de processo (tatuagem, restaurante, academia).
- `VIDEO_UNICO` — um unico video continuo estilo comercial da Apple + 6 a 8 fotos de apoio.
  Melhor para nichos de produto/ambiente (cafeteria, imobiliaria).

As duas escolhas sao **independentes**: FONTE=URL com FORMATO=CLIPES e uma combinacao valida e
comum. Nao amarre uma na outra.

**Regra critica:** se a FONTE for `URL`, o prompt gerado NAO pode conter "site existente nesta
pasta", "analise todo o projeto" nem "crie um backup" — nao ha arquivos. E a `{URL}` precisa
aparecer explicitamente no prompt.

Se a FONTE nao estiver clara, pergunte so isso. O FORMATO pode ser inferido do nicho (use o
padrao indicado em `jornadas-por-nicho.md`).

## Passo 2 — Coletar o minimo (pergunte so o que faltar)

- Nicho do negocio (ex: estudio de tatuagem, cafeteria especial).
- Nome do negocio.
- Pessoa que aparece no final (nome) OU produto que e o "heroi" (se nao houver pessoa).
- Cor de destaque da marca.
- URL do site de origem — **obrigatorio quando FONTE=URL**. Sem ela, nao gere o prompt: peca a
  URL antes.
- Confirmar a pasta de fotos de referencia da pessoa: `assets/referencias-.../` (para
  `identity reference`).

Nao faca interrogatorio: se der para inferir do contexto ou de um preset, use e siga.

## Passo 3 — Desenhar a JORNADA visual (o coracao)

Toda experiencia e uma jornada de 4 a 5 cenas que termina num "reveal". Mapeie o negocio assim:

1. **HERO** — macro cinematografico da ferramenta/simbolo do nicho num ambiente parcialmente
   escuro; a camera circula e avanca. **Nao** mostra a pessoa ainda.
2 a 4. **ETAPAS DE TRANSFORMACAO** — o "antes/depois" do nicho, mostrado como processo real
   (nada acontece por magica). Encadeie as cenas (o ultimo quadro de uma vira o start da proxima).
5. **REVEAL FINAL** — a pessoa (via `identity reference`) OU o produto pronto, no mesmo
   ambiente, agora finalizado. Quadro estavel para receber o CTA de WhatsApp em HTML.

Veja mapas de jornada prontos em `references/jornadas-por-nicho.md`. Se o nicho nao estiver la,
crie a jornada seguindo a mesma logica (ferramenta -> processo -> reveal).

## Passo 4 — Preencher o TEMPLATE

Use o template parametrizado em `references/template-prompt.md`. Ele e montado em 6 blocos:
escolha a variante do BLOCO 1 pela FONTE (pasta ou URL) e a do BLOCO 3 pelo FORMATO (clipes ou
video unico); os demais blocos sao fixos. Rode o checklist do fim do template antes de entregar.

Regras que NUNCA mudam (ja embutidas no template):

- Higgsfield MCP; preferir **Cinema Studio 3.0 em 4K**; clipes **16:9, 5-10s, sem audio**.
- Gerar **primeiro uma imagem hero**, depois anima-la e usa-la como referencia visual de todos
  os clipes (consistencia de cor, luz, materiais).
- **Encadear**: usar o ultimo quadro de cada clipe como `start_image` do proximo.
- Pessoa recorrente = `identity reference` (preservar rosto, cabelo, tom de pele, tipo fisico).
- Site: sequencia de quadros no **canvas** controlada pela rolagem; **GSAP + ScrollTrigger**
  para fixar/controlar, **Lenis** para smooth scroll sincronizado.
- Todo texto/CTA e **HTML real sobreposto** — nunca texto dentro do video. WhatsApp como
  conversao principal.
- **Responsivo** + fallback leve para mobile e `prefers-reduced-motion`.
- **Testar em localhost** num navegador real (scroll pra frente e pra tras, canvas, Lenis,
  ScrollTrigger, ancoras, WhatsApp) e corrigir saltos, quadros vazios e erros de console antes
  de concluir.
- Constraints negativos: sem maos deformadas, dedos extras, objetos flutuando, processos
  impossiveis, logotipos, marcas d'agua ou texto dentro das imagens/videos.

## Passo 5 — Entregar

Salve o prompt final como `prompt-higgsfield-{nicho}.md` na pasta de outputs, num unico bloco de
codigo copiavel, e apresente ao usuario. Mantenha os campos que dependem do usuario entre
colchetes `[ ]`. Nao adicione roteiro nem explicacao longa depois — so o prompt e uma linha de
como usar.

## Referencias
- `references/template-prompt.md` — o template parametrizado (modo existente e modo do zero).
- `references/jornadas-por-nicho.md` — mapas de cena prontos por nicho + como criar novos.
