# Compliance & Sanções

### Compliance & Sanções para Claude, ChatGPT e agentes de IA

Due diligence e KYC: PEP (pessoa exposta politicamente), sanções nacionais e internacionais (OFAC, ONU, UE, Reino Unido, FBI, INTERPOL, FINCEN), idoneidade (CEIS/CNEP/CEAF/CEPIM), improbidade, mandados de prisão, antecedentes criminais, leniência e trabalho forçado. Hospedado pela plataforma, sem credenciais, pague por consulta com crédito pré-pago.

- 📊 **31 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Compliance & Sanções` e **URL** `https://api.mcp.ai/p_compliance`.

### Cursor

[➕ Instalar Compliance & Sanções no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=compliance&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9jb21wbGlhbmNlIn0=)

### VS Code (Copilot Chat)

[➕ Instalar Compliance & Sanções no VS Code](vscode:mcp/install?name=compliance&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_compliance%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_compliance
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Esse nome aparece em listas de sanções (OFAC/ONU/INTERPOL)?
O CPF 000.000.000-00 é PEP?
Esse CNPJ está em alguma lista de inidôneos (CEIS/CNEP)?
```

---

## 31 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `compliance_pep` | Verifica se um CPF é Pessoa Exposta Politicamente (PEP). |
| `compliance_pep_parentescos` | PEP estendida — pessoa exposta politicamente + parentescos. |
| `compliance_ofac` | Busca em listas de sanções OFAC (EUA) por nome. |
| `compliance_onu` | Busca na lista consolidada de sanções da ONU por nome. |
| `compliance_ue` | Busca na lista de sanções financeiras da União Europeia por nome. |
| `compliance_uk` | Busca na lista de sanções do Reino Unido (HM Treasury) por nome. |
| `compliance_fbi` | Busca na lista FBI Most Wanted por nome. |
| `compliance_interpol` | Busca na lista da INTERPOL por nome. |
| `compliance_fincen` | Busca na lista FINCEN por nome. |
| `compliance_ceis` | CEIS — empresas inidôneas e suspensas, por CNPJ/CPF. |
| `compliance_cnep` | CNEP — empresas punidas, por CNPJ/CPF. |
| `compliance_ceaf` | CEAF — expulsões da administração federal, por CPF. |
| `compliance_cepim` | CEPIM — entidades privadas impedidas, por CNPJ. |
| `compliance_improbidade` | CNIA — condenações por improbidade administrativa e inelegibilidade, por CNPJ/CPF. |
| `compliance_mandados_prisao` | CNJ — mandados de prisão em aberto, por CPF/nome. |
| `compliance_antecedentes_pf` | Antecedentes criminais (Polícia Federal) por CPF/nome. |
| `compliance_antecedentes_civil` | Antecedentes criminais (Polícia Civil) por CPF/nome/UF. |
| `compliance_leniencia` | Acordos de leniência por CNPJ. |
| `compliance_cgu` | Consulta de penalidades CGU por CPF/CNPJ. |
| `compliance_trabalho_forcado` | Verificação de empregador em lista de trabalho forçado/escravo, por CNPJ/CPF. |
| `compliance_bacen_inabilitados` | Banco Central — quadro geral de inabilitados, por CPF/CNPJ. |
| `compliance_bacen_proibidos` | Banco Central — quadro geral de proibidos, por CPF/CNPJ. |
| `compliance_pix` | Antifraude de chave PIX — valida o titular de uma chave PIX. |
| `compliance_cvm` | Cadastro na CVM (Comissão de Valores Mobiliários) por CPF/CNPJ. |
| `compliance_cvm_sancionadores` | Processos administrativos sancionadores da CVM por CPF/CNPJ. |
| `compliance_carf` | Processos no CARF (Conselho Administrativo de Recursos Fiscais) por CPF/CNPJ. |
| `compliance_confea_crea` | Registro profissional no CONFEA/CREA (engenharia/agronomia). |
| `compliance_antt` | Regularidade de transportadora na ANTT por CPF/CNPJ/RNTRC. |
| `compliance_ibama_debitos` | Certidão negativa de débitos do IBAMA por CPF/CNPJ. |
| `compliance_cnd_municipal` | Certidão Negativa de Débitos Municipal por CNPJ/CPF (informe o município). |
| `compliance_cadin` | CADIN estadual (inadimplentes com a Fazenda) por CPF/CNPJ/UF. |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Pré-pago (carteira de créditos), paga por uso. Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_compliance`.


---

## Suporte

- 📧 [compliance@mcp.ai](mailto:compliance@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/compliance-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_compliance` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
