# 🔍 Distributed Search & Analytics Infrastructure (Elasticsearch & Docker)

Este repositório centraliza a infraestrutura de código para provisionamento e configuração de um cluster **Elasticsearch**, utilizando contêineres e práticas recomendadas de DevOps. O objetivo deste laboratório é fornecer um ambiente isolado, escalável e de alta performance voltado para indexação massiva de dados, busca textual avançada, análise quantitativa e observabilidade centralizada (gerenciamento de logs e métricas).

---

## 🏗️ Estrutura e Componentes do Projeto

O provisionamento da infraestrutura foi desenhado para ser agnóstico e seguro, utilizando o conceito de Infraestrutura como Código (IaC) local:

* **`docker-compose.yml`:** Arquivo de orquestração de contêineres responsável por definir o ciclo de vida do serviço do Elasticsearch. Ele gerencia as configurações de rede isolada, volumes persistentes (para garantir que os dados indexados não sejam perdidos ao reiniciar o container) e limites de alocação de memória JVM para o motor de busca.
* **`.env` (Environment Variables):** Arquivo de configuração de ambiente utilizado para desacoplar credenciais e parâmetros sensíveis do código principal. Ele centraliza variáveis como senhas de acesso, portas de comunicação externa e definições de tags de versão da imagem oficial do Elastic.

---

## 🛠️ Stack Tecnológica & Arquitetura

* **Mecanismo de Busca:** Elasticsearch (Engine distribuída baseada em Apache Lucene).
* **Orquestração de Infraestrutura:** Docker & Docker Compose.
* **Segurança & Variáveis:** Dotenv (`.env`) para segregação de escopo de configuração.

---

## 🎯 Casos de Uso Práticos Demonstrados

A presença desta stack no ecossistema de dados habilita a criação de soluções voltadas para:

1. **Observabilidade Enterprise (ELK Stack):** Centralização e análise crítica de arquivos de log distribuídos (como os arquivos de auditoria `app.log` e `error.log` gerados por aplicações de backend).
2. **Busca Semântica e Textual de Alta Performance:** Mecanismo de busca autocomplete, filtros facetados e tolerância a falhas de digitação (Fuzzy Search) em grandes volumes de dados.
3. **Análise de Dados em Tempo Real:** Ingestão de dados contínuos provenientes de esteiras de mensageria ou pipelines de engenharia de dados (como Apache Beam ou streaming de dados).

---
## 🚀 Como Inicializar o Ambiente

Certifique-se de ter o Docker e o Docker Compose instalados em sua máquina:

1. Clone o repositório e acesse a pasta.
2. Certifique-se de configurar as variáveis necessárias no arquivo `.env`.
3. Execute o comando para subir o cluster em segundo plano:
   ```bash
   docker-compose up -d
