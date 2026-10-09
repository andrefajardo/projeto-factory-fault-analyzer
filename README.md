# SCTEC - Projeto Final — Módulo 01 | Machine Learning: Modelo Preditivo
**DESENVOLVIMENTO DE IA PARA ANÁLISE PREDITIVA**

> **Projeto:** `projeto-factory-fault-analyzer`  
> **Autor:** André Fajardo  
> **Programa:** SCTEC — Curso de Desenvolvimento de IA para Análise Preditiva  

---

## 📌 1. Visão Geral do Projeto & Descrição do Notebook

Este repositório implementa um **Pipeline Preditivo completo aplicado à Indústria 4.0**. O algoritmo propõe uma solução preditiva para um parque fabril monitorado por sensores, prevendo quebras mecânicas nos equipamentos para evitar paradas na linha de produção.

* **Variável Alvo:** Binária (`falha_maquina = 1` quando há uma avaria detectada e `falha_maquina = 0` para funcionamento normal).
* **Desafio Estatístico:** A base de dados apresenta alto desbalanceamento de classe (~96,6% de operabilidade normal vs. ~3,4% de falhas).

### 💡 Sobre a Base de Dados
A base foi disponibilizada com problemas propositais — valores nulos, registros duplicados, colunas com potencial de vazamento de dados (*data leakage*) e forte desbalanceamento — visando exercitar capacidades reais de avaliação, diagnóstico e tomada de decisão técnica.

### 📹 Vídeo de Demonstração

* 🎬 **Link da Apresentação:** [Clique aqui para o download do vídeo da apresentação](https://drive.google.com/file/d/11snvmloSHcnmrT0xfRrfJOvMOKBpZkeU/view?usp=sharing)  

### ⚠️ Observações Acadêmicas e Didáticas
* **Idioma no Git:** Por diretriz do projeto acadêmico, todas as mensagens de versionamento no Git/GitHub foram padronizadas em **inglês**.
* **Estrutura Granular:** O notebook possui um número elevado de células para isolar trechos específicos de código e permitir um maior detalhamento teórico e prático por meio de comentários.
* **Projeto Modelo:** Devido às mesmas razões acadêmicas, o projeto demandou uma quantidade elevada de comentários, que tornam mais efetivo o foco no aprendizado.
* **Tecnologias:** O projeto foi desenvolvido utilizando o VSCode como IDE, notebooks Jupyter e fazendo uso de um ambiente virtual, para garantir o isolamento (.venv).

---

## 🧠 2. Conceitos e Técnicas Aplicadas

* **Divisão Treino/Teste com Estratificação:** Uso de `stratify=y` para preservar a proporção da classe minoritária (falhas) nos conjuntos divididos.
* **Balanceamento de Classes:** Aplicação do método SMOTE **apenas no conjunto de treino**, evitando o vazamento de informações (*data leakage*) para o teste.
* **Escalonamento Seletivo:** Padronização com `StandardScaler` aplicada exclusivamente ao KNN, preservando os dados originais para a Árvore de Decisão.
* **Ajuste de Hiperparâmetros & Overfitting:** Análise da variação de `n_neighbors` (KNN) e `max_depth` (Árvore de Decisão) com curvas de acurácia (Treino vs. Teste).
* **Avaliação Crítica de Métricas:** Análise de matrizes de confusão e do **Recall da classe crítica (`falha_maquina = 1`)**, demonstrando por que a acurácia bruta pode mascarar a ineficácia do modelo na detecção de quebras raras.

---

## 📂 3. Estrutura do Repositório (Hierarquia de Pastas)

⚠️ **Atenção:** A execução correta deste projeto exige a manutenção rigorosa da estrutura manual de pastas conforme ilustrada abaixo:

```text
projeto-factory-fault-analyzer/
│
├── data/
│   └── manutencao_preditiva.csv        # Dataset utilizado para treino e teste
│
├── docs/
│   ├── anotações do Departamento de Enge...
│   ├── Fundamentos de Dados, Programaçã...
│   └── manutencao_preditiva.csv
│
├── fault-analyzer/
│   └── faultAnalyzer.ipynb            # Notebook principal do pipeline ML
│
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md                           # Documentação do projeto
└── requirements.txt                    # Dependências do ambiente Python