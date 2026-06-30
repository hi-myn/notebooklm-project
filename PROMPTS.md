# Engenharia de Prompts e "Cicatrizes"

Este documento detalha as perguntas estratégicas testadas no NotebookLM treinado com as três fontes do caderno temático, as respostas obtidas, as fontes citadas e as dificuldades encontradas no processo (troubleshooting). O objetivo foi variar o tipo de pergunta — conceitual, comparativa, aplicada e "armadilha" — para avaliar não só a qualidade das respostas, mas a capacidade do notebook de cruzar fontes e admitir limitações.

> Para o contexto geral do projeto, objetivos de estudo e fontes utilizadas, veja o [README.md](./README.md).

---

### Prompt 1: "O que é Machine Learning e como ele se diferencia da programação tradicional?"
**Resposta resumida:** ML é definido como a ciência de programar computadores para aprenderem a partir de dados (citando a definição clássica de Arthur Samuel). A diferença central destacada é que, na programação tradicional, o desenvolvedor escreve manualmente todas as regras (ex: filtro de spam baseado em palavras-chave), enquanto em ML o sistema aprende os padrões a partir de exemplos e se adapta automaticamente a mudanças, sem necessidade de reescrever código.

**Fonte citada pelo notebook:** Hands-On Machine Learning (Géron) — uso do exemplo clássico do filtro de spam.

**Funcionou?** Sim.

**Dificuldade encontrada:** Nenhuma relevante — pergunta de fundamentação ampla e bem coberta pela fonte, resposta clara e didática de primeira tentativa.

**Ajuste feito:** Nenhum necessário.

---

### Prompt 2: "O que Burkov e Huyen dizem sobre monitoramento de modelos em produção? Eles concordam ou divergem em algum ponto?"
**Resposta resumida:** O notebook identificou convergência entre os dois autores em pontos centrais: modelos degradam após o deploy, falhas em ML costumam ser silenciosas, ambos tratam data/concept drift como o principal risco e ambos reconhecem a dificuldade de avaliar modelos online pela ausência de "ground truth" imediato. Como diferença de ênfase (não de fundo), apontou que Burkov foca mais em riscos de segurança e ataques adversariais, enquanto Huyen aprofunda mais os feedback loops degenerativos.

**Fonte citada pelo notebook:** Designing Machine Learning Systems (Huyen) e Machine Learning Engineering (Burkov), citando ambos lado a lado.

**Funcionou?** Sim.

**Dificuldade encontrada:** Nenhuma — esse foi o teste mais importante de "cruzamento de fontes" e o notebook conseguiu comparar os dois livros de forma estruturada, distinguindo convergência de divergência de foco em vez de generalizar.

**Ajuste feito:** Nenhum necessário; o prompt já veio bem direcionado (pedindo explicitamente concordância/divergência), o que ajudou a evitar resposta genérica.

---

### Prompt 3: "Quais erros comuns um engenheiro de software comete ao migrar para ML, segundo os autores?"
**Resposta resumida:** Listou 5 erros recorrentes: tratar ML como software tradicional (ignorando que dados também precisam ser versionados/testados), focar só no modelo e negligenciar infraestrutura/monitoramento, esperar falhas "barulhentas" como em software comum, testar o modelo nos próprios dados de treino (citando Pedro Domingos), e abuso de "glue code" na integração de pacotes.

**Fonte citada pelo notebook:** Designing Machine Learning Systems (Huyen), artigo de Pedro Domingos e referência implícita a práticas de engenharia (glue code).

**Funcionou?** Sim.

**Dificuldade encontrada:** Resposta combinou corretamente fontes diferentes (livro + artigo), mas exigiu que o prompt fosse formulado de forma específica ("segundo os autores", no plural) para forçar o cruzamento — uma versão mais genérica do prompt ("erros comuns em ML") tendia a trazer resposta mais rasa em testes anteriores.

**Ajuste feito:** Adicionei "segundo os autores" explicitamente ao prompt para forçar citação cruzada das fontes, em vez de resposta genérica de conhecimento geral do modelo.

---

### Prompt 4: "Segundo o capítulo sobre deployment de Burkov, quais são as etapas recomendadas?"
**Resposta resumida:** Detalhou os 4 pré-requisitos de Burkov para deploy (testes end-to-end, testes de confiança, métrica de desempenho e intervalo aceitável), o fluxo automatizado de deployment (busca de artefatos, cópia para produção, validação simulada, decisão de rollback) e as estratégias de liberação (single, silent, canary, multi-armed bandits).

**Fonte citada pelo notebook:** Machine Learning Engineering (Burkov), com referência direta ao capítulo de deployment.

**Funcionou?** Sim.

**Dificuldade encontrada:** Este foi um teste de "forçar a fonte" — pedir explicitamente um capítulo específico de um autor específico. O notebook conseguiu isolar corretamente a fonte sem misturar com o conteúdo de Huyen sobre o mesmo assunto (que também trata de canary/silent deployment), o que era o principal risco desse tipo de prompt.

**Ajuste feito:** Nenhum necessário; nomear explicitamente autor + capítulo foi suficiente para evitar mistura de fontes.

---

### Prompt 5: "Crie um roteiro de estudo de 4 semanas baseado nessas fontes, do básico ao avançado."
**Resposta resumida:** Gerou um roteiro estruturado em 4 semanas, progredindo de fundamentos de ML e ciclo de vida do projeto (semana 1), passando por preparação de dados e feature engineering (semana 2), modelagem e algoritmos avançados (semana 3), até deployment, monitoramento e MLOps (semana 4) — sintetizando conteúdo das três fontes em uma sequência lógica de aprendizado.

**Fonte citada pelo notebook:** Combinação das três fontes (Géron, Huyen e Burkov), distribuídas conforme o tema de cada semana.

**Funcionou?** Sim.

**Dificuldade encontrada:** Esse foi o prompt de síntese mais ambicioso (pedindo organização didática, não só recuperação de informação). A resposta veio bem estruturada de primeira tentativa, mas é o tipo de prompt mais difícil de validar — exige checar manualmente se a ordem dos tópicos faz sentido pedagogicamente e se nenhuma fonte ficou sub-representada.

**Ajuste feito:** Nenhum ajuste de prompt, mas como follow-up, recomendo validar item a item comparando com o índice de cada livro, já que prompts de síntese têm maior risco de generalização excessiva.

---

### Prompt 6: "Por que ML sempre precisa de big data?" (prompt "armadilha", com pressuposto questionável)
**Resposta resumida:** Em vez de aceitar a premissa de que ML *sempre* precisa de big data, o notebook explicou o motivo histórico/prático (algoritmos simples com muitos dados superam algoritmos complexos com poucos dados, citando Peter Norvig), mas também trouxe ressalvas importantes: qualidade dos dados importa tanto quanto quantidade, nem sempre é necessário usar todo o dataset disponível, e dados sozinhos não bastam sem conhecimento de domínio.

**Fonte citada pelo notebook:** Hands-On Machine Learning (Géron), com citação da frase de Peter Norvig.

**Funcionou?** Parcial.

**Dificuldade encontrada:** O notebook não corrigiu diretamente a premissa do "sempre" (não deixou explícito que existem técnicas para cenários com poucos dados, como transfer learning ou few-shot learning, mencionadas em outros trechos das próprias fontes), apenas suavizou a afirmação com ressalvas ao longo da resposta. Esse é um exemplo de "cicatriz" real: prompts com pressupostos errados tendem a ser parcialmente aceitos em vez de contestados de forma explícita logo no início da resposta.

**Ajuste feito:** Para uma próxima iteração, planejo reformular o prompt de forma mais direta — ex: "É verdade que ML sempre precisa de big data? Existem exceções nas fontes?" — para forçar o notebook a se posicionar sobre a premissa antes de explicar o conceito.

---

### Prompt 7 (evolução do Prompt 6): "É verdade que ML sempre precisa de big data? Existem exceções nas fontes?"
**Resposta resumida:** Desta vez o notebook se posicionou diretamente logo na primeira frase ("Não, não é verdade..."), contestando a premissa do "sempre" em vez de só suavizá-la. Em seguida, listou 4 exceções concretas presentes nas fontes: Transfer Learning (reaproveitar um modelo treinado em outra tarefa com muitos dados), Zero-shot e Few-shot Learning (aprender com poucos ou nenhum exemplo da tarefa específica), uso de algoritmos clássicos/shallow learning combinados com engenharia de features manual para compensar a falta de volume, e o uso de amostragem com validação cruzada para datasets pequenos (menos de mil exemplos).

**Fonte citada pelo notebook:** Hands-On Machine Learning (Géron), abordando Transfer Learning, zero/few-shot learning e técnicas para datasets pequenos com validação cruzada.

**Funcionou?** Sim.

**Dificuldade encontrada:** Nenhuma — esse foi exatamente o resultado esperado após o ajuste. A simples reformulação do prompt, pedindo explicitamente para o notebook confirmar/refutar a premissa ("É verdade que...? Existem exceções?"), foi suficiente para trocar uma resposta que apenas matizava a afirmação (Prompt 6) por uma resposta que se posiciona com clareza logo de início e ainda traz mais profundidade técnica.

**Ajuste feito:** Nenhum ajuste adicional necessário.

> **Aprendizado de troubleshooting:** comparando os Prompts 6 e 7, a principal "cicatriz" documentada neste caderno foi perceber que perguntas com pressupostos questionáveis tendem a ser respondidas de forma evasiva ou apenas matizada quando formuladas como afirmação aberta ("Por que X sempre...?"). Ao reformular a pergunta exigindo um posicionamento explícito ("É verdade que...? Existem exceções?"), o notebook passou a contestar a premissa diretamente e trouxe informações mais ricas que já estavam nas fontes, mas não haviam sido priorizadas na resposta anterior. Isso reforça a importância de testar variações de um mesmo prompt antes de aceitar a primeira resposta como definitiva.