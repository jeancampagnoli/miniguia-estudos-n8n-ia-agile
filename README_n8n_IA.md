# Caderno Temático: Automação Inteligente com n8n e IA 🚀
> **Projeto desenvolvido para o Bootcamp DIO & Santander - Automação com n8n e IA**

Este repositório contém a documentação, curadoria de fontes e o processo de aprendizado ativo realizado utilizando o **NotebookLM** como copiloto de estudos. O objetivo deste projeto é dominar a integração de fluxos visuais de automação no **n8n** com recursos avançados de Inteligência Artificial (como Agentes de IA, Cadeias e Memórias).

---

## 🎯 1. Contexto e Objetivos

### Contexto
O mercado atual exige processos cada vez mais eficientes e inteligentes. A ferramenta **n8n**, combinada com nós de IA (Advanced AI), permite criar fluxos de trabalho que não apenas movem dados de um sistema para o outro, mas também tomam decisões, analisam sentimentos, extraem informações estruturadas de textos complexos e interagem de forma autônoma (Agentes de IA). 

### Objetivos de Estudo
1. **Compreender a arquitetura do n8n** voltada para IA (Nós de Agente, Cadeias, Modelos de Linguagem, Memória e Ferramentas).
2. **Aprender a estruturar prompts eficazes** para que as IAs integradas aos fluxos de trabalho do n8n operem com precisão e sem alucinações.
3. **Desenvolver habilidades de curadoria** técnica ao extrair valor de documentações e manuais oficiais.
4. **Criar um guia prático reutilizável** para acelerar a construção de futuras automações inteligentes.

---

## 📚 2. Curadoria de Fontes
Para alimentar o NotebookLM e garantir respostas 100% embasadas na realidade técnica da ferramenta, selecionei as seguintes fontes oficiais e abertas (adicione os links reais das fontes que você subir no seu NotebookLM):

1. **Documentação Oficial do n8n - Advanced AI Nodes**  
   *Descrição:* Guia oficial que explica como utilizar os nós de IA (OpenAI, LangChain, etc.) e como conectá-los a memórias e ferramentas.  
   *Link sugerido:* `https://docs.n8n.io/advanced-ai/`
2. **Guia de Integração de Agentes de IA (AI Agents) no n8n**  
   *Descrição:* Conceitos fundamentais sobre a diferença entre fluxos lineares e agentes autônomos baseados em prompts e ferramentas.  
   *Link sugerido:* `https://docs.n8n.io/advanced-ai/agents-and-chains/`
3. **Boas Práticas de Engenharia de Prompts para Automação**  
   *Descrição:* Artigo/paper abordando como estruturar diretrizes para sistemas autônomos tomarem decisões lógicas em workflows.  
   *Link sugerido:* (Insira o link de um artigo ou paper de sua escolha sobre o tema)

---

## 🧠 3. Engenharia de Prompts e "Cicatrizes" (Troubleshooting)

Abaixo estão documentados os testes realizados no NotebookLM para entender o comportamento das automações inteligentes e como as instruções de sistema impactam as execuções dos nós de IA no n8n.

### Teste de Prompt 1: O Prompt Superficial (Abordagem "Ingênua")
*   **Prompt enviado:**
    > *"Como eu crio um agente no n8n para responder e-mails de clientes?"*
*   **Resposta obtida da IA:**
    > A IA deu uma resposta conceitual e genérica, dizendo para usar um nó de trigger de e-mail, um nó de IA e um nó de envio, sem especificar como o agente deveria se comportar, quais ferramentas (Tools) ele precisaria ou como estruturar o System Message para evitar que ele inventasse respostas sobre produtos.
*   **Análise Crítica:** Falta de especificidade técnica e de arquitetura de nós do n8n.

### Teste de Prompt 2: O Prompt Avançado (Engenharia de Prompts)
*   **Prompt enviado (com contexto, persona, tarefas e restrições):**
    > *"Aja como um Arquiteto de Soluções especialista em n8n e IA. Com base na documentação oficial (fontes), descreva o passo a passo exato para estruturar um 'AI Agent' (nó de Agente) que recebe e-mails de clientes via Webhook, analisa o conteúdo e decide se deve responder usando uma ferramenta de pesquisa de banco de dados (Tool) ou se deve encaminhar para um atendente humano. Explique quais sub-nós (Model, Memory, Tools) devem estar conectados ao nó do Agent e como preencher o 'System Message' dele para garantir tom profissional e uso estrito das ferramentas."*
*   **Resposta obtida da IA:**
    > A IA explicou detalhadamente a estrutura:
    > 1. Conectar o nó **AI Agent** ao fluxo principal.
    > 2. Anexar o sub-nó **Chat OpenAI Model** (ou similar) para processamento de linguagem.
    > 3. Anexar o sub-nó **Window Buffer Memory** para manter o histórico da conversa com o cliente.
    > 4. Anexar um sub-nó **Custom Tool** (Ferramenta customizada) configurada com o nó HTTP Request para consultar a API interna de produtos.
    > 5. Exemplo de *System Message* configurado para instruir o Agente a nunca inventar dados e acionar a Tool sempre que houver dúvida.
*   **"Cicatrizes" e Aprendizados (Troubleshooting):**  
    *   *Desafio:* Inicialmente, o NotebookLM misturou conceitos de nós normais do n8n (como o nó IF comum) com nós de decisão do Agente de IA.  
    *   *Como foi resolvido:* Foi necessário refinar o prompt instruindo a IA a focar estritamente na seção de "Advanced AI" e na funcionalidade de "Router/Agent Tools", forçando-a a diferenciar lógica condicional tradicional de decisão autônoma do modelo de linguagem.

---

## 📖 4. Miniguia de Estudo (Entrega Final)

### Resumo Estruturado: Automação Baseada em Agentes de IA vs. Fluxos Tradicionais

1. **Fluxos Tradicionais (Determinísticos):**
   * Seguem uma lógica rígida baseada em regras (`Se A acontecer, faça B`).
   * Excelente para sincronização de dados e tarefas repetitivas simples.
   * Falham quando lidam com entradas de dados não estruturadas (como e-mails longos, áudios ou textos livres).

2. **Fluxos com Advanced AI (Baseados em Intencionalidade):**
   * Utilizam LLMs para interpretar a intenção do usuário.
   * O **AI Agent** funciona como o "cérebro" do fluxo, decidindo em tempo de execução qual caminho tomar usando as ferramentas disponibilizadas a ele (Tools).
   * Permite criar atendimentos personalizados, classificação automática inteligente de tickets e geração de relatórios sob demanda.

### Glossário Técnico de Termos
*   **AI Agent (Agente de IA):** Nó especial no n8n que encapsula um modelo de IA e permite que ele interaja com o fluxo de forma não linear, usando ferramentas de forma autônoma para resolver uma tarefa.
*   **System Message (Instrução do Sistema):** O prompt mestre que define a personalidade, regras de segurança, restrições e objetivos do Agente de IA.
*   **Tools (Ferramentas):** Recursos que o Agente de IA pode "chamar" para realizar ações externas, como buscar dados em uma API, rodar código JavaScript ou ler um banco de dados.
*   **Memory (Memória do Agente):** Nós conectados ao Agent que armazenam o histórico das interações passadas para dar contexto às respostas seguintes (ex: *Window Buffer Memory* ou *Redis Chat Memory*).
*   **Vector Store (Banco de Dados Vetorial):** Banco de dados especializado em armazenar embeddings (vetores de texto) para permitir pesquisas semânticas rápidas, muito usado para estratégias de RAG (Retrieval-Augmented Generation).

### Prompts Reutilizáveis para Estudo e Revisão

*   **Prompt para Geração de Casos de Uso:**
    > *"Com base nas fontes estudadas sobre n8n, sugira 3 ideias práticas de fluxos de automação que integrem n8n, Webhooks e agentes de IA para o setor de atendimento ao cliente, destacando quais ferramentas (tools) cada agente precisará ter."*
*   **Prompt para Debug de Erros de Integração:**
    > *"Estou recebendo um erro de 'Timeout' ou 'JSON inválido' ao tentar passar a resposta da minha IA para o próximo nó do n8n. Com base nas boas práticas de tratamento de dados das fontes, como posso forçar a IA a responder estritamente em formato JSON usando as diretrizes de prompt?"*

---

## 🚀 Como Executar e Adaptar este Projeto
1. Crie seu repositório no GitHub.
2. Copie este arquivo `README.md` e preencha as lacunas com os seus testes e as fontes que você selecionou.
3. Personalize a seção de "Engenharia de Prompts" com as suas próprias dúvidas e descobertas reais durante o Bootcamp!
