# 🧠 Transfer Learning com MobileNetV2 – Classificação Dogs vs Cats

Projeto desenvolvido como desafio da plataforma **DIO – Digital Innovation One**

---

## 📌 Sobre o Projeto

Este projeto aplica **Transfer Learning** utilizando a arquitetura **MobileNetV2** para realizar uma tarefa de classificação binária:
**identificar se uma imagem contém um gato ou um cachorro**.

O trabalho foi realizado no **Google Colab**, seguindo as instruções da DIO para demonstrar:

* Uso de redes pré-treinadas
* Construção de um modelo customizado
* Fine-tuning (ajuste fino da rede)
* Avaliação do desempenho
* Documentação clara do processo

---

## 🎯 Objetivos do Desafio

Ao concluir este projeto, o aluno deve demonstrar:

* Compreensão do conceito de **Transfer Learning**
* Capacidade de ajustar modelos pré-treinados para novas tarefas
* Organização e documentação técnica no GitHub
* Execução do pipeline completo de Machine Learning:

  * Carregamento do dataset
  * Pré-processamento
  * Construção do modelo
  * Treinamento
  * Fine-tuning
  * Salvamento do modelo
  * Registro dos resultados

---

## 📂 Dataset Utilizado

Foi usado o dataset **Cats vs Dogs**, disponível no TensorFlow Datasets (TFDS).

* Número total de imagens: **23.262**
* Classes:

  * `0` → Gatos
  * `1` → Cachorros

As imagens foram:

* Redimensionadas para **150×150**
* Normalizadas para `[0, 1]`
* Divididas em:

  * **80% treino**
  * **20% validação**

---

## 🏗️ Arquitetura do Modelo

Foi utilizada a rede **MobileNetV2 pré-treinada com ImageNet**, com:

* `include_top=False` (remoção da cabeça original do modelo)
* Camadas da base inicialmente **congeladas**
* Adicionadas camadas acima:

  * GlobalAveragePooling2D
  * Dense(1) (classificação binária)

Após o primeiro treinamento, a base foi **descongelada** para fine-tuning.

---

## 🚀 Passo a Passo do Projeto

### ✔️ 1. Importação das Bibliotecas

TensorFlow, Keras, TFDS, Matplotlib, NumPy.

### ✔️ 2. Carregamento e divisão do dataset

O dataset foi embaralhado e dividido em treino e validação.

### ✔️ 3. Pré-processamento

* Redimensionamento
* Normalização
* Batching
* Prefetch para acelerar o pipeline

### ✔️ 4. Criação do modelo base (MobileNetV2)

Base carregada com pesos pré-treinados e sem o topo.

### ✔️ 5. Congelamento da base

Primeiro treinamento apenas do topo.

### ✔️ 6. Treinamento inicial

Treinado por **5 épocas** para estabilização da cabeça do modelo.

### ✔️ 7. Descongelamento da base

Para permitir o fine-tuning completo.

### ✔️ 8. Novo compile com learning rate menor

Treinamento mais suave da base.

### ✔️ 9. Fine-tuning

Treinamento final por **5 épocas** adicionais.

### ✔️ 10. Salvamento do modelo

Arquivo gerado no formato:

```
modelo_transfer_learning.h5
```

---

## 📈 Resultados Obtidos

Os resultados podem variar por execução, mas normalmente:

* **Acurácia de treino:** 93% ~ 98%
* **Acurácia de validação:** 90% ~ 96%

Esses valores demonstram que o transfer learning foi usado de forma eficaz.

---

## 🧪 Como executar este projeto

1. Abra o Google Colab
2. Faça upload do notebook ou importe pelo GitHub
3. Execute célula por célula
4. Certifique-se de que o TFDS será baixado no início
5. Ao final, o modelo estará salvo automaticamente

---

## 🗂️ Estrutura do Repositório

```
📁 transfer-learning-cats-vs-dogs/
│
├── 📄 README.md               # Documentação do projeto
├── 📄 notebook.ipynb          # Notebook do Google Colab
└── 📁 images/                 # (Opcional) prints do processo
```

---

## 💡 Prints recomendados (opcional)

Coloque na pasta `/images`:

* print do summary()
* gráfico accuracy/loss
* print do Colab rodando
* print do arquivo salvo

Isso gera mais pontos com a DIO.

---

## 📚 Tecnologias Utilizadas

* Python
* TensorFlow
* TensorFlow Datasets
* Google Colab
* MobileNetV2
* Keras

---

## 👤 Autor

**Felipe Fuentes**

Projeto desenvolvido para o bootcamp da **Digital Innovation One – DIO**.

---
