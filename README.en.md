# Compliance & Sanções

### Compliance & Sanções for Claude, ChatGPT and AI agents

Due diligence & KYC: PEP, national and international sanctions (OFAC, UN, EU, UK, FBI, INTERPOL, FINCEN), debarment, administrative misconduct, arrest warrants, criminal records, leniency and forced labor. Platform-hosted, prepaid per query.

- 📊 **31 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Compliance & Sanções`, URL `https://api.mcp.ai/p_compliance`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=compliance&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9jb21wbGlhbmNlIn0=)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=compliance&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_compliance%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_compliance
```

---

## 31 tools

| Tool | Description |
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

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_compliance` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
