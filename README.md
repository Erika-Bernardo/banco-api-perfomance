# 🚀 Banco API Performance Tests com K6

## 📌 Introdução
Este repositório contém testes de performance desenvolvidos para validar a escalabilidade, estabilidade e tempo de resposta da API do projeto **Banco API**.  

Os testes foram implementados utilizando **JavaScript** com o framework **K6**, permitindo simular diferentes cenários de carga e medir o comportamento da aplicação sob stress.

---

## 🛠 Tecnologias Utilizadas
- **JavaScript**
- **K6** – ferramenta para testes de carga e performance
- **Node.js** (opcional, para organização do projeto)

---

## 📂 Estrutura do Repositório

banco-api-performance/
│
├── tests/                
├── fixtures/            
├── helpers/                 
├── utils/                
├── config/               
└── README.md             

---

## 🎯 Objetivo de Cada Grupo de Arquivos

- **tests/**  
  Contém os scripts principais de execução dos testes.

- **utils/**  
  Funções utilitárias reutilizáveis.

- **fixtures/**  
  Armazena dados utilizados nos testes (payloads, listas, etc.).

- **helpers/**  
  Funções reutilizáveis como autenticação, criação de headers, etc.

- **config/**  
  Arquivo de configuração de variáveis de ambiente.

---

## ⚙️ Instalação  do Projeto

### 1. Clone do Repositório
git clone https://github.com/Erika-Bernardo/banco-api-perfomance.git
cd banco-api-perfomance

### 2. Instalar o K6

#### Windows (via Chocolatey)
choco install k6

#### Mac (via Homebrew)
brew install k6

#### Linux
sudo apt install k6

---

## ▶️ Execução dos Testes

### 3. Configure as variáveis de Ambiente

⚠️ Este projeto utiliza uma variável de ambiente obrigatória:

BASE_URL

Ela define a URL base da API a ser testada.

Altere o arquivo "config.local.json" e defina a URL da API a ser testada:

```json
{
    "baseUrl": "http://localhost:3000"
}
```
---

### 🔹 Execução simples

```bash
k6 run tests/seu-teste.js
```

Certifique=se de passar a variável de ambiente `BASE_URL`, caso não esteja usando um `config.local.json` ou uma abordagem de carregamento automático:

```bash
k6 run tests/seu-teste.js -e BASE_URL=http://localhost:3000
```

---

## 📊 Execução com Dashboard em Tempo Real

### Bash
K6_WEB_DASHBOARD=true \
K6_WEB_DASHBOARD_EXPORT=html-report.html \
k6 run tests/seu-teste.js \
-e BASE_URL=http://localhost:3000

### CMD
set "K6_WEB_DASHBOARD=true" && set "K6_WEB_DASHBOARD_EXPORT=html-report.html" && k6 run tests\seu-teste.test.js -e BASE_URL=http://localhost:3000

### PowerShell
$env:K6_WEB_DASHBOARD="true"; $env:K6_WEB_DASHBOARD_EXPORT="html-report.html"; k6 run .\tests\seu-teste.test.js -e BASE_URL=http://localhost:3000

---

## 📈 Exportação de Relatório

Ao utilizar a variável:

K6_WEB_DASHBOARD_EXPORT=html-report.html

Será gerado automaticamente um relatório em HTML ao final da execução.

---

## ✅ Considerações Finais

Este projeto tem como objetivo garantir que a API seja capaz de suportar diferentes níveis de carga, ajudando na identificação de gargalos e garantindo uma melhor experiência para o usuário final.
