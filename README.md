
# 🚗 Road Surface Classification with Deep Learning

Projeto de Visão Computacional para classificação de tipos de superfície de vias (asfalto, blocos e off-road) utilizando redes neurais convolucionais (ResNet18) com PyTorch.  
O foco do trabalho vai além da acurácia, incluindo análise de robustez, interpretabilidade e shortcut learning.

---

## 📌 Objetivos

- Classificação de superfícies de vias em imagens reais
- Avaliação de generalização com validação cruzada
- Investigação de shortcut learning
- Análise de interpretabilidade com Grad-CAM
- Estudo de robustez com data augmentation e masking espacial

---

## 🧠 Metodologia

- Modelo base: ResNet18 pré-treinada
- Framework: PyTorch
- Validação: GroupKFold (agrupamento por cenários/sensores para evitar data leakage)
- Métricas: Accuracy, F1-score, matriz de confusão
- Interpretação: Grad-CAM
- Experimentos comparativos:
  - Baseline
  - Experimento 1 (masking)
  - Experimento 2 (data augmentation)

---

## 📁 Estrutura do Projeto

```

.
├── notebook.ipynb
├── data/
│   └── raw/
│       ├── train/
│       │   ├── asphalt/
│       │   ├── belgian_blocks/
│       │   └── offroad/
│       └── test/
│           ├── asphalt/
│           ├── belgian_blocks/
│           └── offroad/
│
├── experiments/
│   ├── baseline/
│   ├── exp_1/
│   ├── exp_2/
│   └── test/
│
└── README.md

```

---

## ⚙️ Estrutura dos Experimentos

### 📊 Baseline / Exp 1 / Exp 2

Cada experimento contém:

```

experiments/<exp_name>/
├── config.json
├── splits.pkl
├── fold_0/
│   ├── model.pt
│   ├── history.json
│   ├── metrics.json
├── fold_1/
│   ├── model.pt
│   ├── history.json
│   ├── metrics.json
├── fold_2/
│   ├── model.pt
│   ├── history.json
│   ├── metrics.json
├── fold_3/
│   ├── model.pt
│   ├── history.json
│   ├── metrics.json
├── fold_4/
│   ├── model.pt
│   ├── history.json
│   ├── metrics.json

```

---

### 🧪 Test Experiment

O experimento final de teste não utiliza folds:

```

experiments/test/
├── config.json
├── model.pt
├── history.json
├── metrics.json
├── test_inference.json

```

---

## 📈 Resultados

Os experimentos incluem:
- Comparação entre baseline e variações
- Avaliação por fold
- Avaliação final em conjunto de teste independente
- Análise qualitativa com Grad-CAM

---

## 🔍 Principais Insights

- Forte presença de shortcut learning em diferentes configurações
- Sensibilidade do modelo a condições de iluminação (especialmente imagens noturnas)
- Classe majoritária tende a absorver erros das demais
- Masking e augmentation influenciam o padrão de atenção, mas não eliminam completamente vieses

---

## 🚀 Tecnologias

- PyTorch
- NumPy
- OpenCV
- Matplotlib
- Scikit-learn

---

## 📎 Repositório

🔗[link](https://drive.google.com/drive/folders/1eCieFEvOu3ol4mTCwWqQfbU1UceukLRC?usp=sharing)

