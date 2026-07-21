# Template parametrizado do prompt (Higgsfield)

Um unico template. Duas escolhas INDEPENDENTES definem o prompt final:

1. **FONTE do conteudo** — de onde vem o texto real do site: `PASTA` (arquivos ja estao na pasta)
   ou `URL` (a pasta esta vazia e o conteudo vem de um site online).
2. **FORMATO visual** — `CLIPES` (4-5 clipes encadeados, jornada em etapas) ou
   `VIDEO_UNICO` (um unico video continuo estilo comercial da Apple).

As duas escolhas nao dependem uma da outra. Ex: FONTE=URL + FORMATO=CLIPES e uma combinacao
valida e comum. **Se a FONTE for URL, o prompt NUNCA pode falar em "site existente nesta pasta",
"analise o projeto" ou "faca backup dos arquivos" — nao ha arquivos.**

Variaveis a preencher:
- `{NICHO}` — ex: estudio de tatuagem, cafeteria especial.
- `{NOME_NEGOCIO}` — ex: [NOME DO ESTUDIO].
- `{DESCRICAO_NEGOCIO}` — 1 frase real do que o negocio faz.
- `{PESSOA}` — nome de quem aparece no reveal, ou o produto heroi (se nao houver pessoa).
- `{PASTA_REF}` — ex: `assets/referencias-tatuador/`.
- `{HERO_IMG}` — descricao da imagem hero (ferramenta/simbolo do nicho).
- `{DIRECAO_ARTE}` — ex: intimista/noir; publicitaria e acolhedora.
- `{CENAS}` — as 4-5 cenas numeradas da jornada (so no FORMATO=CLIPES).
- `{JORNADA}` — a jornada continua numa frase (so no FORMATO=VIDEO_UNICO).
- `{SECOES}` — as secoes da landing (hero + etapas + conteudo real + CTA).
- `{PALETA}` — ex: fundo grafite, texto branco quente, detalhe dourado.
- `{URL}` — obrigatorio quando FONTE=URL.
- `{CONTEUDO_REAL}` — o que preservar: historia, servicos/menu, precos, enderecos, horarios,
  depoimentos, FAQ, redes sociais, contato/WhatsApp.

---

## Montagem do prompt

Monte sempre nesta ordem, escolhendo o BLOCO 1 conforme a FONTE e o BLOCO 3 conforme o FORMATO.
Os blocos 2, 4, 5 e 6 sao fixos.

---

### BLOCO 1 — Abertura + conteudo (escolha UMA variante)

**Variante FONTE = PASTA**

```
[{NICHO} — {NOME_NEGOCIO}]

Transforme o site existente nesta pasta em uma landing page cinematografica, com qualidade
visual de site premiado e efeito de "rolagem 3D", para {NOME_NEGOCIO}, {DESCRICAO_NEGOCIO}.

Antes de alterar os arquivos, analise todo o projeto e crie um backup. Preserve o conteudo real
das paginas de inicio, servicos, sobre e contato, incluindo {CONTEUDO_REAL}. Reuna tudo em uma
unica `index.html`, como uma landing page continua. Substitua links para paginas separadas por
ancoras internas e nao invente informacoes.
```

**Variante FONTE = URL**

```
[{NICHO} — {NOME_NEGOCIO}]

Crie nesta pasta uma landing page cinematografica, com qualidade visual de site premiado e
efeito de "rolagem 3D", para {NOME_NEGOCIO}, {DESCRICAO_NEGOCIO}.

Nao ha arquivos nesta pasta e nao existe site local para transformar. Use como unica fonte de
conteudo o site publicado em {URL}. Acesse essa URL, leia todas as paginas internas e extraia o
conteudo real: {CONTEUDO_REAL}. Crie uma `index.html` unica, original e continua, sem copiar o
layout atual do site de origem, e nao invente nenhuma informacao — se algum dado nao existir na
URL, deixe um marcador claro entre colchetes para eu preencher depois.
```

---

### BLOCO 2 — Visuais e identidade (fixo)

```
VISUAIS: gere todos os conteudos usando o Higgsfield MCP. Use o modelo de geracao de imagens e
videos mais cinematografico disponivel, dando preferencia ao Cinema Studio 3.0 em 4K, com
direcao cinematografica {DIRECAO_ARTE}. Todos os clipes devem ter proporcao 16:9, duracao entre
5 e 10 segundos e nenhum audio.

Primeiro gere UMA imagem principal cinematografica de {HERO_IMG}, sem marca, logotipo ou texto.
Depois anime essa imagem e use-a como referencia visual em todos os clipes seguintes, para que
ambiente, objetos, materiais, iluminacao, cores e toda a direcao artistica permanecam
consistentes durante a experiencia.

As fotografias reais de {PESSOA} estao em `{PASTA_REF}`. Envie-as ao Higgsfield pelo MCP e
use-as como `identity reference` em toda cena em que {PESSOA} aparecer. Preserve rosto, idade
aparente, cabelo, tom de pele, tipo fisico e caracteristicas reconheciveis. Mantenha a mesma
roupa profissional neutra.
```

> Se nao houver pessoa no reveal, remova o paragrafo do `identity reference` e troque {PESSOA}
> pelo produto heroi.

---

### BLOCO 3 — Geracao dos videos (escolha UMA variante)

**Variante FORMATO = CLIPES**

```
Gere os clipes na ordem e use o ultimo quadro de cada clipe como `start_image` do proximo
sempre que possivel, criando uma jornada continua no mesmo ambiente:
{CENAS}
```

**Variante FORMATO = VIDEO_UNICO**

```
Anime a imagem principal em UM UNICO video cinematografico continuo, no estilo dos comerciais
da Apple, em que a camera percorre a jornada inteira sem cortes: {JORNADA}.

CRITICO: gere SOMENTE UM video (a jornada continua). Nao crie videos separados para cada secao.
Gere tambem entre 6 e 8 fotografias estaticas cinematograficas de apoio, na mesma direcao de
arte, para ilustrar as secoes de conteudo.
```

---

### BLOCO 4 — Qualidade e constraints (fixo)

```
Todos os clipes devem ser fotorrealistas, com fotografia publicitaria cinematografica, camera
lenta e estavel, profundidade de campo, luz volumetrica sutil, sombras naturais e materiais
detalhados. Mantenha a continuidade do ambiente, objetos, roupa e identidade. Evite maos
deformadas, dedos extras, objetos flutuando, processos impossiveis, arquitetura instavel,
logotipos, marcas d'agua e textos dentro das imagens ou videos.
```

---

### BLOCO 5 — Site e rolagem (fixo, so muda "os clipes"/"o video")

```
SITE: converta {os clipes | o video} em uma sequencia de quadros no canvas controlada pela
rolagem. Rolar para baixo deve avancar a historia e voltar deve retornar os quadros. Use GSAP
com ScrollTrigger para fixar o canvas, controlar a sequencia e revelar textos HTML nos momentos
corretos. Use Lenis para smooth scroll, sincronizado com GSAP e ScrollTrigger.

Organize a landing page em uma experiencia continua: {SECOES}. Use somente o conteudo real
{extraido do projeto | extraido da URL de origem}.

Nao coloque nomes, logotipos ou textos nos videos. Todo titulo, servico e CTA deve ser HTML real
sobreposto as cenas. Use {PALETA}, tipografia editorial forte e movimentos elegantes. Preserve
o WhatsApp como principal conversao.
```

---

### BLOCO 6 — Responsivo e verificacao (fixo)

```
Otimize a sequencia e crie uma versao responsiva, com fallback mais leve para celular e para
`prefers-reduced-motion`. Execute o site em localhost e verifique em um navegador real se todas
as animacoes de rolagem funcionam corretamente antes de dizer que esta pronto. Teste o scroll
para frente e para tras, transicoes, canvas, Lenis, ScrollTrigger, desktop, mobile, ancoras e
links do WhatsApp. Corrija saltos, quadros vazios, textos sobrepostos e erros no console antes
de concluir.
```

---

## Checklist antes de entregar

- [ ] Se FONTE=URL: o prompt nao cita "site existente nesta pasta", "analise o projeto" nem "backup".
- [ ] Se FONTE=URL: a `{URL}` aparece explicitamente no prompt.
- [ ] Se FONTE=PASTA: o prompt manda fazer backup antes de alterar.
- [ ] O FORMATO escolhido aparece em UM bloco so (nao misture clipes e video unico).
- [ ] Campos que dependem do usuario ficaram entre colchetes `[ ]`.
