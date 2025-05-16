
# 🧠 Classificação de Imagens por Raça com Keras

Este projeto é parte de uma atividade prática do curso de **Machine Learning da Pretalab**, e tem como objetivo realizar a **classificação binária de imagens de rostos humanos** a partir de uma URL. O modelo treinado identifica se a imagem pertence à classe `Branca` ou `Preta`, com base em um dataset pré-processado (não incluído neste repositório).

A aplicação simula um processo de inferência real com imagens externas e retorna a classe predita, a confiança da predição e as probabilidades de cada categoria.

---

## 📌 Contexto Geral

Durante o curso, aprendemos a:

- Treinar modelos com Keras para classificação binária
- Preparar imagens para entrada em redes convolucionais
- Realizar inferência em imagens externas via URL
- Interpretar saídas de modelos `.h5`

Este repositório apresenta o **fluxo completo de carregamento, processamento e predição** de uma imagem externa.

---

## 🛠 Tecnologias Utilizadas

- [Python 3.8+](https://www.python.org/)
- [TensorFlow 2.x (Keras)](https://www.tensorflow.org/)
- [Matplotlib](https://matplotlib.org/)
- [NumPy](https://numpy.org/)
- [Pillow (PIL)](https://python-pillow.org/)
- [Requests](https://docs.python-requests.org/)
- [Google Colab / Jupyter Notebook](https://colab.research.google.com/)
- `nbformat` e `nbconvert` para manipulação de notebooks

---

## 🚀 Como Executar o Projeto

### 1. Clone este repositório

```bash
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo
```

### 2. (Opcional) Crie um ambiente virtual

```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
venv\Scripts\activate     # Windows
```

### 3. Instale as dependências

```bash
pip install tensorflow pillow matplotlib requests nbformat
```

### 4. Execute o notebook no Jupyter ou no Google Colab

- **Localmente**:
  ```bash
  jupyter notebook notebook_limpo.ipynb
  ```

- **Ou no Colab**:
  Abra o notebook diretamente no [Google Colab](https://colab.research.google.com/) e carregue o modelo `.h5` pelo Drive ou upload manual.

---

## 📁 Estrutura do Projeto

```
├── modelo_classificacao_racial.h5       # Modelo treinado (arquivo externo, não incluído)
├── notebook_limpo.ipynb                 # Notebook de inferência corrigido (sem erros de widgets)
├── limpar_widgets.py                    # Script que remove metadados corrompidos
├── README.md                            # Documentação do projeto
```

---

## 🖼️ Fluxo de Classificação

A função principal utilizada é `test_image_from_url(img_url)`. Ela realiza as seguintes etapas:

1. **Faz o download** da imagem via `requests`
2. **Converte** para RGB (se necessário)
3. **Redimensiona** para 224x224 pixels
4. **Normaliza os pixels** no intervalo `[0, 1]`
5. **Faz a predição** com o modelo `.h5`
6. **Retorna**:
   - Classe predita: `Branca` ou `Preta`
   - Nível de confiança da predição
   - Probabilidade de cada classe

---

## ⚠️ Observações

- O modelo `modelo_classificacao_racial.h5` **não está incluído no repositório** por questões de privacidade e espaço.  
  Para executar corretamente, você deve:
  - Treinar seu próprio modelo
  - Ou solicitar o arquivo via instrução do curso

- O script `limpar_widgets.py` pode ser usado para **remover metadados corrompidos** de notebooks `.ipynb` que quebram a visualização no GitHub (erro `'metadata.widgets' missing 'state'`).

---

## 💡 Exemplo de Uso

```python
test_image_from_url("https://exemplo.com/imagem.jpg")
```

Saída esperada:
```
Classe Predita: Branca
Confiança: 85.3%
Probabilidade Branca: 85.3%
Probabilidade Preta: 14.7%
```

---

## ✍️ Autoria

Projeto desenvolvido por **Taís GB** durante o curso de Machine Learning da [Pretalab](https://www.pretalab.com.br).  


---
