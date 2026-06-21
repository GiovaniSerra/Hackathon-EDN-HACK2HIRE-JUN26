# Infraestrutura e Arquitetura Cloud

Esta pasta contém as definições e provisionamento da infraestrutura como código (IaC) utilizando o **AWS CDK**, garantindo um ambiente replicável, serverless e seguro para o processamento inteligente de sinistros.

## Serviços AWS Utilizados

| Serviço | Propósito |
| :--- | :--- |
| **Amazon S3** | Armazenamento seguro de documentos enviados para processamento, logs de auditoria e armazenamento de vetores para indexação e busca semântica. |
| **Amazon Textract** | OCR e extração automática de textos, tabelas e campos estruturados de formulários de sinistro. |
| **Amazon Comprehend** | Classificação documental automática, detecção de entidades e análise de linguagem natural. |
| **Amazon Bedrock** | Acesso a modelos fundacionais (LLMs) para orquestração de embeddings e geração de respostas contextuais. |
| **Agents for Amazon Bedrock** | Agente conversacional gerenciado para responder a consultas complexas sobre sinistros e documentos processados. |
| **AWS Lambda** | Computação serverless responsável pela execução isolada e escalável de cada etapa do pipeline de processamento. |
| **Amazon DynamoDB** | Banco de dados NoSQL utilizado para persistência de metadados, resultados analíticos e controle operacional. *(Ver detalhes abaixo)* |
| **AWS Step Functions** | Orquestração baseada em estados para o fluxo síncrono e assíncrono do pipeline documental. |
| **Amazon API Gateway** | Exposição de endpoints REST seguros para permitir o upload de arquivos e consulta de status pelo front-end. |

---

## Modelagem de Dados (Amazon DynamoDB)

Para otimizar o fluxo e garantir a governança, a camada de dados foi dividida em duas tabelas distintas:

1. **`UploadControl` (Tabela Operacional):** Baseada em tokens de sessão. É utilizada para correlacionar e herdar contextos de anexos que ainda não possuem um CPF estruturado identificado.
2. **`ClaimsComposite` (Tabela Analítica Definitiva):** Utiliza chaves compostas (`CPF` + `ID do Sinistro`) para garantir o isolamento completo de múltiplos processos por cliente e otimizar consultas de busca analítica.

---

## Próximos Passos (Segurança & Melhorias Operacionais)

Para a evolução do MVP rumo a um ambiente produtivo, mapeamos as seguintes implementações prioritárias:

* **Segurança Avançada:** Integração com o **AWS KMS** para criptografia em repouso customizada, **AWS Cognito** para autenticação/autorização e aplicação estrita do princípio de privilégio mínimo (Zero Trust).
* **Notificações:** Acoplamento do **Amazon SNS** para alertas em tempo real de status de processamento e auditoria.
* **Human-in-the-Loop (HITL):** Implementação de uma etapa de revisão humana e validação para documentos sinalizados com potenciais erros ou tentativas de fraude.
* **Métricas de Qualidade:** Criação de dashboards de monitoramento para avaliar a eficiência operacional e o índice de satisfação do cliente (NPS).

---

## Deploy

Todo o deploy e empacotamento do pipeline técnico é automatizado através do **AWS CDK** (Cloud Development Kit), garantindo infraestrutura como código (IaC) documentada e reprodutível.
