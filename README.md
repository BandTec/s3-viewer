# S3 Viewer — Visualizador de Arquivos CSV/JSON do S3

Aplicação **Node.js + Express** para leitura de arquivos (CSV ou JSON) armazenados em **AWS S3**, exibindo seus dados na tela e gerando **gráficos dinâmicos com Chart.js**.

---

## Funcionalidades

* 🔹 Leitura automática de arquivos armazenados no S3
* 🔹 Detecção automática de formato (`JSON`, `CSV` ou `texto puro`)
* 🔹 Exibição de **dados brutos** e **gráficos interativos** (Chart.js)
* 🔹 Suporte tanto para **AWS S3 real**
* 🔹 Configuração simples via **.env**

---

## Estrutura do Projeto

```
📁 s3-viewer
 ┣ 📄 app.js               → Código principal da aplicação
 ┣ 📄 package.json         → Dependências e scripts
 ┣ 📁 views/
 │   ┗ 📄 index.ejs        → Template de visualização de dados
 ┣ 📁 public/
 │   ┗ 📄 style.css        → (opcional) Estilos da página
 ┣ 📄 .env.example         → Modelo de variáveis de ambiente
 ┗ 📄 README.md
```

---

## Pré-requisitos

Antes de começar, instale:

* Node.js (versão 18 ou superior)
* Conta AWS configurada (se for usar S3 real)

---

## Instalação

Clone o repositório e instale as dependências:

```bash
git clone https://github.com/seu-usuario/s3-viewer.git
cd s3-viewer
npm install
```

---

## Configuração das variáveis de ambiente

Crie um arquivo `.env` na raiz do projeto com base no exemplo abaixo:

```bash
# === Config AWS ===
AWS_REGION=sa-east-1
S3_BUCKET=meu-bucket
S3_KEY=exemplo.csv
```

---

## Executando o projeto

### Modo normal:

```bash
npm start
```

### Modo desenvolvimento (com nodemon):

```bash
npm run dev
```

A aplicação ficará disponível em:

**[http://localhost:3000](http://localhost:3000)**

---

##  Como funciona

1. O app conecta ao **AWS S3**.
2. Busca o arquivo indicado (`S3_BUCKET` e `S3_KEY`).
3. Detecta automaticamente se o conteúdo é **JSON**, **CSV** ou **texto simples**.
4. Exibe os dados brutos e, se possível, gera um gráfico automaticamente (para CSVs tabulares).

---

##  Exemplo de gráfico

Se o CSV tiver colunas como:

```csv
aluno;nota
Julia;9
Pedro;7
Henrique;10
```

O app exibirá um gráfico de barras com os alunos no eixo X e as notas no eixo Y, gerado via **Chart.js**.

---

## Tecnologias usadas

| Tecnologia            | Função                                   |
| --------------------- | ---------------------------------------- |
| **Node.js / Express** | Backend e servidor web                   |
| **EJS**               | Template engine                          |
| **Chart.js**          | Visualização gráfica                     |
| **PapaParse**         | Parser CSV                               |
| **AWS SDK**           | Acesso ao S3                             |

---

## Licença

Este projeto está sob a licença **MIT** — sinta-se livre para usar e modificar.
Autor original: **Julia Lima**
