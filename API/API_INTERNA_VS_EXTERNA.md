# Teste de Arquitetura — API Pública vs API Interna

## Tempo

40 minutos.

---

# Contexto

Temos uma aplicação SaaS que possui uma API interna usada pelo frontend:

`GET /api/orders`

Essa API retorna pedidos com vários campos internos:

```json
{
  "id": "123",
  "customerName": "Empresa XPTO",
  "total": 2500,
  "status": "APPROVED",
  "internalStatus": "RISK_VALIDATED",
  "createdByUserId": "789",
  "debugReason": "manual approval"
}
```

Agora queremos liberar uma API pública para clientes consultarem pedidos via integração com seus sistemas.

---

# Objetivo

Propor uma solução simples para criar uma API pública de consulta de pedidos.

---

# Requisitos

A API pública deve permitir:

- listar pedidos;
- consultar um pedido por ID;
- não expor campos internos;
- exigir autenticação;
- ter alguma estratégia básica de versionamento;
- evitar uso abusivo.

---

# Entrega esperada

Responda em texto curto, com no máximo 1 página.

Você deve explicar:

1. Como seria a arquitetura da solução;
2. Quais endpoints públicos criaria;
3. Como faria autenticação;
4. Como evitaria expor campos internos;
5. Como faria versionamento;
6. Como limitaria abuso/excesso de chamadas;
7. Quais trade-offs escolheu.

---

# Perguntas de apoio

Use essas perguntas para guiar sua resposta:

- Vale reutilizar a API interna diretamente?
- Criaria uma camada separada?
- Como evitar quebrar clientes no futuro?
- Como impedir que dados internos vazem?
- Como impedir chamadas excessivas?

---

# O que será avaliado

- clareza de raciocínio;
- consciência de trade-offs;
- simplicidade;
- preocupação com segurança;
- preocupação com evolução futura;
- capacidade de justificar decisões.

---

# Bônus (opcional)

Se sobrar tempo:

- explique como monitoraria erros e uso da API;
- explique como faria documentação para clientes externos.