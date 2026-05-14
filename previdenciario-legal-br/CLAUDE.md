# Previdenciário — Practice Profile

*Arquivo escrito pelo cold-start interview na primeira execução do plugin. Se aparecer `[PLACEHOLDER]` abaixo, rode `/previdenciario-legal-br:cold-start-interview`.*

Este arquivo é o contexto persistente do escritório / advogado que usa o plugin previdenciário. Skills do plugin leem este arquivo antes de cada execução pra calibrar tom, jurisdição, modelos preferidos, e configurações de compliance.

---

## Identidade do advogado

**Nome:** [PLACEHOLDER]
**OAB:** [PLACEHOLDER — número + UF, ex.: "OAB/SP 123.456"]
**Escritório:** [PLACEHOLDER]
**Cidade / UF base:** [PLACEHOLDER]

## Áreas de atuação

**Foco principal:** [PLACEHOLDER — `previdenciário-puro` | `previdenciário + acidentário` | `previdenciário + assistencial` | `outro`]
**Tipos de benefício mais frequentes:** [PLACEHOLDER — BPC-LOAS / aposentadoria por tempo / aposentadoria por idade / aposentadoria especial / auxílio-doença / pensão por morte / salário-maternidade / outros]
**Volume típico:** [PLACEHOLDER — N casos novos por mês]

## Tribunais / fora frequentes

**JEF predominante:** [PLACEHOLDER — qual seção judiciária]
**TRF correspondente:** [PLACEHOLDER — TRF-1, TRF-2, TRF-3, TRF-4, TRF-5, TRF-6]
**TNU — uniformização frequência:** [PLACEHOLDER]
**Recurso ao STJ:** [PLACEHOLDER]

## Perfil do cliente típico

| Categoria | Frequência | Renda média familiar |
|---|---|---|
| Trabalhador rural | [PLACEHOLDER] | |
| Trabalhador urbano | [PLACEHOLDER] | |
| Beneficiário LOAS | [PLACEHOLDER] | |
| Servidor público | [PLACEHOLDER] | |

## Marcos regulatórios que monitora

- [x] EC 103/2019 — Reforma da Previdência
- [x] Pacote Trabalhista 2023
- [ ] Lei 8.213/91 — Plano de Benefícios
- [ ] Lei 8.742/93 — LOAS
- [ ] Decretos INSS — Instruções Normativas vigentes

## Modelos / templates preferidos

| Tipo de peça | Pasta / arquivo seed | Tom |
|---|---|---|
| Petição inicial — BPC-LOAS | [PLACEHOLDER] | [formal / técnico / acessível] |
| Petição inicial — Aposentadoria | [PLACEHOLDER] | |
| Recurso administrativo CRPS | [PLACEHOLDER] | |
| Análise de carta de indeferimento | [PLACEHOLDER] | |
| Cálculo de tempo de contribuição | [PLACEHOLDER] | |

## Compliance pessoal

**OAB exige inclusão de disclaimer?** Sim — CFOAB Recomendação nº 001/2024
**Output marca obrigatória:** `RASCUNHO PARA REVISÃO — Adv. [nome OAB]`
**Audit trail ativo:** Sim (SQLite local em `~/.briefing-estudio/audit.db`)

## Volatilidade — revisão semestral

Área previdenciária tem alta volatilidade jurisprudencial. Plugin acoplado ao cookbook `legislacao-previdenciaria-watcher` (Fase 2) que monitora STF/STJ/INSS e notifica quando alguma skill precisa update. Revisão obrigatória a cada 6 meses.

**Última revisão jurisprudencial:** [PLACEHOLDER — DATA]

---

## Atualizando este arquivo

Re-rodar cold-start interview: `/previdenciario-legal-br:cold-start-interview --redo`

Atualizar manualmente: editar este arquivo direto.

---

*Última atualização: [DATA]*
