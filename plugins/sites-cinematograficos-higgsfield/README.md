# Sites Cinematográficos (Higgsfield)

Gera prompts completos e prontos para colar no Claude que criam **sites e landing pages
cinematográficos com efeito de rolagem 3D** usando o **Higgsfield MCP**. A saída é sempre
**só o prompt** — pronto pra você colar no Claude com o Higgsfield conectado.

## O que ele faz

Você diz o nicho, ele monta a jornada visual (hero → processo → reveal) e devolve o prompt
inteiro com toda a engenharia embutida: geração de imagem/vídeo no Higgsfield (Cinema Studio 3.0,
4K, 16:9, sem áudio), imagem hero animada como referência, encadeamento de quadros, `identity
reference` da pessoa, canvas controlado por rolagem com GSAP + ScrollTrigger + Lenis, versão
responsiva com `prefers-reduced-motion` e verificação em localhost.

## Como usar

**Skill flexível** (qualquer nicho): peça algo como
"gera um prompt de site cinematográfico para um pet shop" ou "site com Higgsfield para uma
clínica". A skill `gerador-prompt-cinematografico` monta a jornada na hora.

**Comandos-preset** (nichos prontos):

| Comando | Nicho |
|---|---|
| `/site-tatuagem` | Estúdio de tatuagem |
| `/site-cafeteria` | Cafeteria especial |
| `/site-restaurante` | Restaurante |
| `/site-imobiliaria` | Imobiliária / imóvel de alto padrão |
| `/site-academia` | Academia / estúdio fitness |

## Dois modos

- **Transformar site existente** — já há um site na pasta; preserva o conteúdo real e reúne
  tudo numa `index.html` cinematográfica.
- **Criar do zero (via URL)** — pasta vazia; usa um site existente como fonte de conteúdo e cria
  uma landing nova e original.

## Pré-requisitos (pra rodar o prompt gerado)

- Higgsfield MCP conectado no Claude e com créditos.
- Pasta do projeto selecionada.
- Fotos de referência da pessoa em `assets/referencias-.../` (quando houver reveal de pessoa).

## Componentes

- **1 skill** — `gerador-prompt-cinematografico` (flexível, qualquer nicho).
- **5 comandos** — presets dos nichos acima.
- **2 referências** — `template-prompt.md` (o template) e `jornadas-por-nicho.md` (mapas de cena).
