# Gerador de Prompt Cinematográfico — Marketplace

Marketplace de plugins do Cowork/Claude Code. Contém o plugin **Sites Cinematográficos
(Higgsfield)**, que gera prompts prontos para criar sites e landing pages cinematográficos com
rolagem 3D usando o Higgsfield MCP.

## Como instalar

No Cowork ou Claude Code:

```
/plugin marketplace add ArrecheNeto/gerador-prompt-cinematografico
/plugin install sites-cinematograficos-higgsfield@arreche-plugins
```

## Plugins

| Plugin | Descrição |
|---|---|
| `sites-cinematograficos-higgsfield` | Gera prompts cinematográficos (Higgsfield MCP) para qualquer nicho — skill flexível + presets (`/site-tatuagem`, `/site-cafeteria`, `/site-restaurante`, `/site-imobiliaria`, `/site-academia`). |

## Estrutura

```
.claude-plugin/marketplace.json          # manifesto do marketplace
plugins/sites-cinematograficos-higgsfield # o plugin
```
