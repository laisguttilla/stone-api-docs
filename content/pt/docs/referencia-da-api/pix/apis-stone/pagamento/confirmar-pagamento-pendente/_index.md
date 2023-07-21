---
title: "Confirmar um pagamento pendente"
linkTitle: "Confirmar um pagamento pendente"
lastmod: 2021-09-20T15:45:21-03:00
weight: 3
draft: false
description: >
---
---
<br>

```
POST https://sandbox-api.openbank.stone.com.br/api/v1/pix/outbound_pix_payments/{id}/actions/confirm
```
<br>

Na confirmação, o body pode conter opcionalmente os campos `amount` e `description`, caso eles não tenham sido preenchidos na criação.
Além disso, também é possível adicionar o contato do pagamento realizado à lista de contatos da conta. Para isso, basta enviar a flag `add_target_to_contacts` com o valor `true`. Lembrando que este campo também é opcional.

<br>

{{% pageinfo %}}
**CONSIDERAÇÕES IMPORTANTES**
- O campo {id} informado na URL é obrigatório e deve ser o valor do identificador do Pix criado. Ele é retornado pelo endpoint `/api/v1/pix/outbound_pix_payments`<br>
- O campo `amount` se torna obrigatório caso este não tenha sido informado na criação do Pix através do endpoint `/api/v1/pix/outbound_pix_payments`. Caso este tenha sido informado, a presença dele se torna opcional.
{{% /pageinfo %}}

<br>

#### **HEADERS**
---
<br>

**authorization*** `string`
<br> Bearer token de autenticação

**x-stone-idempotency-key*** `string`
<br>Chave de idempotência

<br>

Exemplo:

```json
{
  "authorization": "Bearer eyJhbGciOiJSUzI1NiIsInR5cCIgOiAiSldUIiwia2lkIiA6ICI4d3NUd3BhYTRJWUZIYWV5ZFRubnRoRC1UaVlCaU9kanNmOGx6RUlMR1hVIn0.eyJqdGkiOiJiODQ0NDc4OS01ODE5LTQ4MTUtYjc1NC04MDU5NmMyYTg4MGYiLCJleHAiOjE2MTY2OTk5MjQsIm5iZiI6MCwiaWF0IjoxNjE2Njk5MDI0LCJpc3MiOiJodHRwczovL3NhbmRib3gtYWNjb3VudHMub3BlbmJhbmsuc3RvbmUuY29tLmJyL2F1dGgvcmVhbG1zL3N0b25lX2JhbmsiLCJzdWIiOiJhYzE5MGRmYy00YTBjLTQ5ODUtYmQwNi03NWE5Zjc3NjU0MTMiLCJ0eXAiOiJCZWFyZXIiLCJhenAiOiIwNjVlY2IwOC0yNDM5LTQwYzAtOGUxMy0yYjQzYzIxNzQzZTMiLCJhdXRoX3RpbWUiOjAsInNlc3Npb25fc3RhdGUiOiIwMjhlMjY3ZS0zMjYwLTQzNDMtODQ2ZS1hOTRkNzlmZTFjYWEiLCJhY3IiOiIxIiwic2NvcGUiOiJwYXltZW50YWNjb3VudDpwYXltZW50bGlua3M6d3JpdGUgcGF5bWVudGFjY291bnQ6Y29udGFjdDp3cml0ZSBlbnRpdHk6d3JpdGUgcGF5bWVudGFjY291bnQ6cmVhZCBwYXltZW50YWNjb3VudDp0cmFuc2ZlcnM6aW50ZXJuYWwgcGF5bWVudGFjY291bnQ6ZmVlczpyZWFkIHBheW1lbnRhY2NvdW50Omluc3RhbnRwYXltZW50IHBheW1lbnRhY2NvdW50OnBheW1lbnRzIHN0b25lX3N1YmplY3RfaWQgcGF5bWVudGFjY291bnQ6Y29udGFjdDpyZWFkIHNpZ251cDpwYXltZW50YWNjb3VudCBwYXltZW50YWNjb3VudDpib2xldG9pc3N1YW5jZSBwYXltZW50YWNjb3VudDpwYXltZW50bGlua3M6cmVhZCBwYXltZW50YWNjb3VudDpwYXlyb2xsczpyZWFkIHBheW1lbnRhY2NvdW50OnBheXJvbGxzOndyaXRlIHBheW1lbnRhY2NvdW50OnRyYW5zZmVyczpleHRlcm5hbCBlbnRpdHk6cmVhZCIsImNsaWVudElkIjoiMDY1ZWNiMDgtMjQzOS00MGMwLThlMTMtMmI0M2MyMTc0M2UzIiwiY2xpZW50SG9zdCI6IjEwLjEwLjEuMTQ5Iiwic3RvbmVfc3ViamVjdF9pZCI6ImFwcGxpY2F0aW9uOjA2NWVjYjA4LTI0MzktNDBjMC04ZTEzLTJiNDNjMjE3NDNlMyIsImNsaWVudEFkZHJlc3MiOiIxMC4xMC4xLjE0OSJ9.PlAhWLgC2W10H9emucF4obcJhwR92EogMNRIWUej4z-P-p3UaStYlaYd5Bfx4hl7da4ly62K1LEBI7LOqCFkbHMlnJfglp3dFS2M3iHZ571BNSmCff3wUiFy6zoHxFaKEUPy0V8e6mCQwFuapdIvDocA4Z4xYh049dWEwbJ2uevV3V_Q-RL3me8vykNTWGiT-dmyWvFN-XAq889_F1ZQskHsLz-ZtlrFw3XjitnLvEJbg9iyxVA7AuwnexBIQS4gU9QwMXcJjij9JowYbLu4ANUITXU01Jf5hxMYq1oSobOL3-RuGWJLoPOXkJyAbOm5hS15QgSuwp_qOU8VAEa3Yg",
  "x-stone-idempotency-key": "24b53d84-a79d-11eb-bcbc-0242ac130003"
}
```

<br>

#### **PARAMETERS REQUEST**
---
<br>

**id*** `string`

<br>

#### **BODY REQUEST**
---
<br>

**amount** `integer`
<br>Valor a ser transferido

**description** `string`
<br>Descrição do pagamento

**add_target_to_contacts** `boolean`
<br>Flag para adicionar um contato

<br>

Body:

```json
{
  "amount": 39511,
  "description": "some description",
  "add_target_to_contacts": true
}
```

<br>





##### **Responses**

```
204 OK
```
---
```
400 Bad Request
```



Body

```json
{
  "reason": [
    {"error": "can't be blank", "path": ["idempotency_key"]},
    {"error": "is invalid", "path": ["amount"]},
    {"error": "is invalid", "path": ["can't be blank"]},
    {"error": "is invalid", "path": ["description"]},
    {"error": "can't be blank", "path": ["amount"]}
  ],
  "type": "srn:error:validation"
}
```

Acontece quando são passados campos inválidos. Os erros são cumulativos, então é possível que mais de um motivo de erro seja retornado. Também pode acontecer quando o id enviado não se conforma ao padrão UUID, neste caso retorna apenas o status 400.

---
```
401 Unauthenticated
```
Body
```json
{  
  "type": "srn:error:unauthenticated"
}
```
Usuário não está autenticado.

---

```
403 Forbidden
```

Body
```json
{  
  "type": "srn:error:unauthorized"
}
```

Usuário não autorizado a realizar a ação.

---

```
409 Conflict
```

Body
```json
{
  "type": "srn:error:idempotency_conflict"
}
```

Conflito de idempotência. A chave de idempotência já existe para um body diferente.

---
```
422 Unprocessable Entity
```
Body
```json
{
  "type": "srn:error:invoice_expired"
}
```

Acontece quando a transferência está relacionada a uma cobrança criada por uma conta interna, e a cobrança expirou.

---
```
503 Service Unavailable
```

Acontece quando não é possível confirmar o pagamento em decorrência dos serviços externos estarem temporariamente indisponíveis.