# miniguia-estudos-notebooklm
projeto notebooklm

# 🛡️ Caderno Temático NotebookLM: Prevenção a Fraudes Digitais e Análise de Risco

> **Status do Projeto:** Concluído 🚀  
> **Ferramentas:** Google NotebookLM, GitHub, Markdown  
> **Foco:** Aprendizagem Ativa, Curadoria Técnica, Engenharia de Prompts e Prevenção a Fraudes

---

## 🎯 1. Contexto e Objetivos

### 📌 Contexto
Com o avanço dos serviços financeiros digitais e plataformas transacionais, os vetores de ataque tornaram-se cada vez mais sofisticados — desde manipulação e falsificação documental até invasão de contas (*Account Takeover - ATO*) e ataques de injeção de imagens/biometria. 

Este projeto explora o **Google NotebookLM** como uma ferramenta de aprendizagem ativa e síntese de conhecimento, permitindo consolidar os pilares da documentoscopia digital, análise comportamental, validação cadastral e arquitetura de mitigação de riscos sem alucinação de dados.

### 🎯 Objetivos de Estudo
* **Compreender** as principais tipologias de fraudes documentais e biométricas em fluxos de onboarding digital.
* **Mapear** o pipeline de validação de identidade (OCR, Face Match, Liveness Detection e checagem em bureaus).
* **Estruturar** regras de negócio e tomada de decisão (*score de risco*, aprovação automática, mesa manual e recusa).
* **Documentar** o processo de engenharia de prompts técnicos para extração de insights rigorosos a partir de fontes especializadas.

---

## 📚 2. Curadoria de Fontes

Para alimentar o caderno no NotebookLM, foram curadas 4 fontes abertas de referência técnica, acadêmica e setorial:

| # | Fonte / Título | Autor / Origem | Formato | Foco Temático |
|---|----------------|----------------|---------|---------------|
| 1 | *Guia de Boas Práticas para Identificação Digital e Prevenção a Fraudes* | FEBRABAN / Publicações Técnicas | PDF / Artigo | Normas, esteiras de onboarding e validação cadastral |
| 2 | *Fundamentos de Documentoscopia e Perícia Grafotécnica em Documentos Digitais* | Perícia Forense / Artigo Técnico | PDF | Análise de espécimes, fontes tipográficas, alinhamentos e adulterações |
| 3 | *Framework de Detecção de Fraudes e Gestão de Risco em Plataformas Digitais* | Open Source Security / OWASP | Web / Docs | Vetores de ataque, Account Takeover (ATO) e mitigação |
| 4 | *Biometria Facial e Ataques de Apresentação (Presentation Attack Detection - PAD)* | Padrão ISO/IEC 30107 / Artigos | Paper Técnico | Prova de vida (Liveness ativo e passivo), spoofing e deepfakes |

---

## ⚙️ 3. Engenharia de Prompts & "Cicatrizes" (Troubleshooting)

A utilização do NotebookLM exigiu iterações estratégicas para garantir respostas que refletissem o rigor de uma mesa de análise de risco e perícia documental.

### 🧪 Interações e Refinamento de Prompts

#### 🔹 Ciclo 1: Extração Geral vs. Análise de Vetores Específicos
* **Prompt Inicial:**
  > *"Quais são os tipos de fraudes em documentos digitais descritos nos textos?"*
* **Resultado Obtido:** Uma lista superficial citando apenas "falsificação de RG e CNH", sem detalhar anomalias estruturais.
* **Refinamento (Prompt Final):**
  > *"Atuando como um Especialista Sênior em Prevenção a Fraudes e Documentoscopia, categorize as adulterações documentais citadas nas fontes em: (a) Fraude Ideológica, (b) Fraude Material e (c) Montagem Digital. Para cada categoria, descreva 3 indícios visuais ou metadados que denunciam a anomalia em uma esteira de análise."*
* **Impacto da Mudança:** A resposta detalhou inconsistências tipográficas, desalinhamento de campos padrão, artefatos de compressão JPEG em fotos sobrepostas e incongruência na validação de dígitos verificadores.

---

#### 🔹 Ciclo 2: Tomada de Decisão em Regras de Risco
* **Prompt Inicial:**
  > *"Como funciona a esteira de onboarding?"*
* **Resultado Obtido:** Resumo linear e genérico do fluxo de cadastro.
* **Refinamento (Prompt Final):**
  > *"Com base nas fontes 1 e 3, construa um fluxo de tomada de decisão em formato de tabela Markdown, dividindo os cenários em: Aprovação Automática, Mesa de Análise Manual e Rejeição Imediata. Liste os gatilhos de risco e divergências documentais/biométricas correspondentes a cada ação."*
* **Impacto da Mudança:** Gerou uma matriz de risco operacional pronta para aplicação em arquitetura de sistemas antifraude.

---

### 🩹 Cicatrizes e Lições Aprendidas (Troubleshooting)
* **Desafio 1 (Confusão Conceitual entre Fraude Material e Ideológica):** O modelo inicialmente misturava documentos autênticos com dados falsos (ideológica) com documentos adulterados fisicamente ou digitalmente (material).
  * **Solução:** Adicionada a diretriz no prompt: *"Diferencie estritamente a autenticidade do suporte/mídia física da veracidade dos dados cadastrais perante bases oficiais."*
* **Desafio 2 (Generalização sobre Biometria Facial):** Ao tratar de Face Match, o modelo tratava "similaridade facial" como garantia absoluta de legitimidade, ignorando ataques de apresentação.
  * **Solução:** Prompt ancorado na Fonte 4 exigindo a dissociação obrigatória entre *Face Match score* (comparação facial) e *Liveness score* (prova de vida contra fotos estáticas, telas e máscaras).

---

## 📖 4. Miniguia de Estudo (Entrega Consolidada)

### 📌 Resumo Estruturado do Tema

                ESTEIRA DE PREVENÇÃO A FRAUDES NO ONBOARDING
                                     │
 ┌───────────────────────────────────┼───────────────────────────────────┐
 ▼                                   ▼                                   ▼
[Captura Documental]             [Biometria Facial]                 [Análise de Vínculos]

OCR dos dados                  - Face Match vs. Doc               - Checagem em Bureaus

Alinhamento tipográfico        - Liveness Detection (PAD)         - Histórico de Dispositivo

Consistência de segurança      - Detecção de Telas/Deepfake       - Validação de CPF/Receita
└───────────────────────────────────┬───────────────────────────────────┘
▼
[Motor de Regras & Risco]
┌──────────────────┼──────────────────┐
▼                  ▼                  ▼
[Aprovação]       [Mesa Manual]        [Recusa]
Score Baixo       Score Médio /       Score Alto /
Sem anomalias     Incongruência       Fraude Crítica


1. **Camada de Entrada (Captura & OCR):** Extração automatizada de dados e validação preliminar de integridade do documento enviado (CNH, RG, CIN).
2. **Camada de Documentoscopia & Perícia Digital:** Avaliação de espaçamentos, fontes padrão, microimpressões, marcas d'água, artefatos de edição em softwares gráficos e coerência de dados alfanuméricos.
3. **Camada de Biometria e Identidade:** Teste de prova de vida (ISO/IEC 30107) associado à comparação 1:1 entre a selfie e a foto do documento, evitando uso de fotos de terceiros ou geradas por IA.
4. **Camada de Decisão e Risco:** Cruzamento de variáveis comportamentais, geolocalização, *device fingerprinting* e reputação cadastral para mitigar riscos financeiros e regulatórios.

---

### 📚 Glossário de Termos-Chave

* **Liveness Detection (Prova de Vida):** Mecanismo de segurança que verifica se a amostra biométrica capturada provém de um ser humano vivo presente no momento da captura, combatendo ataques de apresentação (*spoofing*).
* **Documentoscopia Digital:** Ramo da perícia voltado à verificação de autenticidade documental em meio eletrônico, analisando fontes tipográficas, diagramação, padrões de segurança e metadados.
* **Account Takeover (ATO):** Modalidade de fraude onde um agente malicioso obtém acesso não autorizado à conta legítima de um usuário para realizar transações ilícitas.
* **Fraude Material:** Adulteração física ou digital na estrutura do documento (substituição de foto, alteração de dígitos, montagem gráfica).
* **Fraude Ideológica:** Documento formalmente autêntico e emitido pelo órgão oficial, mas contendo informações falsas fornecidas pelo emissor ou obtidas mediante falsidade ideológica.
* **Device Fingerprinting:** Técnica que coleta atributos do hardware, navegador e sistema operacional para criar uma identidade única do dispositivo utilizado na requisição.

---

### 🔁 Prompts Reutilizáveis (Para Revisão e Aprofundamento)


[PROMPT 1: SIMULAÇÃO DE MESA DE ANÁLISE]
"Atue como um analista de prevenção a fraudes sênior. Crie um caso prático com inconsistências documentais sutis (ex: data de nascimento vs. data de expedição da CNH, fonte tipográfica fora de padrão) e me guie em um exercício interativo de aprovação ou reprovação."

[PROMPT 2: ANÁLISE COMPARATIVA DE VETORES DE ATAQUE]
"Com base exclusivamente nas fontes do caderno, elabore um comparativo entre 'Ataques de Injeção de Câmera' e 'Apresentação Física de Telas/Fotos'. Apresente as medidas técnicas de contenção recomendadas para cada um."

[PROMPT 3: FLASHCARDS DE REVISÃO TÉCNICA]
"Gere 5 perguntas de revisão técnica no estilo flashcard (pergunta conceitual seguida de resposta fundamentada) cobrindo a diferença entre Liveness Ativo, Liveness Passivo e OCR em esteiras de cadastro."

🛠️ Tecnologias e Ferramentas Utilizadas
Google NotebookLM — Curadoria, ancoragem documental e síntese ativa de conhecimento.

GitHub & Markdown — Estruturação, versionamento e documentação do portfólio.

👤 Autor
Desenvolvido por Bruno Fernandes

GitHub: @brunokr7

LinkedIn: https://www.linkedin.com/in/bruno-fernandes-do-nascimento-53286b26a/
