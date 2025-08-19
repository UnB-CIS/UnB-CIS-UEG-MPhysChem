# Processo Trainee - IEEE CIS Chapter Universidade de Brasília 🚀

Somos um capítulo estudantil vinculado à IEEE, a maior organização profissional do mundo dedicada ao avanço da tecnologia em benefício da humanidade. Nosso objetivo é capacitar estudantes na área de inteligência computacional e inteligência artificial e democratizar o conhecimento. 🎯

Sejam bem vindos, aqui estarão presentes todos os arquivos referentes aos períodos do processo Trainee do CIS!

---
# Sumário


- [1º Período — Regressão e Classificação](#1o-periodo-regressao-e-classificacao-0505--1205)  
- [2º Período — Clusterização](#2o-periodo-clusterizacao-1205--1905)  
- [3º Período — Redes Neurais](#3o-periodo-redes-neurais)  
- [4º Período — Visão Computacional](#4o-periodo-visao-computacional-0306--1006)  
- [5º Período — Apresentações](#5o-periodo-apresentacoes-0206--0906)

---

<!-- 1º Período -->
# 📅 1 Período — Regressão e Classificação (05/05 – 12/05)

## 📌 Regressão Linear
- **Objetivo:** prever valores contínuos.
- **MSE** 🟦: erro médio ao quadrado, sensível a outliers.
- **MAE** 🟩: erro médio absoluto, menos sensível a outliers.
- **Uso:** MSE penaliza mais erros grandes; MAE mostra erro médio real.

## 📌 Classificação
- **Definição:** prever categorias a partir de dados.
- **Exemplo:** e-mails *spam* ou *não spam*.
- **Lazy Learners** 🐢: memorizam dados; adaptação rápida; predição lenta.
- **Eager Learners** 🚀: criam modelo; predição rápida; menos adaptáveis.

## 📌 Métricas de Classificação
- **Acurácia** 📊: % de acertos (bom p/ dados balanceados).
- **Precisão** 🎯: positivos corretos / previstos positivos.
- **Recall** 🔍: positivos encontrados / positivos reais.
- **F1-score** ⚖️: equilíbrio entre precisão e recall.

### 📂 Aula
- [Slides](1_Período/Apresentacao.pdf)

#### 📝 Desafio de Regressão — Wine Quality  
- **Objetivo:** Criar um modelo de regressão para prever a qualidade do vinho verde (variedade vermelha ou branca) com base em dados químicos (ex.: acidez, pH, álcool).  
- **Dados:** 11 atributos químicos; variável alvo: qualidade (score 0-10).  
- **Entrega:** Individual, no GitHub pessoal.  
- [Atividade Completa](1_Período/Atividade_regrecao.pdf)

---

#### 📝 Desafio de Classificação — Census Income  
- **Objetivo:** Construir modelos de classificação binária para prever se a renda anual de um indivíduo é maior que US$ 50.000.  
- **Dados:** 48.842 registros com 14 atributos demográficos e socioeconômicos (idade, educação, ocupação, etc.).  
- **Tarefas obrigatórias:** Treinar Árvore de Decisão e Random Forest; avaliar com acurácia, precisão, recall e F1; gerar matriz de confusão e gráfico de importância.  
- **Tarefas opcionais:** Análise exploratória, validação cruzada e redução de dimensionalidade.  
- [Atividade Completa](1_Período/Atividade_classificacao.pdf)
---

<!-- 2  Período -->
# 📅 2o Periodo - Clusterizacao (12/05 – 19/05)

### 📌 Aprendizado Supervisionado vs. Não Supervisionado

- **Supervisionado:** Prever classe (classificação) ou valor contínuo (regressão) usando dados rotulados.  
- **Não Supervisionado:** Descobrir padrões e agrupar dados não rotulados, como em clusterização.

---

### 📌 O que é Clusterização?

- Técnica de aprendizado **não supervisionado** que agrupa dados semelhantes em **clusters**.  
- 🎯 **Objetivo:** Maximizar a similaridade dentro dos grupos e minimizar entre grupos diferentes.

---

### 📌 Por que usar Clusterização?

- 🔍 Identificação automática de padrões sem necessidade de supervisão.  
- 📉 Redução de dimensionalidade e simplificação dos dados.  
- 🧩 Auxilia na tomada de decisão baseada em agrupamentos.

---

### 📌 Funcionamento do K-means

1. 🚀 **Inicialização:** Escolha K centróides aleatórios.  
2. 🎯 **Atribuição:** Associe cada ponto ao centróide mais próximo.  
3. 🔄 **Recalcular centróides:** Média dos pontos em cada grupo.  
4. 🔁 **Repetir:** Até os centróides não mudarem (convergência).

---

### 📌 Outros pontos Importantes

- 📊 **Inércia:** Mede a qualidade dos clusters; valores menores indicam clusters mais compactos.  
- 🔢 **Número ideal de clusters:** Determinado por análise da inércia ou métodos específicos.  
- ⚙️ Existem outros modelos de clusterização além do K-means.

---

### 📚 Aula
- [Slides do Segundo Período](2_Período/Apresentacao.pdf)

### 📝 Desafio — 2º Período: Clusterização

- 🚀 Implementar K-Means do zero em Python.  
- 📊 Analisar *Student Habits vs Academic Performance*: levantar hipóteses, fazer EDA e revisar com resultados.  
- 🔢 Justificar o número de clusters (K).  
- 📚 Opcional: pesquisar DBSCAN, Hierarchical Clustering e algoritmo avançado.

> 💡 *Dica:* “Se você torturar os dados por tempo suficiente, eles confessarão.”  
- [Desafio de Clusterização](2_Período/Atividade.pdf)

--- 
<!-- 3  Período -->
# 📅 3º Período — Redes Neurais

### 📌 O que são Redes Neurais?

- Inspiradas no cérebro humano para aprender padrões complexos.  
- Usadas em reconhecimento de imagem, tradução, previsão, entre outros.  
- Não "pensam", mas capturam relações complexas nos dados.

---

### 📌 Conteúdos Principais

- Perceptron, funções de ativação, pesos e bias.  
- Feedforward, backpropagation e gradiente descendente.  
- Função de custo, métricas de avaliação.  
- Overfitting, underfitting, regularização e otimização.  
- Implementação prática com TensorFlow e PyTorch.

---

### 📌 Base de Dados

- Stellar Classification Dataset (galáxias, quasares e estrelas) do Kaggle.

---

### 📝 Desafio — 3º Período: Redes Neurais

- 🛠️ Construir uma rede neural para classificar galáxias, quasares e estrelas.  
- ⚙️ Testar variações na arquitetura, épocas e learning rate.  
- 🔎 Identificar overfitting e underfitting, aplicando regularização.  
- 💡 Opcional: criar rede neural “from scratch” em Python e testar outros datasets via Keras.

---

### 📚 Aula  
- [Slides do Terceiro Período](3_Período/Apresentacao.pdf)

### 📝 Link do Desafio  
- [Desafio de Redes Neurais](3_Período/Atividade.pdf)

--- 
# 📅 4º Período — Visão Computacional (03/06 – 10/06)

### 📌 O que são Redes Neurais Convolucionais (CNNs)?

- Algoritmos de aprendizado profundo especializados em reconhecimento de objetos.  
- Aplicações: classificação de imagens, detecção de objetos, segmentação, veículos autônomos, sistemas de segurança, etc.  
- Inspiradas no córtex visual humano, com arquitetura hierárquica e conectividade local.  

---

### 📌 Componentes Principais das CNNs

1. **Camadas Convolucionais:** Aplicam filtros (kernels) para extrair padrões locais (bordas, formas).  
2. **Função de Ativação (ReLU):** Introduz não-linearidade e ajuda a aprender padrões complexos.  
3. **Camadas de Pooling:** Reduzem a dimensionalidade, destacando características importantes e ajudando a evitar overfitting.  
4. **Camadas Totalmente Conectadas:** Realizam a classificação final, geralmente usando Softmax para gerar probabilidades.  

---

### 📌 Overfitting e Regularização

- **Overfitting:** Quando o modelo decora os dados de treino, mas falha em generalizar.  
- **Técnicas para mitigar:**  
  - Dropout  
  - Batch Normalization  
  - Early Stopping  
  - Data Augmentation  
  - Regularização L1 e L2  

---

### 📌 Aplicações Práticas

- Classificação e organização automática de imagens.  
- Detecção e localização de objetos em imagens.  
- Reconhecimento facial para segurança.  
- Veículos autônomos e diagnóstico médico.  

---

### 📌 Frameworks Populares

- **TensorFlow:** Ferramenta completa para desenvolvimento e deploy.  
- **Keras:** Interface simples para prototipagem rápida, roda sobre TensorFlow.  
- **PyTorch:** Popular por seu grafo dinâmico e uso em pesquisa.  

---

### 📚 Materiais e Recursos

- [Slides Redes Neurais Convolucionais](4_Período/aulão_cnn.pdf)  
- [Notebook Aplicação Multiclasse](4_Período/clouds.ipynb)  
- [Extras sobre Utilização](4_Período/multiclass.pdf)  
- [Notebook Extras](4_Período/more_examples.ipynb)  

---

### 📝 Desafio — 4º Período: CNNs

- Implementar e treinar CNN para tarefas de visão computacional.  
- Explorar camadas convolucionais, pooling, ativação e regularização.  
- Aplicar técnicas para evitar overfitting.  
- Utilizar frameworks como TensorFlow, Keras ou PyTorch.

- [Desafio de Redes Neurais Convolucionais](4_Período/Atividade.pdf)
# 📅 5º Período — Apresentações (02/06 – 09/06)

Nesta etapa, os grupos apresentam um modelo de IA, mostrando todo o aprendizado adquirido nos períodos anteriores. É o momento de **compartilhar conhecimento, resultados e experiências.**


## 🎯 Objetivos das Apresentações

- **Comunicar ideias com clareza:** Explicar conceitos e processos de forma objetiva e compreensível.  
- **Demonstrar aplicações práticas:** Mostrar como os modelos estudados podem ser aplicados em situações reais.  
- **Analisar criticamente:** Apontar pontos fortes, limitações e possíveis melhorias do modelo ou abordagem.  
- **Engajar o público:** Incentivar perguntas, reflexões e discussões construtivas.  



## 💡 Importância desta etapa

O 5º período é o **clímax do ciclo de aprendizado**, permitindo que cada grupo **sintetize e compartilhe todo o conhecimento adquirido**, além de exercitar habilidades essenciais de comunicação, trabalho em equipe e análise crítica de modelos de Inteligência Artificial e aprendizado de máquina.
