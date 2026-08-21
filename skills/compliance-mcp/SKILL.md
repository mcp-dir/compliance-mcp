---
name: compliance-mcp
description: Skill da REST API do Compliance & Sanções na MCP.AI: 31 endpoints em /api/compliance. Due diligence e KYC: PEP (pessoa exposta politicamente), sanções nacionais e internacionais (OFAC, ONU, UE, Reino Unido, FBI, INTERPOL, FINCEN), idoneidade (CEIS/CNEP/CEAF/CEPIM), improbidade, mandados de prisão, antecedentes criminais, leniência e trabalho forçado. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Compliance & Sanções — REST API skill

Você tem acesso à **Compliance & Sanções** REST API na MCP.AI.

> Due diligence e KYC: PEP (pessoa exposta politicamente), sanções nacionais e internacionais (OFAC, ONU, UE, Reino Unido, FBI, INTERPOL, FINCEN), idoneidade (CEIS/CNEP/CEAF/CEPIM), improbidade, mandados de prisão, antecedentes criminais, leniência e trabalho forçado. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/compliance
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
curl -X POST https://api.mcp.ai/api/compliance/antecedentes/civil \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"UF":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/compliance/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (31)

#### `compliance_antecedentes_civil`

Antecedentes criminais (Polícia Civil) por CPF/nome/UF. _(POST /api/compliance/antecedentes/civil)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `RG` | string | Não | O parâmetro RG pode ser enviado com ou sem formatação. |
| `NOMEMAE` | string | Não | O parâmetro NOMEMAE pode ser enviado com qualquer outro. |
| `NOME` | string | Não | O parâmetro NOME pode ser enviado com qualquer outro. |
| `DATANASCIMENTO` | string | Não | O parâmetro DATANASCIMENTO deve ser fornecido, com ou sem formatação. |
| `GENERO` | string | Não | GENERO |
| `UF` | string | Sim | UF |

#### `compliance_antecedentes_pf`

Antecedentes criminais (Polícia Federal) por CPF/nome. _(POST /api/compliance/antecedentes/pf)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `NOME` | string | Não | O parâmetro NOME deve ser enviado de forma completa. |
| `DATANASCIMENTO` | string | Não | O parâmetro DATANASCIMENTO deve ser enviado nestes formatos: dd/mm/aaaa ou dd-mm-aaaa. |
| `NOMEMAE` | string | Não | O parâmetro NOMEMAE deve ser enviado de forma completa. |
| `NOMEPAI` | string | Não | O parâmetro NOMEPAI deve ser enviado de forma completa. |

#### `compliance_antt`

Regularidade de transportadora na ANTT por CPF/CNPJ/RNTRC. _(POST /api/compliance/antt)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `RNTRC` | string | Não | O parâmetro RNTRC é um conjunto de 9 números. |

#### `compliance_bacen_inabilitados`

Banco Central — quadro geral de inabilitados, por CPF/CNPJ. _(POST /api/compliance/bacen/inabilitados)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_bacen_proibidos`

Banco Central — quadro geral de proibidos, por CPF/CNPJ. _(POST /api/compliance/bacen/proibidos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_cadin`

CADIN estadual (inadimplentes com a Fazenda) por CPF/CNPJ/UF. _(POST /api/compliance/cadin)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `UF` | string | Não | UF |

#### `compliance_carf`

Processos no CARF (Conselho Administrativo de Recursos Fiscais) por CPF/CNPJ. _(POST /api/compliance/carf)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `compliance_ceaf`

CEAF — expulsões da administração federal, por CPF. _(POST /api/compliance/ceaf)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_ceis`

CEIS — empresas inidôneas e suspensas, por CNPJ/CPF. _(POST /api/compliance/ceis)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_cepim`

CEPIM — entidades privadas impedidas, por CNPJ. _(POST /api/compliance/cepim)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `compliance_cgu`

Consulta de penalidades CGU por CPF/CNPJ. _(POST /api/compliance/cgu)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `TIPO` | string | Sim | O parâmetro TIPO deve ser escolhido. |

#### `compliance_cnd_municipal`

Certidão Negativa de Débitos Municipal por CNPJ/CPF (informe o município). _(POST /api/compliance/cnd/municipal)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `IM` | string | Não | O parâmetro IM (Inscrição Municipal) pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `MUNICIPIO` | string | Sim | O parâmetro MUNICIPIO deve ser informado juntamente com a Unidade Federativa (MUNICIPIO-UF). |

#### `compliance_cnep`

CNEP — empresas punidas, por CNPJ/CPF. _(POST /api/compliance/cnep)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_confea_crea`

Registro profissional no CONFEA/CREA (engenharia/agronomia). _(POST /api/compliance/confea/crea)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `REGISTRONACIONAL` | string | Não | O parâmetro REGISTRONACIONAL pode ser enviado com ou sem formatação. |

#### `compliance_cvm`

Cadastro na CVM (Comissão de Valores Mobiliários) por CPF/CNPJ. _(POST /api/compliance/cvm)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `compliance_cvm_sancionadores`

Processos administrativos sancionadores da CVM por CPF/CNPJ. _(POST /api/compliance/cvm/sancionadores)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `compliance_fbi`

Busca na lista FBI Most Wanted por nome. _(POST /api/compliance/fbi)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado em maiúsculo ou minúsculo. |

#### `compliance_fincen`

Busca na lista FINCEN por nome. _(POST /api/compliance/fincen)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado em maiúsculo ou minúsculo. |

#### `compliance_ibama_debitos`

Certidão negativa de débitos do IBAMA por CPF/CNPJ. _(POST /api/compliance/ibama/debitos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `compliance_improbidade`

CNIA — condenações por improbidade administrativa e inelegibilidade, por CNPJ/CPF. _(POST /api/compliance/improbidade)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_interpol`

Busca na lista da INTERPOL por nome. _(POST /api/compliance/interpol)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado em maiúsculo ou minúsculo. |
| `SOBRENOME` | string | Não | O parâmetro SOBRENOME pode ser enviado em maiúsculo ou minúsculo. |
| `DATANASCIMENTO` | string | Não | O parâmetro DATANASCIMENTO deve ser fornecido, com ou sem formatação. |

#### `compliance_leniencia`

Acordos de leniência por CNPJ. _(POST /api/compliance/leniencia)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |

#### `compliance_mandados_prisao`

CNJ — mandados de prisão em aberto, por CPF/nome. _(POST /api/compliance/mandados/prisao)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |
| `NOME` | string | Não | O parâmetro NOME pode ser enviado com qualquer outro. |
| `NOMEMAE` | string | Não | O parâmetro NOMEMAE pode ser enviado com qualquer outro. |
| `NOMEPAI` | string | Não | O parâmetro NOMEPAI pode ser enviado com qualquer outro. |
| `ALCUNHA` | string | Não | O parâmetro ALCUNHA pode ser enviado com qualquer outro. |

#### `compliance_ofac`

Busca em listas de sanções OFAC (EUA) por nome. _(POST /api/compliance/ofac)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado em maiúsculo ou minúsculo. |

#### `compliance_onu`

Busca na lista consolidada de sanções da ONU por nome. _(POST /api/compliance/onu)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado em maiúsculo ou minúsculo. |

#### `compliance_pep`

Verifica se um CPF é Pessoa Exposta Politicamente (PEP). _(POST /api/compliance/pep)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_pep_parentescos`

PEP estendida — pessoa exposta politicamente + parentescos. _(POST /api/compliance/pep/parentescos)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_pix`

Antifraude de chave PIX — valida o titular de uma chave PIX. _(POST /api/compliance/pix)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `DOCUMENTO` | string | Sim | O parâmetro DOCUMENTO pode ser enviado com ou sem formatação. |
| `CHAVE` | string | Sim | O parâmetro CHAVE pode ser enviado com qualquer outro. |
| `TIPO` | string | Não | O parâmetro TIPO deve ser enviado. |

#### `compliance_trabalho_forcado`

Verificação de empregador em lista de trabalho forçado/escravo, por CNPJ/CPF. _(POST /api/compliance/trabalho/forcado)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `CNPJ` | string | Não | O parâmetro CNPJ pode ser enviado com ou sem formatação. |
| `CPF` | string | Não | O parâmetro CPF pode ser enviado com ou sem formatação. |

#### `compliance_ue`

Busca na lista de sanções financeiras da União Europeia por nome. _(POST /api/compliance/ue)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado em maiúsculo ou minúsculo. |

#### `compliance_uk`

Busca na lista de sanções do Reino Unido (HM Treasury) por nome. _(POST /api/compliance/uk)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `NOME` | string | Não | O parâmetro NOME pode ser enviado com qualquer outro. |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_compliance` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
