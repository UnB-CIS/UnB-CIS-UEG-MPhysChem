# Curso Avançado de IA Aplicada à Química <br> IEEE UnB CIS / CCET UEG Lab MPhysChem 🧪🤖

Bem-vindos ao repositório oficial do **Curso Avançado de IA Aplicada à Química**! Aqui você encontrará todos os materiais, notebooks e exercícios referentes aos 4 dias de imersão em deep learning para descoberta e design molecular.

## Objetivo do Curso

Capacitar químicos e pesquisadores na utilização de técnicas avançadas de machine learning e deep learning para:
- Predição de propriedades moleculares
- Descoberta de novos compostos químicos
- Otimização de reações e processos
- Aplicação de Graph Neural Networks (GNNs) em química computacional

## Sumário

- [Dia 1](#dia-1)
- [Dia 2](#dia-2)
- [Dia 3 — Graph Neural Networks e Message Passing Neural Networks](#dia-3--graph-neural-networks-e-message-passing-neural-networks)
- [Dia 4](#dia-4)
- [Trabalho Final](#trabalho-final)

---

<!-- Dia 1 -->
<a name="dia-1"></a>
# 📅 Dia 1


---

<!-- Dia 2 -->
<a name="dia-2"></a>
# 📅 Dia 2 - Machine Learning e QSAR

## 1. Módulo 1: Coleta e Manipulação de Dados 🧬
**Foco:** O "Hello World" da Química Digital.
Aprendemos a transformar nomes de remédios em estruturas manipuláveis pelo computador.
* **Principais Tópicos:**
    * Uso do **PubChemPy** para baixar estruturas químicas automaticamente.
    * Manipulação de objetos `Mol` com **RDKit**.
    * Cálculo de propriedades físico-químicas (Peso Molecular, LogP, Doadores/Aceitadores de H).
    * Aplicação prática da **Regra dos 5 de Lipinski** para avaliar candidatos a fármacos orais.

## 2. Módulo 2: Representação Molecular e Similaridade 🔍
**Foco:** Traduzindo Química para Matemática.
Como o computador "enxerga" uma molécula? Transformamos desenhos em vetores numéricos.
* **Principais Tópicos:**
    * Geração de **Morgan Fingerprints** (ECFP4) para capturar subestruturas químicas.
    * Entendimento de vetores de bits (0s e 1s).
    * Cálculo de **Similaridade de Tanimoto**: comparando o quão parecidas duas moléculas são matematicamente.
    * Matriz de Distância para agrupar moléculas similares.

## 3. Módulo 3: Machine Learning I - Regressão (Solubilidade) 💧
**Foco:** Prevendo números exatos ($\Delta G_{solv}$).
Construção de um modelo para prever a Energia de Solvatação (o quão solúvel uma molécula é).
* **Pipeline:**
    * Limpeza de dados com `SaltRemover` (removendo íons e impurezas).
    * Divisão de dados (Treino vs Teste).
    * Treinamento de **Regressão Linear**.
    * Avaliação com **RMSE** (Raiz do Erro Quadrático Médio) e gráficos de dispersão.

## 4. Módulo 4: Machine Learning II - Classificação (Anti-HIV) 🦠
**Foco:** Triagem Virtual (Sim/Não).
O desafio final: identificar moléculas ativas contra o HIV em um dataset desbalanceado.
* **Pipeline:**
    * Análise de desbalanceamento de classes (Ativos vs Inativos).
    * Treinamento de **Random Forest** com pesos ajustados (`class_weight='balanced'`).
    * Avaliação avançada: Por que a Acurácia engana? Uso de **Matriz de Confusão, Precision, Recall e Curva ROC-AUC**.

## 🛠️ Ferramentas Utilizadas

- **Linguagem:** Python 3
- **Quimioinformática:** RDKit, PubChemPy
- **Data Science:** Pandas, Numpy
- **Machine Learning:** Scikit-Learn
- **Visualização:** Matplotlib, Seaborn

---

## 📚 Materiais do Dia 2
- [Slides - Módulo 1: Coleta de Dados e Lipinski](Dia_2/Slides_Modulo1.pdf)
- [Notebook - Módulo 1: PubChem e Manipulação de Dados](Dia_2/Modulo1_Dados.ipynb)
- [Slides - Módulo 2: Representação Molecular](Dia_2/Slides_Modulo2.pdf)
- [Notebook - Módulo 2: Fingerprints e Similaridade](Dia_2/Modulo2_Fingerprints.ipynb)
- [Slides - Módulo 3: Regressão e Solubilidade](Dia_2/Slides_Modulo3.pdf)
- [Notebook - Módulo 3: Prática de Solvatação (Regressão)](Dia_2/Modulo3_Regressao.ipynb)
- [Slides - Módulo 4: Classificação e Triagem Virtual](Dia_2/Slides_Modulo4.pdf)
- [Notebook - Módulo 4: Desafio Anti-HIV (Random Forest)](Dia_2/Modulo4_HIV.ipynb)
<!-- Dia 3 -->
<a name="dia-3"></a>
# 📅 Dia 3 — Graph Neural Networks e Message Passing Neural Networks

## Por que Deep Learning para Química?

- Captura relações não-lineares complexas
- Aprendizado automático de features relevantes
- Generalização para novos espaços químicos

## Moléculas como Grafos

**Representação estrutural:**
- **Vértices (Nodes):** Átomos (tipo, carga, hibridização)
- **Arestas (Edges):** Ligações químicas (ordem, tipo)
- **SMILES → Grafo:** Conversão usando RDKit

## Message Passing Neural Networks (MPNNs)

**Conceito:** Propagação de informações entre átomos vizinhos → Agregação de mensagens locais → Representação molecular global

**Arquitetura D-MPNN:**
1. Codificação inicial de features
2. Message Passing dirigido (baseado em ligações)
3. Agregação (pooling)
4. Predição via rede feed-forward

**Vantagens:**
- Evita "totters" (loops desnecessários)
- Maior estabilidade numérica
- Melhor captura de informações direcionais

## Arquiteturas GNN

- **MPNN:** Base para arquiteturas modernas
- **GCN:** Convolução em grafos
- **GAT:** Mecanismos de atenção
- **SchNet:** Features 3D (distâncias interatômicas)
- **DimeNet:** Ângulos diedrais

**Formalização matemática:**
```
Fase de Mensagem: m_ij = φ(h_i, h_j, e_ij)
Fase de Agregação: h_i' = γ(h_i, Σ_{j∈N(i)} m_ij)
```

## GNNs vs. Métodos Tradicionais

| Aspecto | Fingerprints + ML | D-MPNN/GNN |
|---------|-------------------|------------|
| **Features** | Fixas, pré-definidas | Aprendidas automaticamente |
| **Generalização** | Limitada | Melhor para novos scaffolds |
| **Dados necessários** | Poucos | Datasets maiores |
| **Interpretabilidade** | Alta | Moderada (attention) |
| **Performance** | Boa (tarefas simples) | Superior (tarefas complexas) |

## Chemprop

- Implementação otimizada de D-MPNNs
- Interface simplificada para químicos
- Transfer learning, ensemble, interpretabilidade

## Aplicações Reais

1. **Descoberta de Antibióticos:** Halicin (D-MPNN contra *E. coli* resistente)
2. **Propriedades Quânticas:** Aceleração de cálculos DFT
3. **Síntese Retrossintética:** Planejamento de rotas sintéticas

## Técnicas

- **Transfer Learning:** Pré-treino + fine-tuning
- **Representação Híbrida:** GNN + descritores RDKit
- **Ensemble Methods:** Agregação de múltiplos modelos
- **Uncertainty Quantification:** Confiança nas predições

## Frameworks

- **PyTorch Geometric (PyG):** Modular, flexível
- **DGL:** Escalável, TensorFlow/PyTorch
- **Chemprop:** Especializado em química, estado-da-arte

---

## 📚 Materiais do Dia 3

- [Slides - GNNs e MPNNs](Dia_3/slides_gnns_mpnn.pdf)
- [Notebook - Construindo Grafos Moleculares](Dia_3/grafos_moleculares.ipynb)
- [Notebook - Treinando D-MPNN](Dia_3/treinando_dmpnn.ipynb)
- [Notebook - PyTorch Geometric](Dia_3/gnn_pyg.ipynb)
- [Notebook - Transfer Learning](Dia_3/transfer_learning.ipynb)
- [Notebook - Análise de Atenção](Dia_3/attention_analysis.ipynb)
- [Tutorial Chemprop](Dia_3/tutorial_chemprop.pdf)
- [Paper: Halicin Discovery](Dia_3/papers/halicin_discovery.pdf)

## 📝 Exercício para Casa — Dia 3

**Objetivo:** Pipeline completo de GNN para descoberta de inibidores enzimáticos.

**Dataset:** Inibidores de protease (fornecido)

**Tarefas:**
1. **Exploração:** Análise do espaço químico, scaffolds, distribuição de atividades
2. **Modelagem:** D-MPNN base, representação híbrida, transfer learning
3. **Avaliação:** Split por scaffold, comparação com baseline (RF + Morgan)
4. **Interpretabilidade:** Attention weights, features importantes
5. **Virtual Screening:** Ranquear candidatos, análise de diversidade

**Desafio Extra:** Implementar GNN do zero (PyTorch) e comparar com Chemprop

- [📄 Exercício Completo](Dia_3/exercicio_inibidores.pdf)
- [📦 Dataset](Dia_3/dataset_inibidores.zip)

---

<!-- Dia 4 -->
<a name="dia-4"></a>
# 📅 Dia 4


---

<!-- Trabalho Final -->
<a name="trabalho-final"></a>
# Trabalho Final

### 1. GNNs para Cálculos Quânticos (QM/ML)

**Potenciais de ML:** ANI, SchNet, PhysNet, PaiNN  
**Framework MLatomom:** Integração com Gaussian/ORCA/Psi4  
**Aplicação:** Setup no cluster UEG, comparação QM vs. QM/ML

### 2. Generative Models para Design Molecular

**Abordagens:** VAE, GAN, Reinforcement Learning, Diffusion Models  
**Graph-based Generation:** Geração sequencial garantindo valência química

## Projeto Final em Grupo

**Formação:** Grupos de 2-3 pessoas

### Opção 1: Descoberta de Moléculas Bioativas
Identificar potenciais inibidores para alvo terapêutico específico.

**Entregáveis:** Código completo, relatório (10-15 páginas), top 20 candidatos, apresentação (15 min)

### Opção 2: Predição de Propriedades Físico-Químicas
Criar modelo robusto para propriedades como solubilidade, LogP, toxicidade.

**Entregáveis:** Código documentado, benchmark comparativo, análise de features, modelo treinado

### Opção 3: Módulo de Predição para Transitivity 2.0
Desenvolver funcionalidade GNN para o sistema (predição de energia, reatividade, produtos, screening).

**Entregáveis:** Código + API, documentação de integração, testes de performance

### Opção 4: Projeto Livre
Proposta própria envolvendo GNNs aplicadas à química (espectros, síntese retrossintética, catalisadores, materiais).


## Recursos

**Datasets:** MoleculeNet, ChEMBL, PubChem, ZINC15, QM9  
**Ferramentas:** RDKit, Chemprop, PyTorch Geometric, DeepChem, MLatomom  
**Suporte:** Discord/Slack IEEE CIS, office hours, acesso cluster UEG

**Materiais:**
- [Slides - QM/ML e Generative Models](Trabalho_Final/slides_topicos_avancados.pdf)
- [Notebook - MLatomom Tutorial](Trabalho_Final/mlatom_tutorial.ipynb)
- [Notebook - Generative VAE](Trabalho_Final/molecular_vae.ipynb)
- [Template de Projeto](Trabalho_Final/template_projeto.md)
- [Guia de Boas Práticas](Trabalho_Final/boas_praticas_ml_quimica.pdf)

---

## Referências

**Papers:**
1. Stokes et al. (2020) - "A Deep Learning Approach to Antibiotic Discovery"
2. Yang et al. (2019) - "Analyzing Learned Molecular Representations for Property Prediction"
3. Gilmer et al. (2017) - "Neural Message Passing for Quantum Chemistry"
4. Wieder et al. (2020) - "A compact review of molecular property prediction with GNNs"

**Livros:**
- "Deep Learning for the Life Sciences" - Ramsundar et al.
- "Machine Learning in Chemistry" - Engkvist et al.

**Tutoriais:**
- [DeepChem](https://deepchem.io/)
- [PyTorch Geometric](https://pytorch-geometric.readthedocs.io/)
- [Chemprop](https://chemprop.readthedocs.io/)
- [RDKit Cookbook](https://www.rdkit.org/docs/Cookbook.html)


**Bom curso a todos! 🧪**
