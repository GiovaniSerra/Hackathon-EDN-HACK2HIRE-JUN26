# Infraestrutura

## Serviços AWS Utilizados

| Serviço                  | Propósito                                                                      |
| ------------------------ | ------------------------------------------------------------------------------ |
| Amazon S3                | Armazenamento seguro de documentos enviados para processamento                 |
| Amazon S3 Vectors        | Armazenamento vetorial e recuperação semântica para RAG                        |
| Amazon Textract          | OCR e extração automática de texto e campos de documentos                      |
| Amazon Comprehend        | Classificação documental, detecção de entidades e análise de linguagem natural |
| Amazon Bedrock           | Modelos fundacionais, geração de respostas e embeddings                        |
| Amazon Bedrock AgentCore | Agente conversacional para consultas sobre sinistros e documentos processados  |
| AWS Lambda               | Processamento serverless e execução das etapas do pipeline                     |
| Amazon DynamoDB          | Armazenamento de metadados, resultados processados e auditoria                 |
| AWS Step Functions       | Orquestração do fluxo de processamento de documentos                           |
| Amazon API Gateway       | Exposição de APIs REST para upload e consulta de documentos                    |


Deploy realizado utilizando AWS CDK.
