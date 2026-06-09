# Prospecção de Provedores e Tokens de IA

> Base de informações e oportunidades para acesso gratuito ou barato a provedores e modelos de inteligência artificial.

## Propósito

Este repositório mapeia, registra e acompanha oportunidades de acesso a provedores e modelos de IA — seja por programas gratuitos, descontos acadêmicos, créditos para pesquisa ou ofertas promocionais. A meta é prospectar, registrar, solicitar, acompanhar e concluir se cada oportunidade foi convertida ou não resultou em nada.

## Público

Pesquisadores, desenvolvedores e equipes de inovação que precisam de acesso a modelos de IA (LLMs, visão, áudio, etc.) com orçamento limitado. Qualquer pessoa com acesso ao repositório pode avaliar, buscar mais informações e atualizar o status das oportunidades.

## Entidades

- **Provedor**: organização que oferece acesso a modelos ou infraestrutura de IA (OpenAI, Anthropic, Google Cloud, Hugging Face, etc.)
- **Modelo**: sistema/modelo específico ou família versionada (GPT-4o, Claude 3.5 Sonnet, Gemini 1.5 Pro, etc.)
- **Programa**: iniciativa recorrente de acesso, crédito, desconto ou apoio (Google Cloud Research Credits, OpenAI Researcher Access, etc.)
- **Oportunidade**: instância concreta e acompanhável de acesso, chamada ou oferta
- **Fonte**: documento, página ou notícia que sustenta os dados

## Estrutura

```
├── AGENTS.md                      # Diretrizes para agentes de IA e humanos
├── diretrizes-prospeccao.md       # Prompt/diretrizes para processamento de notícias
├── README.md                      # Este arquivo
├── LICENSE                        # CC BY-SA 4.0
├── dados/
│   ├── provedores/                # Fichas por provedor
│   ├── modelos/                   # Fichas por modelo
│   ├── oportunidades/             # Oportunidades de acesso
│   └── matrizes/
│       └── provedores-modelos.md  # Visão consolidada provedores vs. modelos
├── fontes/                        # Notícias, anúncios e referências
└── templates/                     # Modelos para novas fichas
    ├── template-provedor.md
    ├── template-modelo.md
    ├── template-oportunidade.md
    └── template-fonte.md
```

## Tipos de oportunidade

| Tipo | Descrição |
|------|-----------|
| **Créditos gratuitos** | Tokens/créditos oferecidos sem contrapartida financeira |
| **Desconto acadêmico** | Redução de preço para instituições de ensino/pesquisa |
| **Programa de pesquisa** | Acesso estendido para projetos de pesquisa aprovados |
| **Parceria institucional** | Acordos entre org/provedor (ex.: UFBA ↔ Google) |
| **Trial estendido** | Período de teste prolongado para avaliação |
| **Tier gratuito permanente** | Camada free que persiste (ex.: GCP free tier) |
| **Desconto para startups** | Programas como AWS Activate, Google for Startups |
| **Oferta promocional** | Desconto temporário (Black Friday, lançamento, etc.) |

## Status de prospecção

| Status | Significado |
|--------|-------------|
| 🔍 **Identificada** | Oportunidade encontrada em notícia, site ou anúncio |
| 📋 **Em análise** | Informações sendo verificadas e cruzadas |
| 📝 **Formulário iniciado** | Pedido ou inscrição em andamento |
| 📤 **Submetida** | Formulário enviado ao provedor |
| ⏳ **Aguardando resposta** | Formulário enviado, aguardando aprovação |
| ✅ **Convertida** | Acesso obtido e confirmado |
| ❌ **Recusada** | Pedido negado ou programa encerrado |
| ⏰ **Expirada** | Oportunidade passou do prazo ou programa foi descontinuado |
| 🔁 **Verificar** | Necessita revalidação (30+ dias sem atualização) |

## Como contribuir

1. Copie o template apropriado de `templates/`
2. Preencha com os dados disponíveis
3. Adicione referências em `fontes/`
4. Atualize o status conforme o andamento
5. Faça commit com mensagem descritiva (ver `AGENTS.md` para padrões de commit)

## Diretrizes completas

- **AGENTS.md** — Diretrizes completas para operação do repositório (fichas, workflow, anti-padrões)
- **diretrizes-prospeccao.md** — Prompt e diretrizes para processamento de notícias por agentes de IA

## Licença

Creative Commons BY-SA 4.0 — uso livre com atribuição.