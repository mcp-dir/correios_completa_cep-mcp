---
name: correios_completa_cep-mcp
description: Skill da REST API do Correios: Completa CEP (CEP + Área territorial brasileira) na MCP.AI: 1 endpoint em /api/correios_completa_cep. Correios: Completa CEP (CEP + Área territorial brasileira), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Correios: Completa CEP (CEP + Área territorial brasileira) — REST API skill

Você tem acesso à **Correios: Completa CEP (CEP + Área territorial brasileira)** REST API na MCP.AI.

> Correios: Completa CEP (CEP + Área territorial brasileira), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/correios_completa_cep
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/correios_completa_cep/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"cep":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/correios_completa_cep/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `correios_completa_cep_consultar`

Correios: Completa CEP (CEP + Área territorial brasileira), consulta em fonte oficial. _(POST /api/correios_completa_cep/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `cep` | string | Sim | Parâmetro de consulta "cep". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_correios_completa_cep` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
