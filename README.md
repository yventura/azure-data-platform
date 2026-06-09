# ☁️ Pipeline de Dados na Azure

Projeto de engenharia de dados na nuvem utilizando serviços da Microsoft Azure para construção de um pipeline ETL (Extract, Transform, Load).

---

## 🎯 Objetivo do Projeto

Este projeto tem como objetivo simular um ambiente real de engenharia de dados, construindo um pipeline para ingestão, armazenamento, transformação e disponibilização de dados na cloud.

O foco é demonstrar habilidades em arquitetura de dados, integração de serviços Azure e modelagem de fluxo de dados.

---

## 🏗️ Arquitetura da Solução

O pipeline foi estruturado seguindo uma abordagem em camadas:

**Fonte de Dados → Ingestão → Armazenamento → Processamento → Consumo**

Fluxo:

1. Ingestão de dados brutos
2. Armazenamento em Data Lake
3. Processamento e transformação dos dados
4. Carga em banco estruturado
5. Disponibilização para análise

---

## ⚙️ Tecnologias Utilizadas

- Microsoft Azure Data Factory (orquestração do pipeline)
- Azure Data Lake Storage (armazenamento de dados brutos)
- Azure SQL Database (camada estruturada de dados)
- SQL (transformação e consultas)
- (Opcional) Power BI para visualização de dados

---

## 🔄 Etapas do Pipeline

### 1. Ingestão de Dados
Os dados são coletados e ingeridos utilizando Azure Data Factory.

### 2. Armazenamento Raw
Os dados são armazenados em estado bruto no Azure Data Lake Storage.

### 3. Processamento
Os dados passam por tratamento, limpeza e transformação utilizando SQL e/ou Data Factory.

### 4. Camada Estruturada
Os dados processados são carregados no Azure SQL Database para consulta e modelagem.

### 5. Consumo
Os dados ficam disponíveis para análise, relatórios ou dashboards.

---

## 📊 Resultado do Projeto

- Pipeline de dados funcional em ambiente cloud
- Separação de camadas (raw / processed / curated)
- Integração entre serviços Azure
- Base estruturada para análise e BI

---

## 💡 Aprendizados

- Conceitos de engenharia de dados em ambiente cloud
- Orquestração de pipelines com Azure Data Factory
- Armazenamento e organização de dados em Data Lake
- Integração entre serviços de dados na Azure
- Noções de arquitetura de dados moderna

---

## 👨‍💻 Autor

Desenvolvido por Yuri Ventura como projeto prático de estudos em Engenharia de Dados e Cloud Computing com Microsoft Azure.
