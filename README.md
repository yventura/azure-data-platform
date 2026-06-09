# ☁️ Azure Data Platform (ETL + IaC)

Projeto de arquitetura de dados em ambiente Microsoft Azure, integrando pipeline de dados (ETL) e automação de infraestrutura como código (IaC) com PowerShell DSC.

---

## 🎯 Objetivo do Projeto

Construir um ambiente cloud completo simulando uma plataforma de dados, incluindo:

- Pipeline de dados (ETL)
- Armazenamento e processamento em Azure
- Automação de infraestrutura de servidor Windows
- Configuração de serviços via infraestrutura como código

O objetivo é demonstrar conceitos de engenharia de dados e cloud computing aplicados a um cenário real.

---

## 🏗️ Arquitetura da Solução

O projeto é dividido em duas camadas principais:

### 📊 Camada de Dados (Data Platform)
- Ingestão de dados
- Armazenamento em Data Lake
- Processamento e transformação
- Carga em base estruturada (SQL)
- Preparação para análise

### 🖥️ Camada de Infraestrutura (IaC)
- Provisionamento de VM Windows
- Instalação e configuração automática de IIS (Web Server)
- Garantia de serviços ativos via DSC (Desired State Configuration)

---

## ⚙️ Tecnologias Utilizadas

### Cloud & Data
- Microsoft Azure Data Factory
- Azure Data Lake Storage
- Azure SQL Database
- SQL

### Infraestrutura como Código (IaC)
- PowerShell DSC
- Windows Server
- IIS (Web Server)

---

## 🔄 Pipeline de Dados (ETL)

1. Ingestão de dados na Azure
2. Armazenamento em Data Lake (camada raw)
3. Transformação dos dados
4. Carga em banco relacional (Azure SQL)
5. Disponibilização para consumo analítico

---

## 🖥️ Automação de Infraestrutura

Foi utilizado PowerShell DSC para garantir estado desejado da máquina:

- Instalação automática do IIS (Web Server)
- Configuração do serviço w3svc
- Inicialização automática do serviço
- Garantia de consistência da infraestrutura

---

### 🔧 Script DSC utilizado

```powershell id="dsc-script"
configuration ConfigureVM
{
    param (
        [string[]]$NodeName = 'localhost'
    )

    Node $NodeName
    {
        WindowsFeature IIS
        {
            Name = "Web-Server"
            Ensure = "Present"
        }

        Service IISService
        {
            Name = "w3svc"
            StartupType = "Automatic"
            State = "Running"
            DependsOn = "[WindowsFeature]IIS"
        }
    }
}

ConfigureVM -OutputPath "C:\DSC\ConfigureVM"
