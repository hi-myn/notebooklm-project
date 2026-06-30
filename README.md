# Caderno Temático: Machine Learning para Engenheiros de Software

> Projeto desenvolvido como parte do desafio de bootcamp

---

## Contexto e Objetivos

O assunto escolhido para este caderno temático foi **Machine Learning (ML)**, com foco específico em como esse conhecimento se aplica e se conecta à rotina de um(a) engenheiro(a) de software.
 
A escolha desse tema parte de uma constatação simples: ML é uma das áreas que mais cresce atualmente e está presente, direta ou indiretamente, em praticamente todo produto de software moderno. Hoje em dia, falar em Inteligência Artificial é, em grande parte, falar em Machine Learning — já que é por meio dele que a maioria dos sistemas de IA aprende padrões, toma decisões e evolui com base em dados.
 
Como engenheiro(a) de software, entender ML deixou de ser um diferencial e passou a ser uma competência cada vez mais necessária, seja para construir esses sistemas, seja para integrá-los, mantê-los ou simplesmente conversar com times de dados de forma mais técnica e crítica.

### Objetivos de Estudo

Com este material, busco:
 
- **Entender como uma IA é construída na prática**, partindo do princípio de que toda Inteligência Artificial é, em sua essência, resultado de um processo de Machine Learning bem aplicado.
- **Aprender a diferenciar e criar sistemas "dependentes" e "independentes"**, ou seja, compreender a fronteira entre modelos que dependem fortemente de supervisão e ajuste humano constante e modelos capazes de aprender e se adaptar com maior autonomia.
- **Desenvolver a habilidade de "ensinar máquinas"**, indo além da lógica tradicional de programação (onde o engenheiro escreve regras explícitas) para a lógica de ML (onde o sistema aprende padrões a partir de dados e exemplos).
- **Conectar a engenharia de software à engenharia de ML**, entendendo como decompor problemas de negócio em problemas de aprendizado de máquina, e como isso se integra a sistemas em produção (não apenas em notebooks de experimentação).
- **Construir uma base prática e conceitual** que permita, no futuro, treinar, validar e implantar modelos de forma responsável, entendendo tanto a teoria por trás dos algoritmos quanto os desafios reais de levar ML para produção.

> Em resumo, o objetivo central deste estudo não é apenas entender *o que* é Machine Learning, mas sim **aprender a pensar como alguém que treina máquinas para resolver problemas com certo grau de autonomia** — unindo a mentalidade de resolução de problemas já presente na engenharia de software com a mentalidade de aprendizado de máquina.

---

## Curadoria de Fontes

Para treinar o caderno temático no NotebookLM, foram selecionadas e disponibilizadas (via upload em PDF, presentes na pasta [`/fontes`](/fontes) deste repositório) as seguintes fontes:

1. "Designing Machine Learning Systems" — Chip Huyen: Referência central para entender ML aplicado em produção, com foco em arquitetura de sistemas, pipelines de dados e desafios reais do ciclo de vida de um modelo — indo além da teoria pura de algoritmos.
2. "Machine Learning Engineering" — Andriy Burkov: Material direto e objetivo sobre engenharia de ML, cobrindo desde a preparação de dados até deploy e monitoramento, com uma abordagem mais prática e menos acadêmica.
3. Hands-On Machine Learning with Scikit-Learn, Keras & TensorFlow" — Aurélien Géron: Livro de referência clássico, utilizado como base teórica e prática, equilibrando fundamentos de algoritmos de ML com implementação de código real.

> As três fontes foram escolhidas por se complementarem: enquanto o livro de Géron fornece a base conceitual e prática dos algoritmos, os livros de Huyen e Burkov aprofundam a perspectiva de engenharia, produção e ciclo de vida de sistemas de ML — alinhando-se diretamente aos objetivos de estudo definidos para este caderno temático.

---

## Engenharia de Prompts e "Cicatrizes"

Foram testados 7 prompts estratégicos no NotebookLM, variando entre perguntas conceituais, comparativas entre fontes, aplicadas ao contexto de engenharia de software e prompts "armadilha" (com pressupostos questionáveis), para avaliar a qualidade das respostas, a fidelidade às fontes e a capacidade do notebook de admitir limitações.
 
O destaque do processo foi um caso de troubleshooting real: o prompt "Por que ML sempre precisa de big data?" gerou uma resposta apenas parcialmente satisfatória (o notebook suavizou a premissa em vez de contestá-la diretamente). Ao reformular para "É verdade que ML sempre precisa de big data? Existem exceções?", a resposta passou a se posicionar com clareza e trouxe informações mais ricas, já presentes nas fontes, mas que não haviam sido priorizadas antes.
 
O detalhamento completo de cada prompt testado — resposta resumida, fonte citada, se funcionou, dificuldades encontradas e ajustes feitos — está documentado em [PROMPTS.md](./PROMPTS.md).

---

## Miniguia de Estudo (Entrega Final)
 
Como consolidação de todo o processo de curadoria e teste de prompts, o resultado final deste caderno temático está reunido em [GUIA-DE-ESTUDO.md](./GUIA-DE-ESTUDO.md), contendo:
 
- **Resumos estruturados** dos principais temas estudados (fundamentos de ML, preparação de dados, modelagem, deployment e monitoramento), sintetizando o conteúdo das três fontes utilizadas.
- **Glossário** com os principais conceitos aprendidos durante o estudo (ex: overfitting, data drift, feature engineering, canary deployment, entre outros).
- **Prompts reutilizáveis**, refinados a partir dos testes documentados em [PROMPTS.md](./PROMPTS.md), prontos para apoiar futuras revisões sobre o tema diretamente no NotebookLM.
## Estrutura do Repositório
 
```
.
├── README.md              # Contexto, objetivos, fontes e visão geral do projeto
├── PROMPTS.md              # Detalhamento dos testes de engenharia de prompts
├── GUIA-DE-ESTUDO.md       # Entrega final: resumos, glossário e prompts reutilizáveis
└── fontes/                 # PDFs das fontes utilizadas no NotebookLM
```
---
## 🔗 Link do Notebook

> 📎 Acesse o caderno temático completo no NotebookLM: **[NotebookLM](https://notebooklm.google.com/notebook/2ce88f13-0c1b-4cb6-8300-075596748c0b)**
