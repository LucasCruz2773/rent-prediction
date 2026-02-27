# Property Value Prediction (Previsão de Aluguel)

Projeto de **Machine Learning** para previsão do valor de aluguel de imóveis com base em características como área, número de quartos, idade do imóvel, garagem e localização. Desenvolvido no contexto da Trilha IA da Rocketseat.

## Sobre o projeto

O repositório contém:

- **Análise e modelagem** (`rent_prediction.ipynb`): exploração dos dados, pré-processamento, treinamento de um modelo de regressão linear (scikit-learn Pipeline) e avaliação. O modelo treinado é salvo em `rent_model.pkl`.
- **App interativo** (`app_gradio_rent.ipynb`): interface web com [Gradio](https://gradio.app/) para prever o valor do aluguel a partir dos inputs do usuário (área, quartos, idade da casa, garagem, localização).

### Dados

O dataset (`datasets/dataset_aluguel.csv`) possui as colunas:

| Coluna | Descrição |
|--------|-----------|
| `tamanho_m2` | Área em m² |
| `n_quartos` | Número de quartos |
| `idade_casa` | Idade do imóvel (anos) |
| `garagem` | Presença de garagem (0/1) |
| `localizacao_Periferia` | Indicador de localização na periferia |
| `localizacao_Subúrbio` | Indicador de localização no subúrbio |
| `valor_aluguel` | Valor do aluguel (target) |

## Pré-requisitos

- **Python 3.11**
- [Pipenv](https://pipenv.pypa.io/) (ou use o `Pipfile` como referência para instalar dependências com `pip`)

## Instalação

1. Clone o repositório e entre na pasta do projeto:

```bash
git clone <url-do-repositorio>
cd property-value-prediction
```

2. Crie o ambiente e instale as dependências com Pipenv:

```bash
pipenv install
pipenv shell
```

Ou, com `pip`:

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# Linux/macOS:
# source .venv/bin/activate
pip install -r requirements.txt
```

> Se não existir `requirements.txt`, gere com: `pipenv requirements > requirements.txt`

## Uso

### Treinar o modelo

1. Abra o notebook `rent_prediction.ipynb` no Jupyter ou no VS Code.
2. Execute todas as células para carregar os dados, treinar o modelo e salvar `rent_model.pkl` na raiz do projeto.

### Rodar o app Gradio

1. Certifique-se de que o arquivo `rent_model.pkl` existe (rode o notebook de predição antes, se necessário).
2. Abra `app_gradio_rent.ipynb` e execute as células. A última célula sobe a interface do Gradio (geralmente em `http://127.0.0.1:7860`).
3. Use os controles (área, quartos, idade da casa, garagem, localização) e veja o valor do aluguel previsto.

## Tecnologias

- **Python 3.11**
- **pandas** – manipulação de dados
- **scikit-learn** – pipeline de pré-processamento e regressão linear
- **matplotlib / seaborn** – visualizações
- **Gradio** – interface web para o modelo
- **joblib** – serialização do modelo (`rent_model.pkl`)
- **scipy / pingouin** – análises estatísticas (no notebook de predição)

## Estrutura do repositório

```
property-value-prediction/
├── datasets/
│   └── dataset_aluguel.csv
├── rent_prediction.ipynb      # EDA, treino e salvamento do modelo
├── app_gradio_rent.ipynb      # App Gradio para previsão
├── rent_model.pkl             # Modelo salvo (gerado ao rodar rent_prediction.ipynb)
├── Pipfile
├── Pipfile.lock
└── README.md
```

## Licença

Projeto de estudo. Sinta-se à vontade para usar e adaptar.
