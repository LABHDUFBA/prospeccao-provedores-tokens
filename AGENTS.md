# AGENTS.md — Prospecção de Provedores e Tokens de IA

> Diretrizes para agentes de IA (Hermes, Claude, GPT, etc.) e agentes humanos que operam este repositório.

## Missão

Mapear, registrar, verificar, solicitar e acompanhar oportunidades de acesso gratuito, subsidiado ou institucional a provedores, programas, APIs e modelos de IA para pesquisa, ensino, desenvolvimento e inovação, mantendo rastreabilidade documental das fontes, decisões e mudanças ao longo do tempo.

## Entidades do repositório

- **Provedor**: organização, plataforma ou serviço que oferece acesso a modelos ou infraestrutura de IA. Ex.: OpenAI, Anthropic, Google Cloud, Azure AI Foundry, Hugging Face.
- **Modelo**: sistema/modelo específico ou família versionada acessível por API, plataforma ou download. Ex.: GPT-4o, Claude 3.5 Sonnet, Gemini 1.5 Pro, Llama 3.1.
- **Programa**: iniciativa recorrente ou institucional de acesso, crédito, desconto ou apoio. Ex.: Google Cloud Research Credits, OpenAI Researcher Access Program.
- **Oportunidade**: instância concreta e acompanhável de acesso, chamada, edital, oferta ou solicitação possível, normalmente vinculada a um programa, ciclo ou prazo. Ex.: Google Cloud Research Credits 2025 para pesquisadores.
- **Fonte**: documento, página, notícia, anúncio ou evidência usada para sustentar os dados.

## Princípios

1. **Verdade acima de completude** — Registre apenas fatos verificados. Se a informação é rumor ou estimativa, marque explicitamente como `[não confirmado]`, `[estimativa]` ou `[inferência]`.
2. **Rastro de fontes** — Cada fato relevante requer fonte com URL, data de acesso e trecho relevante. Sem fonte = sem entrada factual.
3. **Separação entre fato, inferência e decisão** — Fatos devem estar apoiados em fonte. Inferências devem ser marcadas como `[inferência]`. Decisões internas, como prioridade, responsável ou próximo passo, devem ser identificadas como decisão da equipe/repositório.
4. **Hierarquia de fontes** — Em caso de conflito, priorizar: página oficial do programa/provedor → documentação oficial/API/pricing → blog oficial → comunicado institucional → notícia de terceiro → redes sociais → agregadores.
5. **Cruzamento obrigatório** — Antes de criar uma ficha, verifique se já existe entrada para o mesmo provedor, modelo, programa ou oportunidade. Atualize em vez de duplicar.
6. **Status sempre atual** — Toda oportunidade deve ter `Última atualização` e, quando aplicável, `Próxima verificação`. Por padrão, revisar após 30 dias; para programas instáveis/promocionais, revisar em 7 ou 15 dias; para programas anuais, revisar próximo ao ciclo de renovação.
7. **Sem alucinação de preços** — Nunca invente preços, limites de tokens, datas ou condições. Se não encontrou, escreva `Desconhecido (verificar)`.
8. **Não registrar segredos ou dados sensíveis** — Nunca incluir chaves de API, tokens, senhas, dados pessoais desnecessários, documentos internos restritos ou informações confidenciais.
9. **Idioma** — Fichas em português brasileiro. Nomes próprios, termos técnicos e nomes de provedores/modelos mantêm o original quando apropriado.

## Estrutura de Fichas

### Provedor (`dados/provedores/YYYY-MM-DD-nome-provedor.md`)

```markdown
# [Nome do Provedor]

| Campo | Valor |
|-------|-------|
| **ID interno** | provedor/nome-provedor |
| **Nome legal / marca** | Nome oficial, se diferente |
| **URL** | https://... |
| **URL de pricing** | https://... |
| **URL de documentação/API** | https://... |
| **Sede** | País, cidade |
| **Tipo** | Cloud / On-premise / Edge / Marketplace / Outro |
| **Meios de acesso** | API / Console web / Cloud marketplace / Open source / Outro |
| **Modelos próprios** | Lista |
| **Modelos terceiros** | Lista, se houver |
| **Tier gratuito** | Sim/Não + detalhes |
| **Desconto acadêmico** | Sim/Não + detalhes |
| **Programa de pesquisa** | Sim/Não + nome + link |
| **Regiões atendidas** | Global / EUA / UE / Brasil / Desconhecido (verificar) |
| **Elegibilidade Brasil** | Sim / Não / Desconhecido (verificar) |
| **Moeda de cobrança** | USD / BRL / EUR / Desconhecido |
| **Contato comercial/institucional** | Email ou formulário |
| **Termos de uso relevantes** | Link e observações |
| **Política de uso de dados** | Retenção, treinamento com dados do usuário, privacidade; ou Desconhecido (verificar) |
| **Status do provedor** | Ativo / Indisponível / Verificar / Arquivado |
| **Notas** | Observações relevantes |
| **Última atualização** | YYYY-MM-DD |
| **Última verificação** | YYYY-MM-DD |
| **Próxima verificação** | YYYY-MM-DD ou Desconhecido (verificar) |
| **Fontes principais** | URLs com data de acesso |

## Programas e oportunidades relacionados

| Programa/Oportunidade | Tipo | Ciclo/versão | Status | Link interno |
|-----------------------|------|--------------|--------|--------------|
| ... | ... | ... | ... | ... |

## Modelos disponíveis

| Modelo | Tipo | Disponível via | Tier gratuito | Preço conhecido | Link interno |
|--------|------|----------------|---------------|-----------------|--------------|
| ... | ... | ... | ... | ... | ... |

## Histórico de alterações

- YYYY-MM-DD: Ficha criada por [agente/pessoa]
```

### Modelo (`dados/modelos/YYYY-MM-DD-nome-modelo.md`)

```markdown
# [Nome do Modelo]

| Campo | Valor |
|-------|-------|
| **ID interno** | modelo/nome-modelo |
| **Provedor original** | Organização que desenvolve o modelo |
| **Família** | GPT / Gemini / Claude / Llama / Mistral / etc. |
| **Versão** | x.y, snapshot ou Desconhecido (verificar) |
| **Nome de API / identificador técnico** | ex.: gpt-4o-mini, claude-3-5-sonnet-20241022 |
| **Tipo** | Linguagem / Visão / Áudio / Vídeo / Multimodal / Embeddings / Outro |
| **Modalidades suportadas** | Texto / Imagem / Áudio / Vídeo / Tool use / etc. |
| **Tamanho de contexto** | tokens ou Desconhecido (verificar) |
| **Dados de treinamento / conhecimento até** | Data informada oficialmente ou Desconhecido (verificar) |
| **Licença** | Proprietária / Open weights / Open source / Desconhecido |
| **Disponibilidade** | Geral / Preview / Beta / Restrita / Descontinuada |
| **Data de lançamento** | YYYY-MM-DD ou Desconhecido (verificar) |
| **Data de descontinuação** | YYYY-MM-DD ou Não aplicável |
| **Provedores de acesso** | APIs/plataformas disponíveis |
| **Acesso gratuito** | Sim/Não + detalhes |
| **Última atualização** | YYYY-MM-DD |
| **Última verificação** | YYYY-MM-DD |
| **Próxima verificação** | YYYY-MM-DD ou Desconhecido (verificar) |
| **Fontes principais** | URLs com data de acesso |

## Preços por provedor

| Provedor | API/plataforma | Input/1M tokens | Output/1M tokens | Moeda | Data da fonte | Fonte |
|----------|----------------|-----------------|------------------|-------|---------------|-------|
| ... | ... | ... | ... | ... | ... | ... |

## Oportunidades de acesso

- [Vincular para ficha de oportunidade, se houver]

## Disponibilidade por provedor

| Provedor | API | Tier gratuito | Preço | Notas |
|----------|-----|---------------|-------|-------|
| ... | ... | ... | ... | ... |

## Histórico de alterações

- YYYY-MM-DD: Ficha criada por [agente/pessoa]
```

### Oportunidade (`dados/oportunidades/YYYY-MM-DD-tipo-instituicao.md`)

```markdown
# [Nome da Oportunidade]

| Campo | Valor |
|-------|-------|
| **ID interno** | oportunidade/provedor-programa-ciclo |
| **Tipo** | Créditos gratuitos / Desconto acadêmico / Programa de pesquisa / Trial / Parceria / Tier gratuito permanente / Desconto para startups / Oferta promocional |
| **Provedor** | Nome do provedor |
| **Programa relacionado** | Nome do programa, se houver |
| **Ciclo/versão do programa** | 2025 / Spring 2025 / v2 / Contínuo |
| **Substitui** | Link para oportunidade/programa anterior, se houver |
| **Substituído por** | Link para nova oportunidade/programa, se houver |
| **Modelos incluídos** | Lista ou Desconhecido (verificar) |
| **Instituição elegível/específica** | Nome da instituição, se específica |
| **Público-alvo** | Pesquisadores / estudantes / startups / instituições / open source / outro |
| **Elegibilidade para UFBA/Brasil** | Sim / Não / Desconhecido (verificar) |
| **Requisitos** | O que é necessário para solicitar |
| **Benefícios** | Créditos, descontos, acesso estendido, limites |
| **Valor estimado** | US$ X/mês ou ano; ou Desconhecido (verificar) |
| **Moeda** | USD / BRL / EUR / Outra |
| **Janela de candidatura** | Data inicial e final, ou Contínuo |
| **Prazo final** | YYYY-MM-DD ou Contínuo |
| **Validade do benefício** | Ex.: créditos válidos por 12 meses |
| **URL oficial** | https://... |
| **URL de candidatura/solicitação** | https://... |
| **Contrapartidas exigidas** | Relatório, publicação, divulgação, caso de uso etc. |
| **Restrições de uso** | Pesquisa apenas, não comercial, limite geográfico etc. |
| **Acionabilidade** | Acionável / Informacional / Aguardar abertura / Não acionável |
| **Prioridade** | Alta / Média / Baixa |
| **Próximo passo** | Ação objetiva e responsável |
| **Status do programa** | Ativo / Pausado / Encerrado / Substituído / Desconhecido |
| **Status da prospecção** | 🔍 Identificada / 📋 Em análise / 📝 Formulário iniciado / 📤 Submetida / ⏳ Aguardando resposta / ✅ Convertida / ❌ Recusada / ⏰ Expirada / 🔁 Verificar |
| **Responsável** | Pessoa ou grupo |
| **Última atualização** | YYYY-MM-DD |
| **Última verificação** | YYYY-MM-DD |
| **Próxima verificação** | YYYY-MM-DD ou Desconhecido (verificar) |
| **Fontes principais** | URLs com data de acesso |

## Cronologia

- YYYY-MM-DD: Oportunidade identificada em [fonte]
- YYYY-MM-DD: Formulário de solicitação enviado
- ...

## Divergências entre fontes

- YYYY-MM-DD: Fonte A informa X; fonte B informa Y. Valor adotado: Z, por ser fonte oficial.

## Dados não confirmados

- [não confirmado] ...

## Notas e observações

- ...
```

## Workflow de Prospecção

### 1. Identificar oportunidade

Quando um agente encontrar uma oportunidade em notícia, anúncio, site ou documentação:

1. Registrar a fonte inicial.
2. Identificar provedor, modelo(s), programa, tipo de oferta, público-alvo, requisitos, benefícios, valores e prazos.
3. Classificar a fonte como `oficial`, `documentação/pricing`, `blog oficial`, `notícia de terceiro`, `agregador`, `rede social` ou `rumor`.
4. Verificar se há página oficial do programa/provedor.
5. Se não houver fonte oficial, marcar a oportunidade como `Informacional` ou `Desconhecido (verificar)`.

### 2. Deduplicar e cruzar

Antes de criar ficha:

1. Buscar duplicatas por nome oficial, aliases, nomes anteriores, provedor, modelo, URL, programa e ciclo.
2. Verificar fichas existentes em `dados/provedores/`, `dados/modelos/`, `dados/oportunidades/` e `fontes/`.
3. Atualizar ficha existente quando se tratar do mesmo programa/ciclo.
4. Criar nova ficha quando houver novo ciclo, nova chamada, mudança substancial de condições ou oportunidade distinta.

### 3. Criar ou atualizar fichas

1. Criar ficha de oportunidade em `dados/oportunidades/` ou atualizar a existente.
2. Se o provedor ou modelo não existir, criar fichas correspondentes.
3. Registrar a fonte em `fontes/YYYY-MM-DD-tipo-fonte.md`.
4. Vincular fichas entre si: oportunidade → provedor; oportunidade → modelo; provedor/modelo → oportunidade.
5. Atualizar a matriz consolidada em `dados/matrizes/provedores-modelos.md`, se aplicável.

### 4. Verificar e cruzar informações

- Comparar dados da notícia com site oficial do provedor.
- Confirmar preços, limites, requisitos e prazos em página oficial ou documentação.
- Se houver divergência, registrar ambas as versões em `## Divergências entre fontes`, com URLs, datas e trechos.
- Não converter moeda sem registrar taxa, data e fonte da conversão.

### 5. Avaliar acionabilidade e prioridade

- `Acionabilidade` indica se há ação possível agora. `Prioridade` indica relevância estratégica. Não usar uma como sinônimo da outra.
- Marcar Acionabilidade: Acionável / Informacional / Aguardar abertura / Não acionável.
- Marcar Prioridade: Alta / Média / Baixa, justificando em 1-3 frases.
- Indicar próximo passo objetivo.
- Oportunidades de alta prioridade ou que exijam submissão institucional devem passar por revisão humana antes de contato externo.

### 6. Solicitar ou encaminhar

- Se a oportunidade é acionável, registrar quem pode solicitar.
- Marcar status da prospecção como `📋 Em análise`, `📝 Formulário iniciado`, `📤 Submetida` ou `⏳ Aguardando resposta`.
- Documentar cada passo na `Cronologia`.
- Não registrar credenciais, tokens, chaves de API ou documentos sensíveis.

### 7. Acompanhar

- Registrar cada atualização na seção `Cronologia`.
- Atualizar `Status do programa` e `Status da prospecção` separadamente.
- Atualizar `Última atualização`, `Última verificação` e `Próxima verificação`.

### 8. Concluir

- **Convertida**: registrar acesso obtido, valores, limites e prazo de validade, sem expor credenciais.
- **Recusada**: registrar motivo, se disponível.
- **Expirada**: registrar data de expiração.
- **Substituída**: vincular para nova ficha/ciclo.
- Adicionar entrada ao `Histórico de alterações`.

## Processamento de Notícias

Quando um agente recebe uma notícia sobre oferta de tokens/IA:

1. **Extrair** — Identificar provedor, modelo(s), programa, tipo de oferta, público-alvo, valores, prazo, requisitos e URLs.
2. **Classificar fonte** — Determinar se é oficial, documentação/pricing, blog oficial, notícia de terceiro, agregador, rede social ou rumor.
3. **Verificar** — Cruzar com site oficial do provedor, página de pricing, documentação ou página do programa.
4. **Deduplicar** — Verificar se já existe ficha para o mesmo provedor, modelo, programa ou ciclo.
5. **Decidir** — Criar nova ficha, atualizar ficha existente ou apenas registrar fonte.
6. **Criar/Vincular** — Criar ou atualizar ficha de oportunidade e vincular com provedor/modelo.
7. **Registrar fonte** — Arquivar a notícia original em `fontes/`.
8. **Avaliar acionabilidade** — Indicar se há próximos passos possíveis e quem pode tomar.
9. **Atualizar matriz** — Atualizar `dados/matrizes/provedores-modelos.md`, quando aplicável.

## Formato de Fontes (`fontes/YYYY-MM-DD-tipo-fonte.md`)

```markdown
# [Título da notícia ou fonte]

| Campo | Valor |
|-------|-------|
| **Tipo de fonte** | Oficial / Documentação / Pricing / Blog oficial / Notícia / Agregador / Rede social |
| **Confiabilidade** | Alta / Média / Baixa |
| **URL** | https://... |
| **URL arquivada** | Internet Archive, Perma.cc ou outro, se houver |
| **Data da publicação** | YYYY-MM-DD |
| **Data de acesso** | YYYY-MM-DD |
| **Autor/organização publicadora** | Nome |
| **Idioma da fonte** | PT / EN / Outro |
| **Provedor(es) citado(s)** | Lista |
| **Modelo(s) citado(s)** | Lista |
| **Programa(s) citado(s)** | Lista |
| **Oportunidade(s) gerada(s)** | Link para ficha(s) |
| **Resumo** | 1-3 parágrafos com os pontos relevantes |

## Trechos relevantes

> "Citação direta da fonte"

## Dados extraídos

- Provedor X oferece Y créditos para Z
- Modelo A disponível gratuitamente para pesquisadores
- ...

## Lacunas

- Campo não encontrado: ...
- Necessário verificar: ...

## Histórico

- YYYY-MM-DD: Fonte registrada por [agente/pessoa]
```

## Matriz consolidada de provedores vs. modelos

Manter o arquivo `dados/matrizes/provedores-modelos.md`:

```markdown
# Matriz consolidada de provedores vs. modelos

| Provedor | Modelo/Família | Tipo | API/Plataforma | Acesso gratuito | Programa/Oportunidade relacionada | Preço verificado | Status | Última verificação | Fontes |
|----------|----------------|------|-----------------|-----------------|-----------------------------------|------------------|--------|--------------------|--------|
| ... | ... | ... | ... | ... | ... | ... | ... | ... | ... |
```

Atualizar a matriz sempre que uma ficha de provedor, modelo ou oportunidade alterar disponibilidade, preço, acesso gratuito ou programa relacionado.

## Programas com mudanças frequentes

Para programas que mudam nome, URL, critérios, valores ou ciclos:

1. Não sobrescrever silenciosamente condições antigas.
2. Registrar `Ciclo/versão do programa`.
3. Registrar `Nome anterior`, `Nome atual`, `Substitui` e `Substituído por`, quando aplicável.
4. Manter histórico com data e fonte de cada condição.
5. Se o programa for recorrente anual, criar ou atualizar a oportunidade do novo ciclo.
6. Se apenas a página mudou, atualizar URL e preservar URL antiga no histórico.
7. Se as condições mudaram substancialmente, registrar nova entrada de cronologia e considerar nova ficha de oportunidade para o novo ciclo.
8. Marcar oportunidades antigas como `Expirada`, `Encerrada` ou `Substituída`, sem apagá-las.

## Versionamento de programas

Para programas recorrentes, usar identificadores por ciclo, por exemplo:

- `google-cloud-research-credits-2024`
- `google-cloud-research-credits-2025`

Criar nova ficha de oportunidade quando houver:

- novo ano/ciclo;
- novo prazo;
- novo formulário;
- mudança substancial de elegibilidade;
- mudança substancial de valor, benefício ou restrição;
- renomeação oficial do programa.

Quando o programa apenas alterar uma URL ou corrigir texto menor, atualizar a ficha existente e registrar no histórico.

## Commits

Mensagens de commit seguem formato convencional:

- `feat:` nova ficha ou nova seção estrutural
- `update:` atualização de status, preços, requisitos ou fonte
- `fix:` correção factual, ortográfica ou de link
- `docs:` alteração em diretrizes, templates ou documentação
- `data:` atualização de matriz, vínculo ou metadado estruturado
- `archive:` marcação de programa encerrado, expirado ou substituído

## Anti-padrões (NÃO fazer)

- ❌ Inventar preços, limites, datas ou condições não encontrados em fontes
- ❌ Criar fichas duplicadas sem verificar nomes, aliases, URLs e ciclos anteriores
- ❌ Deixar campos obrigatórios em branco sem `Desconhecido (verificar)`
- ❌ Registrar oportunidades sem fonte ou URL
- ❌ Copiar texto diretamente de fontes sem reformular; usar paráfrase e citações diretas curtas entre aspas
- ❌ Remover histórico de alterações de fichas existentes
- ❌ Confundir provedor, modelo, programa e oportunidade
- ❌ Tratar notícia de terceiro como confirmação oficial de preço ou elegibilidade
- ❌ Assumir que uma oferta global é válida para Brasil/UFBA sem fonte
- ❌ Converter moedas sem registrar taxa, data e fonte
- ❌ Inferir tamanho de contexto, preço ou versão a partir do nome do modelo
- ❌ Atualizar preço sem preservar preço anterior no histórico
- ❌ Marcar oportunidade como acionável sem URL de candidatura ou instrução clara
- ❌ Registrar contatos pessoais, credenciais, chaves de API, tokens ou dados sensíveis
- ❌ Criar nova ficha para programa recorrente sem verificar ciclos anteriores
- ❌ Apagar informação histórica quando programa for renomeado, encerrado ou substituído

## Checklist final antes de salvar

Antes de criar ou atualizar fichas, verificar:

- [ ] Há fonte com URL e data de acesso?
- [ ] Há trecho relevante citado?
- [ ] A fonte é oficial ou a falta de fonte oficial foi marcada?
- [ ] Provedor, modelo, programa e oportunidade foram diferenciados?
- [ ] Foi feita busca por duplicatas?
- [ ] Campos desconhecidos foram preenchidos como `Desconhecido (verificar)`?
- [ ] Status do programa e status da prospecção estão separados?
- [ ] Última atualização e próxima verificação foram registradas?
- [ ] Programas recorrentes foram versionados?
- [ ] A matriz provedores-modelos foi atualizada, se necessário?
- [ ] Não há dados sensíveis, tokens ou credenciais?