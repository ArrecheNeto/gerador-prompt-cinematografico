# Template parametrizado do prompt (Higgsfield)

Dois modos. Preencha as `{VARIAVEIS}` a partir do que o usuario informou e da jornada montada
(veja `jornadas-por-nicho.md`). Entregue o resultado num unico bloco de codigo. Mantenha campos
que o usuario preenche depois entre colchetes `[ ]`.

Variaveis a preencher:
- `{NICHO}` — ex: estudio de tatuagem, cafeteria especial.
- `{NOME_NEGOCIO}` — ex: [NOME DO ESTUDIO].
- `{DESCRICAO_NEGOCIO}` — 1 frase real do que o negocio faz.
- `{PESSOA}` — nome de quem aparece no reveal, ou o produto heroi (se nao houver pessoa).
- `{PASTA_REF}` — ex: `assets/referencias-tatuador/`.
- `{HERO_IMG}` — descricao da imagem hero (ferramenta/simbolo do nicho).
- `{DIRECAO_ARTE}` — ex: intimista/noir; publicitaria e acolhedora.
- `{CENAS}` — as 4-5 cenas numeradas da jornada.
- `{SECOES}` — as secoes da landing (hero + etapas + conteudo real + CTA).
- `{COR_DESTAQUE}` / `{PALETA}` — ex: fundo grafite, texto branco quente, detalhe ambar.
- `{URL}` — so no modo "criar do zero".

---

## MODO A — Transformar um site existente

```
[{NICHO} — {NOME_NEGOCIO}]

Transforme o site existente nesta pasta em uma landing page cinematografica, com qualidade
visual de site premiado e efeito de "rolagem 3D", para {NOME_NEGOCIO}, {DESCRICAO_NEGOCIO}.

Antes de alterar os arquivos, analise todo o projeto e crie um backup. Preserve o conteudo real
das paginas de inicio, servicos, sobre e contato, incluindo historia de {PESSOA}, servicos,
depoimentos, perguntas frequentes, SEO local e links do WhatsApp. Reuna tudo em uma unica
`index.html`, como uma landing page continua. Substitua links para paginas separadas por
ancoras internas e nao invente informacoes.

VISUAIS: gere todos os conteudos usando o Higgsfield MCP. Use o modelo de geracao de imagens e
videos mais cinematografico disponivel, dando preferencia ao Cinema Studio 3.0 em 4K, com
direcao cinematografica {DIRECAO_ARTE}. Todos os clipes devem ter proporcao 16:9, duracao entre
5 e 10 segundos e nenhum audio.

Primeiro gere UMA imagem principal cinematografica de {HERO_IMG}. Depois anime essa imagem e
use-a como referencia visual em todos os clipes seguintes, para que ambiente, objetos,
materiais, iluminacao, cores e toda a direcao artistica permanecam consistentes durante a
experiencia.

As fotografias reais de {PESSOA} estao em `{PASTA_REF}`. Envie-as ao Higgsfield pelo MCP e
use-as como `identity reference` em toda cena em que {PESSOA} aparecer. Preserve rosto, idade
aparente, cabelo, tom de pele, tipo fisico e caracteristicas reconheciveis. Mantenha a mesma
roupa profissional neutra.

Gere os clipes na ordem e use o ultimo quadro de cada clipe como `start_image` do proximo
sempre que possivel, criando uma jornada continua no mesmo ambiente:
{CENAS}

Todos os clipes devem ser fotorrealistas, com fotografia publicitaria cinematografica, camera
lenta e estavel, profundidade de campo, luz volumetrica sutil, sombras naturais e materiais
detalhados. Mantenha a continuidade do ambiente, objetos, roupa e identidade. Evite maos
deformadas, dedos extras, objetos flutuando, processos impossiveis, arquitetura instavel,
logotipos, marcas d'agua e textos dentro das imagens ou videos.

SITE: converta os clipes em uma sequencia de quadros no canvas controlada pela rolagem. Rolar
para baixo deve avancar a historia e voltar deve retornar os quadros. Use GSAP com ScrollTrigger
para fixar o canvas, controlar a sequencia e revelar textos HTML nos momentos corretos. Use
Lenis para smooth scroll, sincronizado com GSAP e ScrollTrigger.

Organize a landing page em uma experiencia continua: {SECOES}. Use somente o conteudo real
extraido do projeto.

Nao coloque nomes, logotipos ou textos nos videos. Todo titulo, servico e CTA deve ser HTML real
sobreposto as cenas. Use {PALETA}, tipografia editorial forte e movimentos elegantes. Preserve
o WhatsApp como principal conversao.

Otimize a sequencia e crie uma versao responsiva, com fallback mais leve para celular e para
`prefers-reduced-motion`. Execute o site em localhost e verifique em um navegador real se todas
as animacoes de rolagem funcionam corretamente antes de dizer que esta pronto. Teste o scroll
para frente e para tras, transicoes, canvas, Lenis, ScrollTrigger, desktop, mobile, ancoras e
links do WhatsApp. Corrija saltos, quadros vazios, textos sobrepostos e erros no console antes
de concluir.
```

---

## MODO B — Criar do zero (usando um site como fonte)

Diferencas em relacao ao Modo A: nao ha arquivos; usa `{URL}` como fonte; cria layout novo e
original; pode usar UM UNICO video (jornada continua) em vez de varios clipes; gera de 6 a 8
fotos estaticas de apoio.

```
[{NICHO} — {NOME_NEGOCIO}]

Crie do zero uma landing page cinematografica, com qualidade visual de site premiado e efeito de
"rolagem 3D", para {NOME_NEGOCIO}, {DESCRICAO_NEGOCIO}. Nao ha arquivos nesta pasta. Use como
fonte de conteudo o site existente em {URL}. Analise o site e preserve as informacoes reais —
historia, servicos/menu, enderecos, horarios, depoimentos, redes sociais e contato/WhatsApp.
Crie uma landing page unica e original, sem copiar o layout atual, e nao invente informacoes.

VISUAIS: gere todos os conteudos usando o Higgsfield MCP. Use o modelo de geracao de imagens e
videos mais cinematografico disponivel, dando preferencia ao Cinema Studio 3.0 em 4K, com
direcao cinematografica {DIRECAO_ARTE}. Todos os clipes devem ter proporcao 16:9 e nenhum audio.

Primeiro gere UMA imagem principal cinematografica de {HERO_IMG}, sem marca, logotipo ou texto.
Depois anime essa imagem em UM UNICO video cinematografico continuo, no estilo dos comerciais da
Apple, em que o produto "se abre" e a camera percorre a jornada. Use essa imagem como referencia
visual para manter paleta, iluminacao e direcao artistica consistentes.

CRITICO: gere SOMENTE UM video (a jornada continua). Nao crie videos separados para cada secao.
Gere tambem entre 6 e 8 fotografias estaticas cinematograficas de apoio.

SITE: converta o video em uma sequencia de quadros no canvas controlada pela rolagem. Rolar para
baixo deve avancar a jornada e voltar deve retornar os quadros. Use GSAP com ScrollTrigger para
fixar o canvas, controlar a sequencia e revelar textos HTML nos momentos corretos. Use Lenis
para smooth scroll, sincronizado com GSAP e ScrollTrigger.

Organize a landing page em uma experiencia continua: {SECOES}. Use somente o conteudo real
extraido do site.

Nao coloque nomes, logotipos ou textos nos videos. Todo titulo, item e CTA deve ser HTML real
sobreposto as cenas. Use {PALETA}, tipografia editorial forte e movimentos elegantes. Preserve
o WhatsApp como principal conversao. Evite maos deformadas, dedos extras, objetos flutuando,
liquido/elementos irreais, logotipos, marcas d'agua e textos dentro das imagens ou videos.

Otimize a sequencia e crie uma versao responsiva, com fallback mais leve para celular e para
`prefers-reduced-motion`. Execute o site em localhost e verifique em um navegador real se todas
as animacoes de rolagem funcionam corretamente antes de dizer que esta pronto. Teste o scroll
para frente e para tras, transicoes, canvas, Lenis, ScrollTrigger, desktop, mobile, ancoras e
links do WhatsApp. Corrija saltos, quadros vazios, textos sobrepostos e erros no console antes
de concluir.
```
