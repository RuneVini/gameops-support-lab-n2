![Node.js](https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?logo=express&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?logo=mysql&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?logo=postman&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?logo=elasticsearch&logoColor=white)
![Kibana](https://img.shields.io/badge/Kibana-E8478B?logo=kibana&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-F46800?logo=grafana&logoColor=white)
# GameOps Support Lab — N2 (Logs, APIs & Incident Analysis)

Simulação de um ambiente de backend de jogo online com foco em **suporte técnico N2**, análise de logs, investigação de incidentes e troubleshooting de APIs.

---

## Objetivo

Este projeto demonstra, na prática, habilidades essenciais para atuação como:

* Analista de Suporte Técnico N2
* Application Support Analyst
* Support Engineer

Com foco em:

* Análise de logs
* Investigação de incidentes (RCA)
* Troubleshooting de APIs
* Correlação de eventos e impacto

---

## Arquitetura do Projeto

```bash
gameops-n2-lab/
│
├── database/       # Estrutura e queries SQL
├── api/            # API simulando backend de jogo
├── logs/           # Logs simulados de produção
├── monitoring/     # Métricas do sistema
├── incidents/      # Documentação de incidentes (RCA)
├── postman/        # Collection para testes de API
└── README.md
```

---

## Contexto do Sistema

O sistema simula um jogo online com os seguintes módulos:

* Autenticação (login de jogador)
* Matchmaking (busca de partidas)
* Loja (microtransações)
* Monitoramento de eventos

---

## Tecnologias Utilizadas

* Node.js (Express)
* SQL (estrutura relacional)
* Logs estruturados (simulação)
* Postman (testes de API)
* Docker (ELK - opcional)

---

## Como Executar

### 1. Instalar dependências

```bash
npm install express
```

---

### 2. Rodar a API

```bash
node api/app.js
```

API disponível em:

```
http://localhost:3000
```

---

### 3. Testar endpoints

Importe a collection em:

```
/postman/collection.json
```

---

## Cenários de Teste (Simulação N2)

### 1. Matchmaking indisponível

* Endpoint:

```
GET /matchmaking
```

* Retorno:

```
500 - Matchmaking service unavailable
```

* Investigação:

  * Verificar logs
  * Validar status do serviço

---

### 2. Falha em pagamento

* Endpoint:

```
POST /purchase
```

* Retorno:

```
504 - Payment timeout
```

* Investigação:

  * Timeout em serviço externo
  * Impacto financeiro

---

### 3. Erro de login

* Endpoint:

```
POST /login
```

* Retorno:

```
400 - Missing email
```

* Investigação:

  * Validação de payload
  * Erro de frontend

---

## Análise de Logs

Exemplo:

```log
ERROR matchmaking Matchmaking service unavailable
ERROR store Payment timeout
ERROR auth Invalid token
```

Atividades esperadas:

* Identificar padrões de erro
* Correlacionar eventos
* Determinar causa raiz

---

## SQL para Investigação

Exemplo de análise:

```sql
SELECT service, COUNT(*) 
FROM logs 
WHERE level = 'ERROR'
GROUP BY service;
```

Objetivo:

* Identificar serviços com maior falha
* Priorizar incidentes

---

## Incident Response (RCA)

Cada incidente contém:

* Sintoma
* Evidência
* Investigação
* Causa raiz
* Ação corretiva
* Prevenção

Local:

```
/incidents/
```

---

## Métricas do Sistema

Arquivo:

```
/monitoring/metrics.json
```

Exemplo:

```json
{
  "active_players": 1200,
  "matchmaking_errors": 120
}
```

---

## Habilidades Demonstradas

* Troubleshooting de APIs (HTTP 400/500/504)
* Análise de logs e eventos
* Investigação de incidentes reais
* Query SQL para diagnóstico
* Documentação técnica (RCA)

---

## Aplicação Profissional

Este projeto simula atividades reais de:

* Suporte N2 em ambientes SaaS
* Operações de sistemas críticos
* Análise de falhas em produção

---

## Próximos Passos

* [ ] Integração com Grafana
* [ ] Geração automática de logs
* [ ] Alertas simulados (monitoramento)
* [ ] Pipeline de incidentes

---

## Autor

Vinicius Brito de Lima
Analista de Suporte Técnico N2

* Experiência com troubleshooting avançado
* Análise de logs e indicadores
* Suporte a sistemas corporativos

---

## 📌 Observação

Projeto desenvolvido com foco em evolução para atuação como:

**Analista de Suporte N2 com foco em dados, logs e observabilidade**
