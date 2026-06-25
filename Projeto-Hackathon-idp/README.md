# Projeto Hackathon IDP

## Visão Geral

Solução de Intelligent Document Processing (IDP) para automatizar o processamento de sinistros em seguradoras utilizando serviços AWS serverless e Inteligência Artificial.

A solução recebe documentos enviados pelos usuários, realiza classificação automática, extração de informações relevantes, processamento dos dados e armazenamento estruturado para consulta posterior.

## Problema de Negócio

Atualmente, o processamento de sinistros é realizado manualmente, exigindo análise humana de documentos como:

* Formulários de abertura de sinistro
* Boletins de ocorrência
* Laudos técnicos e médicos
* Notas fiscais e orçamentos
* Documentos de identificação
* Comprovantes e recibos

Esse processo é lento, sujeito a erros e possui baixa escalabilidade.

## Objetivo

Automatizar o fluxo de processamento de documentos utilizando serviços AWS, reduzindo o tempo de análise e aumentando a eficiência operacional.

## Arquitetura da Solução

![image alt](https://github.com/GiovaniSerra/Hackathon-EDN-HACK2HIRE-JUN26/blob/main/Projeto-Hackathon-idp/evidence/arq-01.png)

Fluxo principal:

Cliente → API Gateway → Lambda Upload → Amazon S3 → Processamento → DynamoDB

## Serviços AWS Utilizados

* Amazon API Gateway
* AWS Lambda
* Amazon S3
* Amazon DynamoDB
* AWS Step Functions
* Amazon Textract
* Amazon Comprehend
* Amazon Bedrock

## Estrutura do Projeto

## Componentes Implementados

### API Gateway

Responsável por receber requisições de upload de documentos.

### Lambda Upload

Recebe os arquivos enviados e realiza o armazenamento inicial.

### Lambda Classify

Classifica os documentos utilizando serviços de IA.

### Lambda Analyze

Executa a análise e extração de informações relevantes.

### Lambda Process

Realiza tratamento e normalização dos dados extraídos.

### Lambda AnalyzeClaim

Processa informações relacionadas ao sinistro.

### DynamoDB

Armazena os dados processados e metadados para consulta.

## Evidências

Capturas de tela e testes podem ser encontrados em:

[Evidence](https://github.com/GiovaniSerra/Hackathon-EDN-HACK2HIRE-JUN26/tree/main/Projeto-Hackathon-idp/evidence)

## Licença

Projeto desenvolvido exclusivamente para fins educacionais e participação no Hackathon Escola Da Nuvem HACK2HIRE JUN/2026.

