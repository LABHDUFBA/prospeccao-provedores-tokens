## Revisão e refinamento sugeridos

### Seção: Missão → Alteração: delimitar melhor o escopo do repositório  
→ Justificativa: A missão atual fala em “provedores e modelos”, mas o repositório também acompanha **programas**, **oportunidades concretas**, **fontes** e **status de solicitação**. Recomendo explicitar que o repositório não é apenas catálogo técnico, mas também instrumento de acompanhamento operacional.

**Sugestão de ajuste:**

> Mapear, registrar, verificar, solicitar e acompanhar oportunidades de acesso gratuito, subsidiado ou institucional a provedores, programas, APIs e modelos de IA para pesquisa, ensino, desenvolvimento e inovação, mantendo rastreabilidade documental das fontes e das decisões tomadas.

---

### Seção: Princípios → Alteração: adicionar princípio de “separação entre fato, inferência e decisão”  
→ Justificativa: Para agentes de IA, é fundamental separar o que está explicitamente na fonte, o que foi inferido e o que é decisão da equipe. Isso reduz alucinações e melhora auditabilidade.

**Adicionar princípio:**

> **Separação entre fato, inferência e decisão** — Fatos devem estar apoiados em fonte. Inferências devem ser marcadas como `[inferência]`. Decisões internas, como prioridade ou responsável, devem ser marcadas como decisão do repositório/equipe, não como informação da fonte.

---

### Seção: Princípios → Alteração: adicionar regra de hierarquia de fontes  
→ Justificativa: Notícias frequentemente resumem ou distorcem condições de programas. É útil orientar agentes a priorizar fontes oficiais.

**Adicionar princípio:**

> **Hierarquia de fontes** — Em caso de conflito, priorizar nesta ordem: página oficial do programa/provedor; documentação oficial/API/pricing; blog oficial; comunicado institucional; notícia de terceiro; redes sociais; agregadores. Fontes não oficiais podem gerar alerta, mas não devem confirmar condições sozinhas.

---

### Seção: Princípios → Alteração: adicionar orientação sobre informações sensíveis  
→ Justificativa: Ao acompanhar solicitações reais, pode haver e-mails, nomes pessoais, tokens, chaves de API, valores de contrato, credenciais ou documentos institucionais.

**Adicionar princípio:**

> **Não registrar segredos ou dados sensíveis** — Nunca incluir chaves de API, tokens, senhas, dados pessoais desnecessários, documentos internos restritos ou informações confidenciais. Quando necessário, registrar apenas “documento enviado”, “contato institucional realizado” ou referência interna segura.

---

### Seção: Princípios → Alteração: substituir “30+ dias” por política flexível de revalidação  
→ Justificativa: Alguns programas mudam semanalmente, outros anualmente. Recomendo manter 30 dias como padrão, mas permitir frequência menor ou maior.

**Sugestão:**

> Toda oportunidade deve ter `Última atualização` e, quando aplicável, `Próxima verificação`. Por padrão, revisar após 30 dias; para programas instáveis ou promocionais, revisar em 7 ou 15 dias; para programas anuais, revisar próximo ao ciclo de renovação.

---

### Seção: Estrutura de Fichas → Alteração: padronizar campos obrigatórios comuns  
→ Justificativa: As três fichas têm campos parecidos, mas não totalmente consistentes. Recomendo campos comuns mínimos para todas: identificador, status, última verificação, fontes, responsável pela atualização e histórico.

**Campos comuns sugeridos para todas as fichas:**

```markdown
| **ID interno** | provedor/google-cloud ou modelo/gemini-1.5-pro ou oportunidade/google-ai-credits-2025 |
| **Status do registro** | Ativo / Verificar / Arquivado |
| **Última verificação** | YYYY-MM-DD |
| **Próxima verificação** | YYYY-MM-DD ou Desconhecido (verificar) |
| **Fontes principais** | URLs com data de acesso |
```

---

### Seção: Estrutura de Fichas → Alteração: diferenciar claramente “provedor”, “modelo”, “programa” e “oportunidade”  
→ Justificativa: Hoje há possível confusão entre ficha de provedor, ficha de modelo e ficha de oportunidade. Por exemplo, “Google AI Credits” é programa/oportunidade, não provedor nem modelo. “Gemini 1.5 Pro” é modelo, não oportunidade. “Google Cloud” é provedor.

**Sugestão de definição no AGENTS.md:**

```markdown
## Entidades do repositório

- **Provedor**: organização, plataforma ou serviço que oferece acesso a modelos ou infraestrutura de IA. Ex.: OpenAI, Anthropic, Google Cloud, Azure AI Foundry, Hugging Face.
- **Modelo**: sistema/modelo específico ou família versionada acessível por API, plataforma ou download. Ex.: GPT-4o, Claude 3.5 Sonnet, Gemini 1.5 Pro, Llama 3.1.
- **Programa**: iniciativa recorrente ou institucional de acesso, crédito, desconto ou apoio. Ex.: Google Cloud Research Credits, OpenAI Researcher Access Program.
- **Oportunidade**: instância concreta e acompanhável de acesso, chamada, edital, oferta ou solicitação possível, normalmente vinculada a um programa, ciclo ou prazo. Ex.: Google Cloud Research Credits 2025 para pesquisadores.
- **Fonte**: documento, página, notícia, anúncio ou evidência usada para sustentar os dados.
```

Mesmo sem criar uma quarta ficha obrigatória de “programa”, essa definição reduz confusão. Uma solução leve é tratar “programa” como campo dentro da ficha de oportunidade.

---

### Seção: Ficha de Provedor → Alteração: adicionar campos sobre acesso, termos e cobertura  
→ Justificativa: Para decisão institucional, não basta saber se existe tier gratuito. É importante saber regiões, meios de acesso, restrições, termos de uso e disponibilidade para instituições brasileiras.

**Adicionar à tabela do Provedor:**

```markdown
| **ID interno** | provedor/nome-provedor |
| **Nome legal / marca** | Nome oficial, se diferente |
| **URL de pricing** | https://... |
| **URL de documentação/API** | https://... |
| **Regiões atendidas** | Global / EUA / UE / Brasil / Desconhecido (verificar) |
| **Elegibilidade Brasil** | Sim / Não / Desconhecido (verificar) |
| **Moeda de cobrança** | USD / BRL / EUR / Desconhecido |
| **Meios de acesso** | API / Console web / Cloud marketplace / Open source / Outro |
| **Termos de uso relevantes** | Link e observações |
| **Política de uso de dados** | Treinamento com dados do usuário? retenção? Desconhecido (verificar) |
| **Status do provedor** | Ativo / Indisponível / Verificar / Arquivado |
| **Última verificação** | YYYY-MM-DD |
| **Próxima verificação** | YYYY-MM-DD |
```

---

### Seção: Ficha de Provedor → Alteração: transformar “Programas de acesso” em seção mais estruturada  
→ Justificativa: Programas mudam de nome, condições e ciclo. A ficha do provedor deve apontar para oportunidades/programas, não tentar conter todo o histórico.

**Sugestão:**

```markdown
## Programas e oportunidades relacionados

| Programa/Oportunidade | Tipo | Ciclo/versão | Status | Link interno |
|-----------------------|------|--------------|--------|--------------|
| Google Cloud Research Credits | Créditos de pesquisa | 2025 | Ativo | ../oportunidades/... |
```

---

### Seção: Ficha de Modelo → Alteração: adicionar campos de identificador de API e disponibilidade  
→ Justificativa: Modelos podem ter nomes comerciais, nomes de API, snapshots e disponibilidade diferente por provedor. Ex.: mesmo modelo disponível em OpenAI e Azure, com nomes e preços distintos.

**Adicionar campos:**

```markdown
| **ID interno** | modelo/nome-modelo |
| **Nome de API / identificador técnico** | ex.: gpt-4o-mini, claude-3-5-sonnet-20241022 |
| **Provedor original** | Organização que desenvolve o modelo |
| **Provedores de acesso** | Plataformas que oferecem o modelo |
| **Modalidades suportadas** | Texto / Imagem / Áudio / Vídeo / Embeddings / Tool use |
| **Licença** | Proprietária / Open weights / Open source / Desconhecido |
| **Disponibilidade** | Geral / Preview / Beta / Restrita / Descontinuada |
| **Data de lançamento** | YYYY-MM-DD ou Desconhecido |
| **Data de descontinuação** | YYYY-MM-DD ou Não aplicável |
| **Última verificação** | YYYY-MM-DD |
```

---

### Seção: Ficha de Modelo → Alteração: evitar campo único “Treinamento até” como obrigatório  
→ Justificativa: Muitos provedores não divulgam data de corte de treinamento. Torná-la obrigatória induz agentes a inventarem ou inferirem.

**Sugestão:**

Trocar:

```markdown
| **Treinamento até** | Mês/ano dos dados de treinamento |
```

Por:

```markdown
| **Dados de treinamento / conhecimento até** | Data informada oficialmente ou Desconhecido (verificar) |
```

---

### Seção: Ficha de Modelo → Alteração: separar preço oficial por provedor  
→ Justificativa: O mesmo modelo pode ter preços diferentes por API, região ou plataforma. O campo único “Preço input/output” pode induzir erro.

**Sugestão:**

Manter preço geral apenas se houver um provedor único. Caso contrário, usar tabela:

```markdown
## Preços por provedor

| Provedor | API/plataforma | Input/1M tokens | Output/1M tokens | Moeda | Data da fonte | Fonte |
|----------|----------------|-----------------|------------------|-------|---------------|-------|
| ... | ... | ... | ... | ... | ... | ... |
```

---

### Seção: Ficha de Oportunidade → Alteração: adicionar campos essenciais de elegibilidade, acionabilidade e ciclo  
→ Justificativa: A ficha de oportunidade é o núcleo operacional. Ela precisa informar se a oportunidade pode ser solicitada pela equipe/instituição e qual ciclo/versão está sendo acompanhado.

**Adicionar campos:**

```markdown
| **ID interno** | oportunidade/provedor-programa-ciclo |
| **Programa relacionado** | Nome do programa, se houver |
| **Ciclo/versão do programa** | 2025 / Spring 2025 / v2 / Contínuo |
| **Substitui** | Link para oportunidade/programa anterior, se houver |
| **Substituído por** | Link para nova oportunidade/programa, se houver |
| **Público-alvo** | Pesquisadores / estudantes / startups / instituições / open source / outro |
| **Elegibilidade para UFBA/Brasil** | Sim / Não / Desconhecido (verificar) |
| **URL de candidatura/solicitação** | https://... |
| **Janela de candidatura** | Data inicial e final, ou Contínuo |
| **Validade do benefício** | Ex.: créditos válidos por 12 meses |
| **Contrapartidas exigidas** | Relatório, publicação, caso de uso, créditos, divulgação etc. |
| **Restrições de uso** | Pesquisa apenas, não comercial, limite geográfico, limite por instituição etc. |
| **Acionabilidade** | Acionável / Informacional / Aguardar abertura / Não acionável |
| **Prioridade** | Alta / Média / Baixa |
| **Próximo passo** | Ação objetiva e responsável |
| **Próxima verificação** | YYYY-MM-DD |
| **Status do programa** | Ativo / Pausado / Encerrado / Substituído / Desconhecido |
| **Status da prospecção** | Identificada / Em análise / Formulário iniciado / Submetida / Aguardando resposta / Convertida / Recusada / Expirada / Verificar |
```

---

### Seção: Ficha de Oportunidade → Alteração: separar “Status do programa” e “Status da prospecção”  
→ Justificativa: Um programa pode estar ativo, mas a solicitação interna estar aguardando resposta. Ou o programa pode ter sido encerrado, mas a oportunidade ainda ser referência histórica. Um único campo “Status” mistura essas dimensões.

**Sugestão:**

Substituir:

```markdown
| **Status** | 🔍 Identificada / ... |
```

Por:

```markdown
| **Status do programa** | Ativo / Pausado / Encerrado / Substituído / Desconhecido |
| **Status da prospecção** | 🔍 Identificada / 📋 Em análise / 📝 Formulário iniciado / 📤 Submetida / ⏳ Aguardando resposta / ✅ Convertida / ❌ Recusada / ⏰ Expirada / 🔁 Verificar |
```

---

### Seção: Ficha de Oportunidade → Alteração: corrigir “Chronologia” para “Cronologia”  
→ Justificativa: Corrige erro ortográfico e mantém português brasileiro.

**Alterar:**

```markdown
## Chronologia
```

Para:

```markdown
## Cronologia
```

---

### Seção: Workflow de Prospecção → Alteração: corrigir erros de digitação  
→ Justificativa: Há pequenos erros que podem atrapalhar clareza e agentes automatizados.

**Correções:**

- “Quando um agente encontro” → “Quando um agente encontrar”
- “oprotonidade” → “oportunidade”
- “Chronologia” → “Cronologia”

---

### Seção: Workflow de Prospecção → Alteração: adicionar etapa de triagem/deduplicação antes da criação de ficha  
→ Justificativa: A regra de não duplicar já existe, mas o workflow cria ficha muito cedo. Melhor incluir busca ativa por duplicatas usando nome do programa, provedor, URL, modelo e aliases.

**Adicionar passo antes de criar ficha:**

> Verificar duplicidade por nome oficial, nomes anteriores, aliases, URL oficial, provedor, programa, modelo e ciclo. Se já houver ficha, atualizar a existente em vez de criar nova.

---

### Seção: Workflow de Prospecção → Alteração: adicionar etapa de avaliação de confiabilidade da fonte  
→ Justificativa: Agentes precisam decidir se uma notícia basta para criar uma oportunidade acionável ou apenas uma fonte informacional.

**Adicionar:**

> Classificar a fonte como `oficial`, `secundária confiável`, `notícia de terceiro`, `agregador` ou `rumor/rede social`. Oportunidades acionáveis devem preferencialmente ter fonte oficial.

---

### Seção: Workflow de Prospecção → Alteração: adicionar etapa de atualização da matriz consolidada  
→ Justificativa: O usuário solicitou considerar uma matriz provedores vs. modelos. Essa matriz é útil para visão executiva e para evitar dispersão.

**Adicionar ao workflow:**

> Após criar ou atualizar ficha de provedor/modelo/oportunidade, revisar a matriz consolidada em `dados/matrizes/provedores-modelos.md`.

---

### Seção: Workflow de Prospecção → Alteração: adicionar etapa de revisão humana para oportunidades de alta prioridade  
→ Justificativa: Antes de submeter solicitações institucionais ou registrar dados sensíveis, deve haver validação humana.

**Adicionar:**

> Oportunidades classificadas como Alta prioridade ou que exijam submissão institucional devem ser marcadas para revisão humana antes de envio de formulário ou contato externo.

---

### Seção: Processamento de Notícias → Alteração: exigir saída estruturada em blocos  
→ Justificativa: O prompt mestre fica mais útil em pipelines de IA se a saída for previsível.

**Sugestão de blocos:**

```markdown
1. Resumo executivo
2. Fatos extraídos com fonte
3. Lacunas e campos desconhecidos
4. Avaliação de confiabilidade
5. Decisão: criar nova ficha / atualizar ficha existente / apenas registrar fonte
6. Fichas ou patches sugeridos
7. Próximos passos
```

---

### Seção: Formato de Fontes → Alteração: adicionar campos de arquivamento e confiabilidade  
→ Justificativa: URLs mudam ou desaparecem. Para arquivística e preservação digital, é importante registrar data de acesso, cópia arquivada e nível de confiabilidade.

**Adicionar campos:**

```markdown
| **Tipo de fonte** | Oficial / Documentação / Pricing / Blog oficial / Notícia / Agregador / Rede social |
| **Confiabilidade** | Alta / Média / Baixa |
| **URL arquivada** | Internet Archive, Perma.cc ou outro, se houver |
| **Idioma da fonte** | PT / EN / Outro |
| **Autor/organização publicadora** | Nome |
| **Licença/uso do conteúdo** | Se informado |
```

---

### Seção: Commits → Alteração: padronizar verbos e tipos  
→ Justificativa: O formato mistura `feat`, `update`, `fix`, `docs`, `data`. Recomendo manter, mas definir uso.

**Sugestão:**

```markdown
- `feat:` nova ficha ou nova seção estrutural
- `update:` atualização de status, preços, requisitos ou fonte
- `fix:` correção factual, ortográfica ou de link
- `docs:` alteração em diretrizes, templates ou documentação
- `data:` atualização de matriz, vínculo ou metadado estruturado
- `archive:` marcação de programa encerrado, expirado ou substituído
```

---

### Seção: Anti-padrões → Alteração: ampliar casos comuns de erro  
→ Justificativa: A seção atual cobre o essencial, mas faltam erros frequentes de agentes de IA: confundir programa com modelo, assumir disponibilidade global, converter moeda sem data, usar fonte secundária como oficial etc.

**Adicionar anti-padrões:**

```markdown
- ❌ Confundir provedor, modelo, programa e oportunidade.
- ❌ Tratar notícia de terceiro como confirmação oficial de preço ou elegibilidade.
- ❌ Assumir que uma oferta global é válida para Brasil/UFBA sem fonte.
- ❌ Converter moedas sem registrar taxa, data e fonte.
- ❌ Inferir tamanho de contexto, preço ou versão a partir do nome do modelo.
- ❌ Atualizar preço sem preservar preço anterior no histórico.
- ❌ Marcar oportunidade como acionável sem URL de candidatura ou instrução clara.
- ❌ Registrar contatos pessoais, credenciais, chaves de API ou dados sensíveis.
- ❌ Criar nova ficha para programa recorrente sem verificar ciclos anteriores.
- ❌ Apagar informação histórica quando programa for renomeado ou substituído.
```

---

### Seção: Programas que mudam frequentemente → Alteração: adicionar seção específica  
→ Justificativa: Programas como Google Cloud Research Credits, Google AI for Education, Microsoft for Startups, AWS Activate e similares mudam nomes, valores, critérios e páginas. Agentes precisam saber como versionar e atualizar sem perder histórico.

**Adicionar seção:**

```markdown
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
```

---

### Seção: Matriz de provedores vs. modelos → Alteração: criar visão consolidada  
→ Justificativa: Uma matriz ajuda agentes e humanos a ver rapidamente quais provedores oferecem quais modelos, se há acesso gratuito, preço e oportunidades relacionadas.

**Adicionar ao AGENTS.md:**

```markdown
## Matriz consolidada de provedores vs. modelos

Manter arquivo:

`dados/matrizes/provedores-modelos.md`

Campos recomendados:

| Provedor | Modelo/Família | Tipo | API/Plataforma | Acesso gratuito | Programa/Oportunidade relacionada | Preço verificado | Status | Última verificação | Fontes |
|----------|----------------|------|----------------|-----------------|----------------------------------|------------------|--------|--------------------|--------|
```

---

### Seção: Versionamento de programas → Alteração: adicionar política explícita  
→ Justificativa: Programas renovados anualmente exigem distinção entre continuidade institucional e condições específicas daquele ciclo.

**Adicionar orientação:**

> Para programas recorrentes, manter uma relação entre ciclos. Ex.: `google-cloud-research-credits-2024`, `google-cloud-research-credits-2025`. Cada ciclo pode ter ficha própria se houver mudanças de prazo, elegibilidade, valor ou formulário. Usar campos `Substitui`, `Substituído por` e `Ciclo/versão`.

---

### Seção: Prompt mestre → Alteração: tornar mais adequado a pipelines de IA  
→ Justificativa: O prompt atual é bom, mas genérico. Para pipelines, é melhor ter entrada, regras, etapas, critérios de decisão e saída em formato previsível.

**Melhorias recomendadas:**

- Incluir “entrada esperada”.
- Incluir “não navegar na web se não tiver ferramenta”.
- Incluir “se não houver fonte oficial, marcar como pendente”.
- Incluir “decisão operacional”: criar ficha, atualizar ficha ou só registrar fonte.
- Exigir tabela “fatos extraídos”.
- Exigir tabela “lacunas”.
- Exigir “patches sugeridos” em vez de presumir escrita direta no repositório.
- Exigir links internos relativos.

---

### Seção: Diretrizes para priorização → Alteração: adicionar critérios de alinhamento institucional e esforço  
→ Justificativa: Uma oportunidade de US$ 10 mil pode ser baixa prioridade se exigir muita burocracia ou não cobrir modelos úteis. Priorização deve considerar valor, esforço, prazo, aderência e risco.

**Adicionar critérios:**

```markdown
| **Esforço de solicitação** | Baixo | Médio | Alto |
| **Aderência à pesquisa/ensino** | Alta | Média | Baixa |
| **Risco/contrapartida** | Baixo | Médio | Alto |
| **Elegibilidade Brasil/UFBA** | Confirmada | Provável | Incerta/negativa |
```

---

### Seção: Diretrizes para cruzamento de dados → Alteração: registrar conflitos em vez de escolher silenciosamente  
→ Justificativa: Mesmo que fonte oficial tenha prioridade, divergências úteis devem ser preservadas.

**Sugestão:**

> Quando houver conflito, registrar o dado oficial como valor principal e mover divergências para `## Divergências entre fontes`, com URL, data e trecho.

---

### Seção: Diretrizes para avaliação de acionabilidade → Alteração: separar acionabilidade da prioridade  
→ Justificativa: Uma oportunidade pode ser acionável, mas baixa prioridade; ou alta prioridade, mas ainda não acionável.

**Adicionar:**

> `Acionabilidade` indica se há ação possível agora. `Prioridade` indica relevância estratégica. Não usar uma como sinônimo da outra.

---

# Versão refinada completa — AGENTS.md

```markdown
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
3. **Separação entre fato, inferência e decisão** — Fatos devem estar apoiados em fonte. Inferências devem ser marcadas. Decisões internas, como prioridade, responsável ou próximo passo, devem ser identificadas como decisão da equipe/repositório.
4. **Hierarquia de fontes** — Em caso de conflito, priorizar: página oficial do programa/provedor; documentação oficial/API/pricing; blog oficial; comunicado institucional; notícia de terceiro; redes sociais; agregadores.
5. **Cruzamento obrigatório** — Antes de criar uma ficha, verifique se já existe entrada para o mesmo provedor, modelo, programa ou oportunidade. Atualize em vez de duplicar.
6. **Status sempre atual** — Toda oportunidade deve ter `Última atualização` e, quando aplicável, `Próxima verificação`. Por padrão, revisar após 30 dias; para programas instáveis/promocionais, revisar em 7 ou 15 dias; para programas anuais, revisar próximo ao ciclo de renovação.
7. **Sem alucinação de preços** — Nunca invente preços, limites de tokens, datas ou condições de programas. Se não encontrou, escreva `Desconhecido (verificar)`.
8. **Não registrar segredos ou dados sensíveis** — Nunca incluir chaves de API, tokens, senhas, dados pessoais desnecessários, documentos internos restritos ou informações confidenciais.
9. **Idioma** — Fichas em português brasileiro. Nomes próprios, termos técnicos e nomes de provedores/modelos devem ser mantidos no original quando apropriado.

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
| **Tipo** | Créditos gratuitos / Desconto acadêmico / Programa de pesquisa / Trial / Parceria / etc. |
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

Quando um agente encontrar uma oportunidade em notícia, anúncio, site de provedor ou documentação:

1. Registrar a fonte inicial.
2. Identificar provedor, modelo(s), programa, tipo de oferta, público-alvo, requisitos, benefícios, valores e prazos.
3. Classificar a fonte como `oficial`, `documentação/pricing`, `blog oficial`, `notícia de terceiro`, `agregador`, `rede social` ou `rumor`.
4. Verificar se há página oficial do programa/provedor.
5. Se não houver fonte oficial, marcar a oportunidade como `Informacional` ou `Desconhecido (verificar)`, conforme o caso.

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

- Marcar `Acionabilidade`: Acionável / Informacional / Aguardar abertura / Não acionável.
- Marcar `Prioridade`: Alta / Média / Baixa.
- Indicar próximo passo objetivo.
- Oportunidades de alta prioridade ou que exijam submissão institucional devem passar por revisão humana antes de contato externo.

### 6. Solicitar ou encaminhar

- Se a oportunidade é acionável, registrar quem pode solicitar.
- Marcar status como `📋 Em análise`, `📝 Formulário iniciado`, `📤 Submetida` ou `⏳ Aguardando resposta`.
- Documentar cada passo do processo na `Cronologia`.
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
2. **Verificar** — Cruzar com site oficial do provedor, página de pricing, documentação, página educacional ou programa de pesquisa.
3. **Classificar** — Determinar tipo de oportunidade: créditos, desconto, pesquisa, parceria, trial, tier gratuito, startup, promoção etc.
4. **Decidir** — Criar nova ficha, atualizar ficha existente ou apenas registrar fonte.
5. **Criar/Vincular** — Criar ou atualizar ficha de oportunidade e vincular com provedor/modelo.
6. **Registrar fonte** — Arquivar a notícia original em `fontes/`.
7. **Avaliar acionabilidade** — Indicar se há próximos passos possíveis e quem pode tomar.
8. **Atualizar matriz** — Atualizar `dados/matrizes/provedores-modelos.md`, quando aplicável.

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

- Provedor X oferece Y créditos para Z.
- Modelo A disponível gratuitamente para pesquisadores.
- ...

## Lacunas

- Campo não encontrado: ...
- Necessário verificar: ...

## Histórico

- YYYY-MM-DD: Fonte registrada por [agente/pessoa]
```

## Matriz consolidada de provedores vs. modelos

Manter o arquivo:

`dados/matrizes/provedores-modelos.md`

Formato recomendado:

```markdown
# Matriz consolidada de provedores vs. modelos

| Provedor | Modelo/Família | Tipo | API/Plataforma | Acesso gratuito | Programa/Oportunidade relacionada | Preço verificado | Status | Última verificação | Fontes |
|----------|----------------|------|----------------|-----------------|----------------------------------|------------------|--------|--------------------|--------|
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

- `feat:` nova ficha ou nova seção estrutural.
- `update:` atualização de status, preços, requisitos ou fonte.
- `fix:` correção factual, ortográfica ou de link.
- `docs:` alteração em diretrizes, templates ou documentação.
- `data:` atualização de matriz, vínculo ou metadado estruturado.
- `archive:` marcação de programa encerrado, expirado ou substituído.

Exemplos:

- `feat: adiciona oportunidade Google Cloud Research Credits 2025`
- `update: atualiza status da oportunidade OpenAI para Aguardando resposta`
- `fix: corrige preço do GPT-4o mini conforme pricing oficial`
- `docs: adiciona diretrizes para programas recorrentes`
- `data: atualiza matriz provedores-modelos com Anthropic Claude`
- `archive: marca Google AI Credits 2024 como substituído`

## Anti-padrões (NÃO fazer)

- ❌ Inventar preços, limites, datas ou condições não encontrados em fontes.
- ❌ Criar fichas duplicadas sem verificar nomes, aliases, URLs e ciclos anteriores.
- ❌ Deixar campos obrigatórios em branco sem `Desconhecido (verificar)`.
- ❌ Registrar oportunidades sem fonte ou URL.
- ❌ Copiar texto diretamente de fontes sem reformular; usar paráfrase e citações diretas curtas entre aspas.
- ❌ Remover histórico de alterações de fichas existentes.
- ❌ Confundir provedor, modelo, programa e oportunidade.
- ❌ Tratar notícia de terceiro como confirmação oficial de preço ou elegibilidade.
- ❌ Assumir que uma oferta global é válida para Brasil/UFBA sem fonte.
- ❌ Converter moedas sem registrar taxa, data e fonte.
- ❌ Inferir tamanho de contexto, preço ou versão a partir do nome do modelo.
- ❌ Atualizar preço sem preservar preço anterior no histórico.
- ❌ Marcar oportunidade como acionável sem URL de candidatura ou instrução clara.
- ❌ Registrar contatos pessoais, credenciais, chaves de API, tokens ou dados sensíveis.
- ❌ Criar nova ficha para programa recorrente sem verificar ciclos anteriores.
- ❌ Apagar informação histórica quando programa for renomeado, encerrado ou substituído.
```

---

# Versão refinada completa — diretrizes-prospeccao.md

```markdown
# Diretrizes/prompt para prospecção de provedores e tokens

Este documento serve como prompt/diretriz para agentes de IA que processem notícias, anúncios e informações sobre acesso a provedores, programas, APIs e modelos de IA, com o objetivo de extrair dados estruturados e alimentar as fichas deste repositório.

O documento principal de operação do repositório é o `AGENTS.md`. Em caso de conflito, seguir o `AGENTS.md`.

---

## Prompt mestre para processamento de notícias

```text
Você é um analista de prospecção de oportunidades de IA para pesquisa, ensino, desenvolvimento e inovação.

Sua tarefa é processar notícias, anúncios, páginas oficiais, documentação, páginas de pricing e outras fontes sobre provedores, programas, APIs e modelos de IA para identificar oportunidades de acesso gratuito, subsidiado, acadêmico ou institucional.

ENTRADA:
- Texto da fonte, URL, metadados ou notícia fornecida pelo usuário/pipeline.
- Se houver acesso a ferramentas de navegação, use-as apenas para verificar fontes oficiais.
- Se não houver acesso à web, não finja verificação externa. Marque como "Pendente de verificação".

REGRAS ANTI-ALUCINAÇÃO:
1. Extraia APENAS fatos explícitos na fonte.
2. Nunca invente preços, limites, datas, requisitos, elegibilidade, tamanho de contexto ou condições.
3. Para cada fato relevante, registre URL, data de acesso e trecho relevante.
4. Se um campo obrigatório estiver ausente, escreva "Desconhecido (verificar)".
5. Separe fatos, inferências e decisões internas.
6. Marque rumores como "[não confirmado]"; estimativas como "[estimativa]"; inferências como "[inferência]".
7. Fonte oficial prevalece sobre notícia de terceiro. Se houver conflito, registre a divergência.
8. Não assuma que uma oportunidade global é válida para Brasil/UFBA sem fonte.
9. Não converta moedas sem registrar taxa, data e fonte.
10. Não registre dados sensíveis, chaves de API, tokens, senhas ou documentos confidenciais.
11. Não confunda provedor, modelo, programa e oportunidade.

DEFINIÇÕES:
- Provedor: organização, plataforma ou serviço que oferece acesso a modelos ou infraestrutura de IA.
- Modelo: sistema/modelo específico ou família versionada.
- Programa: iniciativa recorrente ou institucional de acesso, crédito, desconto ou apoio.
- Oportunidade: instância concreta e acompanhável de acesso, chamada, edital, oferta ou solicitação possível.
- Fonte: documento, página, notícia ou evidência usada para sustentar os dados.

PASSOS:
a) IDENTIFICAR — Quais provedores, modelos, programas e oportunidades são mencionados?
b) CLASSIFICAR FONTE — A fonte é oficial, documentação/pricing, blog oficial, notícia, agregador, rede social ou rumor?
c) EXTRAIR — Dados concretos: requisitos, benefícios, valores, prazos, URLs, público-alvo e restrições.
d) VERIFICAR — Procurar ou indicar necessidade de cruzamento com site oficial, pricing, documentação ou página do programa.
e) DEDUPLICAR — Verificar se já existe ficha para o mesmo provedor, modelo, programa, oportunidade ou ciclo.
f) DECIDIR — Indicar uma das opções: criar nova ficha, atualizar ficha existente ou apenas registrar fonte.
g) VINCULAR — Conectar oportunidade com provedor, modelo, programa e fonte.
h) AVALIAR ACIONABILIDADE — A oportunidade pode ser solicitada agora? Quem pode solicitar? Qual o próximo passo?
i) PRIORIZAR — Classificar como Alta, Média ou Baixa prioridade, justificando.
j) VERSIONAR — Se o programa for recorrente ou mudou de nome/condição, registrar ciclo, substitui/substituído por e histórico.

SAÍDA ESPERADA:
1. Resumo executivo em 1-3 parágrafos.
2. Tabela de fatos extraídos, cada um com fonte e trecho.
3. Lacunas e campos "Desconhecido (verificar)".
4. Avaliação de confiabilidade da fonte.
5. Decisão operacional: criar ficha / atualizar ficha / apenas registrar fonte.
6. Ficha de Fonte em markdown.
7. Ficha de Oportunidade em markdown, se aplicável.
8. Ficha de Provedor em markdown, se não existir.
9. Ficha de Modelo em markdown, se não existir.
10. Atualização sugerida para matriz provedores-modelos, se aplicável.
11. Próximos passos.
```

---

## Estrutura recomendada da resposta do agente

Ao processar uma fonte, a resposta do agente deve seguir esta estrutura:

```markdown
## 1. Resumo executivo

...

## 2. Fatos extraídos

| Fato | Valor | Fonte | Trecho relevante | Confiança |
|------|-------|-------|------------------|-----------|
| ... | ... | ... | "..." | Alta/Média/Baixa |

## 3. Lacunas e verificações pendentes

| Campo | Situação | Ação sugerida |
|-------|----------|---------------|
| ... | Desconhecido (verificar) | Verificar página oficial |

## 4. Avaliação da fonte

- Tipo de fonte:
- Confiabilidade:
- Fonte oficial disponível? Sim/Não/Desconhecido
- Observações:

## 5. Decisão operacional

- [ ] Criar nova ficha de oportunidade
- [ ] Atualizar ficha existente
- [ ] Criar ficha de provedor
- [ ] Criar ficha de modelo
- [ ] Apenas registrar fonte
- Justificativa:

## 6. Fichas ou patches sugeridos

### Fonte

...

### Oportunidade

...

### Provedor, se necessário

...

### Modelo, se necessário

...

### Matriz provedores-modelos, se necessário

...

## 7. Próximos passos

- ...
```

---

## Diretrizes para cruzamento de dados

Quando houver múltiplas fontes sobre o mesmo provedor, modelo, programa ou oportunidade:

1. **Preço oficial tem prioridade** — Sempre preferir a página de pricing do provedor sobre notícias de terceiros.
2. **Documentação oficial prevalece** — Para limites técnicos, disponibilidade de modelos e nomes de API, priorizar documentação oficial.
3. **Data mais recente importa, mas não apaga histórico** — Se houver mudança, registrar nova condição e preservar condição anterior no histórico.
4. **Conflitos devem ser documentados** — Registrar divergências em seção `## Divergências entre fontes`, com URLs, datas e trechos.
5. **Dados não confirmados ficam em seção separada** — Criar seção `## Dados não confirmados` quando houver rumores, vazamentos ou informações não oficiais.
6. **Programas encerrados ficam no histórico** — Não remover, mas marcar como `Expirada`, `Encerrada` ou `Substituída`, com a data e fonte.
7. **Elegibilidade local não deve ser presumida** — Só marcar Brasil/UFBA como elegível se houver evidência explícita ou confirmação institucional.

---

## Diretrizes para avaliação de acionabilidade

`Acionabilidade` indica se há ação possível agora. `Prioridade` indica relevância estratégica. Não usar uma como sinônimo da outra.

Uma oportunidade é **acionável** quando:

- Há URL direta para solicitação, formulário ou instrução oficial clara.
- Os requisitos são claros e aparentemente atingíveis pela equipe/instituição.
- O prazo está dentro do período viável.
- Os benefícios são concretos e mensuráveis.
- Não há impedimento conhecido para Brasil/UFBA.

Uma oportunidade é **informacional** quando:

- Não há como solicitar no momento.
- A informação vem de notícia, rumor ou anúncio futuro sem formulário.
- Os requisitos são vagos ou proibitivos.
- Já expirou, mas serve como referência para programas recorrentes.
- Falta confirmação oficial suficiente.

Valores recomendados para o campo:

- `Acionável`
- `Informacional`
- `Aguardar abertura`
- `Não acionável`

---

## Diretrizes para priorização

| Critério | Alta | Média | Baixa |
|----------|------|-------|-------|
| **Valor estimado** | >US$ 5.000/ano | US$ 500-5.000/ano | <US$ 500/ano |
| **Acessibilidade** | Sem requisitos especiais | Requisito institucional | Requisito complexo |
| **Prazo** | >90 dias | 30-90 dias | <30 dias ou expirando |
| **Cobertura de modelos** | Múltiplos modelos úteis | Modelos específicos úteis | Modelos pouco relevantes |
| **Esforço de solicitação** | Baixo | Médio | Alto |
| **Aderência à pesquisa/ensino** | Alta | Média | Baixa |
| **Risco/contrapartida** | Baixo | Médio | Alto |
| **Elegibilidade Brasil/UFBA** | Confirmada | Provável | Incerta ou negativa |

A prioridade final deve ser justificada em 1-3 frases.

---

## Diretrizes para programas que mudam frequentemente

Programas como créditos de cloud, programas de pesquisa, startups, educação e IA generativa podem mudar nome, valor, elegibilidade, formulário e periodicidade.

Ao lidar com esses casos:

1. Registrar o nome oficial atual.
2. Registrar nomes anteriores, se conhecidos.
3. Registrar `Ciclo/versão do programa`.
4. Preservar condições anteriores no histórico.
5. Usar `Substitui` e `Substituído por` quando houver nova ficha.
6. Não apagar oportunidades expiradas.
7. Se a mudança for substancial, criar nova ficha para o novo ciclo.
8. Se a mudança for menor, atualizar a ficha existente e registrar no histórico.
9. Definir `Próxima verificação` menor para programas instáveis: 7 ou 15 dias.
10. Para programas anuais, revisar próximo ao período histórico de abertura.

Exemplo de versionamento:

- `google-cloud-research-credits-2024`
- `google-cloud-research-credits-2025`

---

## Diretrizes para matriz de provedores vs. modelos

A matriz consolidada deve oferecer visão rápida sobre disponibilidade de modelos por provedor.

Arquivo recomendado:

`dados/matrizes/provedores-modelos.md`

Campos recomendados:

```markdown
| Provedor | Modelo/Família | Tipo | API/Plataforma | Acesso gratuito | Programa/Oportunidade relacionada | Preço verificado | Status | Última verificação | Fontes |
|----------|----------------|------|----------------|-----------------|----------------------------------|------------------|--------|--------------------|--------|
```

Atualizar a matriz quando:

- novo modelo for identificado;
- novo provedor oferecer modelo relevante;
- preço mudar;
- tier gratuito mudar;
- programa de créditos/desconto for criado, encerrado ou substituído;
- modelo for descontinuado.

---

## Diretrizes para versionamento de programas

Criar nova ficha de oportunidade quando ocorrer pelo menos uma destas situações:

- novo ciclo anual ou semestral;
- novo edital/chamada;
- mudança significativa de valor;
- mudança significativa de elegibilidade;
- mudança de formulário ou processo;
- novo prazo de candidatura;
- renomeação oficial com alteração de escopo;
- substituição explícita por novo programa.

Atualizar a ficha existente quando ocorrer:

- correção menor de texto;
- atualização de URL sem mudança de escopo;
- adição de FAQ;
- pequena clarificação de requisito já existente.

Sempre registrar no histórico:

```markdown
- YYYY-MM-DD: Programa alterado de X para Y conforme [fonte]. Condição anterior preservada no histórico.
```

---

## Anti-padrões específicos para agentes de IA

Não fazer:

- ❌ Criar oportunidade a partir de rumor sem marcar como não confirmado.
- ❌ Inferir preço a partir de nome do plano.
- ❌ Inferir elegibilidade para Brasil com base em termos como “global” sem confirmação.
- ❌ Misturar preço de um provedor com modelo oferecido por outro.
- ❌ Tratar modelo open weights como automaticamente gratuito para API hospedada.
- ❌ Confundir créditos de cloud com créditos específicos para API de IA.
- ❌ Confundir programa de startup com programa acadêmico.
- ❌ Criar nova ficha para cada notícia sobre o mesmo programa/ciclo.
- ❌ Apagar ciclos anteriores de programas recorrentes.
- ❌ Usar valores convertidos para BRL sem taxa/data/fonte.
- ❌ Registrar dados sensíveis de submissão, credenciais ou chaves.

---

## Checklist final antes de salvar ou propor commit

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
```

---