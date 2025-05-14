# 🌤️ DataClima — Coleta Inteligente de Dados Climáticos com Airflow

Este projeto utiliza o Apache Airflow para automatizar a coleta, tratamento e exportação de previsões climáticas da [Visual Crossing Weather API](https://www.visualcrossing.com/weather-api/), com foco no **planejamento estratégico de viagens para empresas do setor de turismo**.

---

## ✈️ Objetivo

Permitir que agências de turismo consultem previsões meteorológicas de forma automatizada e confiável, facilitando o agendamento de passeios, escolha de destinos e redução de riscos causados por eventos climáticos adversos.

---

## ⚙️ Tecnologias Utilizadas

- [Python 3.10+](https://www.python.org/)
- [Apache Airflow](https://airflow.apache.org/)
- [Visual Crossing Weather API](https://www.visualcrossing.com/weather-api/)
- [Pandas](https://pandas.pydata.org/) para tratamento de dados
- `.env` para variáveis de ambiente (como a chave da API)

---

## 🗂️ Estrutura do Projeto

```bash
📦 data-clima/
├── dags/
│   └── extract_climatic_data.py         # DAG principal do Airflow
├── requirements.txt                     # Dependências do projeto
├── .env                                 # Chave da API (não versionado)
├── .gitignore
└── README.md
```

## 🚀 Como Executar o Projeto

1. Clone o repositório
   
```bash
git clone https://github.com/seu-usuario/data-clima.git
cd data-clima
```
2. Crie e ative um ambiente virtual
   
```bash
python -m venv env
source env/bin/activate  # Linux/macOS
.\env\Scripts\activate   # Windows
```
4. Instale as dependências
   
```bash
Copiar
Editar
pip install -r requirements.txt
```

6. Configure a variável de ambiente
Crie um arquivo .env com a seguinte estrutura:

API_KEY=coloque_sua_api_key_aqui

5. Inicie o Airflow
Certifique-se de que o Airflow está corretamente configurado. Siga os passos abaixo caso seja sua primeira execução:

```bash
export AIRFLOW_HOME=$(pwd)/airflow
airflow standalone
```
Em seguida, inicie o webserver e o scheduler:

```bash
Acesse: http://localhost:8080
```
# 🧠 Funcionamento da DAG

A DAG coleta_clima.py realiza os seguintes passos:

Coleta: Requisição de dados da API da Visual Crossing.

Transformação: Conversão e limpeza dos dados climáticos.

Exportação: Salvamento local (CSV) ou envio para outro sistema.

Agendamento: A DAG pode ser configurada para rodar diariamente ou conforme necessidade.

# 📈 Exemplo de Uso

A empresa de turismo pode usar os dados gerados para:

Evitar passeios em dias chuvosos.

Oferecer destinos alternativos com melhor clima.

Criar campanhas promocionais com base no tempo previsto.

# ✅ Requisitos

Conta na Visual Crossing com uma chave de API válida.

Python 3.10 ou superior.

Airflow configurado localmente.
