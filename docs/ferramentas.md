# Ferramentas

Compliance & Sanções expõe 31 ferramentas (todas somente leitura).

### 1. `compliance_pep`
**Input**: `CPF` (opcional), `completo` (opcional)

Verifica se um CPF é Pessoa Exposta Politicamente (PEP).

### 2. `compliance_pep_parentescos`
**Input**: `CPF` (opcional), `completo` (opcional)

PEP estendida — pessoa exposta politicamente + parentescos.

### 3. `compliance_ofac`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca em listas de sanções OFAC (EUA) por nome.

### 4. `compliance_onu`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista consolidada de sanções da ONU por nome.

### 5. `compliance_ue`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista de sanções financeiras da União Europeia por nome.

### 6. `compliance_uk`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista de sanções do Reino Unido (HM Treasury) por nome.

### 7. `compliance_fbi`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista FBI Most Wanted por nome.

### 8. `compliance_interpol`
**Input**: `NOME` (opcional), `SOBRENOME` (opcional), `DATANASCIMENTO` (opcional), `completo` (opcional)

Busca na lista da INTERPOL por nome.

### 9. `compliance_fincen`
**Input**: `NOME` (opcional), `completo` (opcional)

Busca na lista FINCEN por nome.

### 10. `compliance_ceis`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

CEIS — empresas inidôneas e suspensas, por CNPJ/CPF.

### 11. `compliance_cnep`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

CNEP — empresas punidas, por CNPJ/CPF.

### 12. `compliance_ceaf`
**Input**: `CPF` (opcional), `completo` (opcional)

CEAF — expulsões da administração federal, por CPF.

### 13. `compliance_cepim`
**Input**: `CNPJ` (opcional), `completo` (opcional)

CEPIM — entidades privadas impedidas, por CNPJ.

### 14. `compliance_improbidade`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

CNIA — condenações por improbidade administrativa e inelegibilidade, por CNPJ/CPF.

### 15. `compliance_mandados_prisao`
**Input**: `CPF` (opcional), `NOME` (opcional), `NOMEMAE` (opcional), `NOMEPAI` (opcional), `ALCUNHA` (opcional), `completo` (opcional)

CNJ — mandados de prisão em aberto, por CPF/nome.

### 16. `compliance_antecedentes_pf`
**Input**: `CPF` (opcional), `NOME` (opcional), `DATANASCIMENTO` (opcional), `NOMEMAE` (opcional), `NOMEPAI` (opcional), `completo` (opcional)

Antecedentes criminais (Polícia Federal) por CPF/nome.

### 17. `compliance_antecedentes_civil`
**Input**: `CPF` (opcional), `RG` (opcional), `NOMEMAE` (opcional), `NOME` (opcional), `DATANASCIMENTO` (opcional), `GENERO` (opcional), `UF`, `completo` (opcional)

Antecedentes criminais (Polícia Civil) por CPF/nome/UF.

### 18. `compliance_leniencia`
**Input**: `CNPJ` (opcional), `completo` (opcional)

Acordos de leniência por CNPJ.

### 19. `compliance_cgu`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `TIPO`, `completo` (opcional)

Consulta de penalidades CGU por CPF/CNPJ.

### 20. `compliance_trabalho_forcado`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Verificação de empregador em lista de trabalho forçado/escravo, por CNPJ/CPF.

### 21. `compliance_bacen_inabilitados`
**Input**: `CPF` (opcional), `completo` (opcional)

Banco Central — quadro geral de inabilitados, por CPF/CNPJ.

### 22. `compliance_bacen_proibidos`
**Input**: `CNPJ` (opcional), `CPF` (opcional), `completo` (opcional)

Banco Central — quadro geral de proibidos, por CPF/CNPJ.

### 23. `compliance_pix`
**Input**: `DOCUMENTO`, `CHAVE`, `TIPO` (opcional), `completo` (opcional)

Antifraude de chave PIX — valida o titular de uma chave PIX.

### 24. `compliance_cvm`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Cadastro na CVM (Comissão de Valores Mobiliários) por CPF/CNPJ.

### 25. `compliance_cvm_sancionadores`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Processos administrativos sancionadores da CVM por CPF/CNPJ.

### 26. `compliance_carf`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Processos no CARF (Conselho Administrativo de Recursos Fiscais) por CPF/CNPJ.

### 27. `compliance_confea_crea`
**Input**: `CPF` (opcional), `REGISTRONACIONAL` (opcional), `completo` (opcional)

Registro profissional no CONFEA/CREA (engenharia/agronomia).

### 28. `compliance_antt`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `RNTRC` (opcional), `completo` (opcional)

Regularidade de transportadora na ANTT por CPF/CNPJ/RNTRC.

### 29. `compliance_ibama_debitos`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `completo` (opcional)

Certidão negativa de débitos do IBAMA por CPF/CNPJ.

### 30. `compliance_cnd_municipal`
**Input**: `CNPJ` (opcional), `IM` (opcional), `CPF` (opcional), `MUNICIPIO`, `completo` (opcional)

Certidão Negativa de Débitos Municipal por CNPJ/CPF (informe o município).

### 31. `compliance_cadin`
**Input**: `CPF` (opcional), `CNPJ` (opcional), `UF` (opcional), `completo` (opcional)

CADIN estadual (inadimplentes com a Fazenda) por CPF/CNPJ/UF.

## Prompts de exemplo

```
Esse nome aparece em listas de sanções (OFAC/ONU/INTERPOL)?
O CPF 000.000.000-00 é PEP?
Esse CNPJ está em alguma lista de inidôneos (CEIS/CNEP)?
```
