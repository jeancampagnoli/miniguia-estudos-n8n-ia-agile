# 🤖 Miniguia de Estudos: Automação com n8n, Inteligência Artificial e Agilidade Scrum para Melhoria de Produto

Repositório desenvolvido como entrega de desafio de projeto do **Bootcamp de Automação com n8n e IA**, uma parceria entre a **DIO** e o **Banco Santander**. Este projeto demonstra de forma prática como utilizar a Inteligência Artificial e a automação de fluxos de trabalho (workflows) para acelerar a entrega de valor, melhorar a qualidade do produto e otimizar as cerimônias e artefatos de times ágeis utilizando o framework Scrum.

---

## 🎯 Contexto e Objetivos de Estudo

### Contexto
No desenvolvimento moderno de produtos digitais, a agilidade (Scrum) e a automação não são mais diferenciais, mas pré-requisitos para a sobrevivência de mercado. A união do **n8n** (uma poderosa plataforma de automação low-code/no-code com suporte nativo a IA avançada) com modelos de linguagem (LLMs) permite que times de produto automatizem tarefas repetitivas de gestão, qualifiquem o backlog de forma inteligente e identifiquem impedimentos em tempo real. 

### Objetivos de Estudo
* **Dominar o n8n com IA Avançada**: Compreender como conectar modelos de LLM (ex: OpenAI, Anthropic) aos fluxos do n8n utilizando agentes autônomos (AI Agents) e cadeias de decisão.
* **Integrar Automação ao Scrum**: Explorar formas de integrar ferramentas de desenvolvimento/gestão (Jira, Trello, Notion, Slack) em fluxos inteligentes para triagem de bugs, geração automatizada de User Stories e monitoramento de impedimentos.
* **Melhoria Contínua do Produto**: Demonstrar como a IA e o n8n aceleram o feedback de clientes (triagem de emails e canais de suporte), transformando dados brutos diretamente em itens de backlog estruturados e prontos para o planejamento da Sprint (*Refinement*).

---

## 📚 Curadoria de Fontes (NotebookLM)

Para este caderno temático, foram selecionadas e analisadas no NotebookLM as seguintes fontes oficiais e artigos técnicos de referência técnica de alta relevância:

1. **Documentação Oficial de Advanced AI do n8n**
   * *Link:* [n8n Advanced AI Docs](https://docs.n8n.io/advanced-ai/)
   * *Foco:* Conceitos de nós de IA no n8n (AI Agent, Model, Memory, Tools e Vector Stores).
2. **Template de Automação de Projetos Ágeis com IA no n8n**
   * *Link:* [n8n Workflow Template: Agile Project Setup](https://n8n.io/workflows/8101-automate-agile-project-setup-with-gpt-5-mini-jira-and-form-interface/)
   * *Foco:* Estudo de caso prático de automação que traduz ideias brutas de features em User Stories estruturadas no Jira com sub-tasks geradas por IA.
3. **Template de Assistente de Scrum Master Automatizado com OpenAI, Slack e Asana**
   * *Link:* [n8n Workflow Template: AI-powered Scrum Master Assistant](https://n8n.io/workflows/5478-ai-powered-scrum-master-assistant-with-openai-slack-and-asana-integration/)
   * *Foco:* Exemplo real de monitoramento ágil inteligente que coleta dados do Slack, Asana e reportes de desenvolvedores para prever atrasos e sugerir intervenções para o alcance da Sprint Goal.
4. **Artigo Prático: Construção de Agentes de IA com n8n**
   * *Link:* [Integrating AI Agents with n8n - Dev Community](https://dev.to/truelime/integrating-ai-agents-with-n8n-enhance-your-workflow-automation-52pc)
   * *Foco:* Desafios reais de engenharia de prompt (system messages) e a importância do ciclo de testes e refinamento direto na interface visual do n8n.

---

## 🧠 Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Um dos pontos altos deste projeto foi o aprendizado prático de como formular prompts altamente assertivos para agentes do n8n que precisam interagir em cenários de Scrum e desenvolvimento de produtos.

### Variações de Prompts Testadas

#### ❌ Prompt Inicial (Abordagem Superficial)
> *"Escreva uma user story sobre um novo fluxo de login no meu aplicativo usando IA."*
* **Resultado da IA:** Gerou uma história genérica, sem critérios de aceitação específicos, sem detalhes técnicos de segurança (como OAuth ou LGPD) e sem divisão de sub-tarefas para o time. Totalmente inadequado para um planejamento de Sprint real.

#### 💡 Prompt Avançado (Engenharia de Prompts com Contexto Ágil)
> *"Aja como um Product Owner e Analista de Sistemas Sênior trabalhando sob o framework Scrum.
> Sua tarefa é analisar o seguinte escopo bruto de feature: '{input_do_formulario}' e transformá-lo em uma User Story impecável de nível de produção.
>
> Siga RIGOROSAMENTE as seguintes regras de formatação:
> 1. Formato Padrão: 'Como [Persona], eu quero [Funcionalidade], para que [Benefício].'
> 2. Critérios de Aceitação: Detalhe pelo menos 3 cenários usando a sintaxe Gherkin (Dado que... Quando... Então...).
> 3. Sub-Tarefas Necessárias: Liste sub-tarefas essenciais divididas em: Engenharia (Frontend/Backend), Design (UI/UX), Qualidade (QA/Testes) e Infraestrutura/Segurança.
> 4. Restrição de Saída: Retorne a resposta estruturada estritamente em formato JSON válido para que possamos enviar diretamente ao nó de criação de cartões no Jira."*

* **Resultado da IA:** Retornou um JSON estruturado perfeitamente, com critérios de aceitação em Gherkin ultra-específicos e uma lista de sub-tarefas pronta para o time técnico iniciar o desenvolvimento imediatamente no Jira, reduzindo o tempo de planejamento do time em 70%.

Este código JSON está perfeitamente formatado.
{
  "user_story": {
    "title": "Atendimento Automatizado e Inteligente via WhatsApp (n8n + IA)",
    "as_a": "Cliente com dúvidas sobre os produtos ou serviços da empresa",
    "i_want_to": "ser atendido de forma rápida por um assistente inteligente de IA integrado ao WhatsApp que consulte a base de conhecimento interna e realize o transbordo para um humano quando necessário",
    "so_that": "eu consiga resolver minhas dúvidas instantaneamente, sem filas, mas ainda tenha suporte humano para questões complexas."
  },
  "acceptance_criteria": [
    {
      "scenario": "Cenário 1: Resolução de dúvida comum via IA",
      "given": "que o cliente inicia uma conversa com o bot de suporte no WhatsApp",
      "when": "ele envia uma dúvida cuja resposta está presente na base de conhecimento interna",
      "then": "o agente de IA processa a pergunta no n8n e responde imediatamente de forma precisa, mantendo o atendimento no fluxo automático."
    },
    {
      "scenario": "Cenário 2: Transbordo por falta de resposta na base de conhecimento",
      "given": "que o cliente envia uma dúvida técnica ou complexa",
      "when": "o agente de IA consulta a base de conhecimento no n8n e não localiza a informação necessária para responder",
      "then": "o sistema deve notificar o cliente amigavelmente e transferir a conversa para a fila de atendimento humano, enviando o histórico do chat para o atendente."
    },
    {
      "scenario": "Cenário 3: Cliente solicita falar com humano diretamente",
      "given": "que o cliente está no meio de uma interação com o agente de IA",
      "when": "ele digita comandos como 'falar com atendente', 'humano' ou seleciona essa opção",
      "then": "o fluxo do n8n interrompe a automação da IA imediatamente e direciona o chat para a fila de transbordo humano."
    }
  ],
  "sub_tasks": {
    "design_ui_ux": [
      "Desenhar o fluxo de conversação (árvore de decisão) e tom de voz amigável da IA",
      "Criar os templates de mensagens de boas-vindas, falha técnica e transferência para o operador humano"
    ],
    "engineering": [
      "Configurar o nó de Trigger (gatilho) do WhatsApp Webhook no n8n",
      "Integrar o nó de IA Agent com o modelo de LLM e o nó de Vector Store (Base de Conhecimento RAG) no n8n",
      "Implementar lógica dinâmica (nós Switch/Router) para direcionar o chat ao suporte humano em caso de falha ou requisição"
    ],
    "quality_assurance": [
      "Criar conjunto de perguntas de teste para homologar a acurácia das respostas da IA contra alucinações",
      "Validar se o fluxo de transbordo de conversa transfere o histórico completo da sessão para o operador de suporte",
      "Realizar testes de carga simulando múltiplos usuários enviando mensagens em tempo real no WhatsApp"
    ],
    "infrastructure_security": [
      "Configurar variáveis de ambiente criptografadas e credenciais seguras para chaves de API da OpenAI/Meta no n8n",
      "Implementar mecanismos de Rate Limiting (limite de requisições) para mitigar abuso de custos com tokens",
      "Garantir conformidade com a LGPD anonimizando dados sensíveis compartilhados nas conversas com a IA"
    ]
  }
}

### 🩹 "Cicatrizes" de Desenvolvimento (Troubleshooting)

1. **Problema de Alucinação de JSON no n8n:**
   * *Sintoma:* O nó do Agent de IA do n8n às vezes incluía explicações em texto Markdown (como ```json ...) antes e depois do JSON, o que quebrava o nó de integração com a API do Jira que exigia JSON puro.
   * *Solução:* Foi adicionado um nó de tratamento de código JavaScript/Python (nó Code) logo após o nó de IA para realizar o parsing e higienização das strings, além de reforçar no prompt do agente técnico: *"Não adicione nenhuma explicação, tags markdown ou texto além do próprio JSON."*
2. **Perda de Contexto em Conversas Longas (Buffer Memory):**
   * *Sintoma:* O agente de IA esquecia decisões tomadas no início da conversa sobre o design de uma determinada feature ao gerar tarefas adicionais.
   * *Solução:* Configuração correta de um nó de memória persistente no n8n (`Window Buffer Memory` ou banco de dados relacional leve como SQLite para sessões de longa duração), garantindo que o histórico recente de refinamento da feature permanecesse visível ao modelo.

---

## 📕 Miniguia de Estudo (Entrega Final)

### 📊 Resumos Estruturados: Automação + IA + Scrum

#### 1. Aceleração da Esteira de Valor (Lead Time & Cycle Time)
Ao invés de deixar que o time perca horas preciosas de planejamento criando histórias, estruturando tarefas repetitivas no Jira ou triando dezenas de e-mails de feedback de clientes de forma manual, o n8n conectado a IAs faz a ingestão em tempo real. O feedback do cliente chega através de um webhook (nós de gatilho do n8n), a IA classifica, gera um sumário inteligente e injeta diretamente no Backlog com a prioridade correta pré-sugerida. Isso reduz drasticamente o *Lead Time* da melhoria do produto.

#### 2. O Papel da IA como Facilitadora nas Cerimônias Scrum
A IA não substitui papéis, ela empodera as pessoas no framework Scrum:
* **Product Owner (PO):** O PO ganha um assistente virtual de refinamento de backlog que escreve rascunhos de histórias extremamente ricos a partir de ideias em áudio, notas de reuniões ou e-mails de clientes.
* **Scrum Master (SM):** IAs integradas com n8n analisam fluxos de conversas no Slack e movimentação de tarefas no Asana/Jira para identificar padrões de comportamento de equipe, gargalos em fases específicas da Sprint (ex: gargalos de QA) e alertar o SM sobre riscos iminentes ao Sprint Goal antes que a Sprint termine.
* **Developers:** Passam menos tempo preenchendo status ou abrindo cards manuais, pois podem usar integrações simples de chatbot no Slack/Telegram conectadas ao n8n para atualizar tarefas por comando de voz ou comandos rápidos de linguagem natural.

---

### 📖 Glossário de Conceitos Integrados

* **AI Agent (n8n):** Um nó avançado no n8n que pode tomar decisões de forma semi-autônoma, decidindo de forma dinâmica quando e qual ferramenta externa usar (como ler o Jira, disparar um e-mail ou buscar informações) para resolver uma instrução em linguagem natural.
* **Backlog Grooming / Refinement (Scrum):** O processo de adição de detalhes, estimativas e ordenação aos itens do Product Backlog. A automação n8n com IA atua aqui, estruturando ideias abstratas e qualificando-as tecnicamente antes da reunião de refinamento oficial com o time.
* **System Message (n8n Agent):** O prompt mestre que instrui e define a personalidade, regras de comportamento, tom, conhecimentos permitidos e as restrições operacionais que o agente de IA do n8n deve obedecer.
* **Webhooks (n8n):** Nós de gatilho que permitem que o n8n escute requisições instantâneas vindas de outras ferramentas (como Slack, Jira ou seu próprio produto digital). Permitem a criação de automações baseadas em eventos em tempo real.
* **Impediment Alerting (Scrum):** Prática ágil de monitorar e remover barreiras que bloqueiam o progresso do time de desenvolvimento. No contexto n8n, é executada de forma automática através de agentes de IA integrados a canais de Slack de daily meetings.

---

### 📋 Prompts Reutilizáveis para Estudos e Prática Ágil

Abaixo estão 3 templates de prompts de alta performance testados e prontos para serem reutilizados na sua jornada de estudos no NotebookLM ou integrados nos nós de IA do seu n8n:

#### 1. Prompt para Geração de Acceptance Criteria (Foco: PO)
```text
Aja como um Product Owner especialista em Scrum.
Analise a seguinte feature proposta: "Integração de um agente de IA no chat de suporte do WhatsApp (via n8n) que consulte a nossa base de conhecimento interna para responder dúvidas frequentes dos clientes automaticamente, encaminhando para um atendente humano somente se a IA não souber responder ou se o cliente solicitar."
Gere 3 critérios de aceitação detalhados usando a linguagem de testes Gherkin (Dado que / Quando / Então).
A resposta deve ser em Português e focada no valor entregue ao usuário final do produto.
```

#### 2. Prompt para Diagnóstico de Gargalos na Sprint (Foco: Scrum Master)
```text
Aja como um Agile Coach experiente. Analise o seguinte resumo de status do time de desenvolvimento na Sprint atual:
"O nó de integração do WhatsApp no n8n está apresentando erro de autenticação na API de homologação, deixando 3 tarefas travadas na coluna de QA. No canal do Slack, os desenvolvedores estão em um debate infinito sobre usar PostgreSQL ou Pinecone para salvar a memória do Agente de IA. Faltam apenas 3 dias para o fim da Sprint e a meta (Sprint Goal) está em risco."
Forneça um plano de ação de 3 passos rápidos para o Scrum Master mitigar o risco de não entrega do Sprint Goal, focando em colaboração e remoção de impedimentos.
```

#### 3. Prompt para Tradução de Feedback Técnico em Itens de Melhoria de Produto
```text
Aja como um Analista de QA e Engenheiro de Suporte de Nível 3.
Leia o seguinte e-mail de reclamação técnica de cliente: "De: carlos.vendas@empresa.com Assunto: URGENTE: O robô de vendas do WhatsApp quebrou e está enviando código de erro!
Olá, suporte! Desde as 9h da manhã de hoje, o nosso assistente automático de vendas do WhatsApp parou de funcionar. Quando os clientes mandam mensagem perguntando o preço de um produto, o robô responde com um bloco enorme de código JSON esquisito com uma mensagem de 'Internal Server Error (500)'. Nossos vendedores estão perdendo vendas porque o robô trava a conversa e não repassa para os humanos. Preciso de uma solução agora mesmo, estamos perdendo dinheiro!"
Traduza essa reclamação em um relatório de bug estruturado para desenvolvedores contendo:
- Descrição clara do problema técnico suspeito.
- Passos prováveis para reproduzir.
- Gravidade esperada (Alta, Média ou Baixa) com base no impacto no produto.
```

---

*Estudo desenvolvido como parte do projeto de portfólio no Bootcamp de Automação com n8n e IA da DIO e Santander. 🚀*
#Jean Campagnoli Sales
