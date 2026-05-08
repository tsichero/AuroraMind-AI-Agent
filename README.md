# AuroraMind AI Agent

Sistema de Agente Inteligente utilizando LangChain, Python e LLMs para automação, conversação inteligente e integração com IA Generativa.

---

# Visão Geral

O AuroraMind AI Agent é um projeto desenvolvido para construção de agentes inteligentes capazes de:

* interpretar linguagem natural;
* responder perguntas;
* automatizar fluxos;
* integrar APIs;
* utilizar modelos de IA Generativa;
* executar tarefas inteligentes;
* servir como base para copilotos personalizados.

O projeto utiliza arquitetura modular com Python, LangChain e integração com LLMs.

---

# Tecnologias

* Python
* LangChain
* OpenAI API
* FastAPI
* Google Colab
* Docker
* APIs REST
* LLMs
* IA Generativa

---

# Estrutura Inicial do Projeto

```bash
AuroraMind-AI-Agent/
│
├── app/
│   ├── main.py
│   ├── agent.py
│   ├── prompts.py
│   ├── memory.py
│   ├── tools.py
│   └── config.py
│
├── requirements.txt
├── .env
├── README.md
└── dockerfile
```

---

# Funcionalidades Planejadas

* Agente conversacional inteligente
* Memória contextual
* Integração com múltiplos LLMs
* Engenharia de prompts
* Automação de tarefas
* APIs integradas
* Base para copilotos personalizados
* Fluxos inteligentes com IA

---

# Código Inicial do Agente

## app/main.py

```python
from fastapi import FastAPI
from app.agent import run_agent

app = FastAPI()

@app.get("/")
def home():
    return {"message": "AuroraMind AI Agent online 🚀"}

@app.post("/chat")
def chat(user_input: str):
    response = run_agent(user_input)
    return {"response": response}
```

---

## app/agent.py

```python
from langchain_openai import ChatOpenAI
from langchain_core.prompts import ChatPromptTemplate
from dotenv import load_dotenv
import os

load_dotenv()

llm = ChatOpenAI(
    model="gpt-4o-mini",
    temperature=0.7,
    api_key=os.getenv("OPENAI_API_KEY")
)

prompt = ChatPromptTemplate.from_template(
    "Você é AuroraMind, uma IA inteligente e útil. Responda: {input}"
)

chain = prompt | llm


def run_agent(user_input):
    response = chain.invoke({"input": user_input})
    return response.content
```

---

## app/config.py

```python
import os
from dotenv import load_dotenv

load_dotenv()

OPENAI_API_KEY = os.getenv("OPENAI_API_KEY")
```

---

## .env

```env
OPENAI_API_KEY=sua_chave_aqui
```

---

# Instalação

```bash
pip install -r requirements.txt
```

---

# Requirements

```txt
langchain
openai
fastapi
uvicorn
python-dotenv
```

---

# Objetivo do Projeto

Desenvolver uma arquitetura moderna de agentes inteligentes utilizando IA Generativa, permitindo aplicações em automação, produtividade, educação, saúde e copilotos personalizados.

---

# Autor

Tainã Sichero Dulcetti

LinkedIn:
[https://www.linkedin.com/in/tainã-sichero-dulcetti-65270b149/](https://www.linkedin.com/in/tainã-sichero-dulcetti-65270b149/)

GitHub:
[https://github.com/tsichero](https://github.com/tsichero)

