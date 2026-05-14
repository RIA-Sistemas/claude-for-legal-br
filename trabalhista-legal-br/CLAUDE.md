# Trabalhista — Practice Profile

*Arquivo escrito pelo cold-start interview na primeira execução do plugin. Se aparecer `[PLACEHOLDER]` abaixo, rode `/trabalhista-legal-br:cold-start-interview`.*

Este arquivo é o contexto persistente do escritório / advogado que usa o plugin trabalhista. Skills do plugin leem este arquivo antes de cada execução pra calibrar tom, jurisdição, modelos preferidos, e configurações de compliance.

---

## Identidade do advogado

**Nome:** [PLACEHOLDER]
**OAB:** [PLACEHOLDER — número + UF, ex.: "OAB/SP 123.456"]
**Escritório:** [PLACEHOLDER]
**Cidade / UF base:** [PLACEHOLDER]

## Áreas de atuação

**Foco principal:** [PLACEHOLDER — `defesa-empregador` | `defesa-empregado` | `ambos`]
**Subáreas frequentes:** [PLACEHOLDER — verbas rescisórias / horas extras / dano moral / acidente de trabalho / terceirização / equiparação / etc.]
**Volume típico:** [PLACEHOLDER — N casos novos por mês]

## Tribunais / fora frequentes

**TRT predominante:** [PLACEHOLDER — ex.: TRT-2 (SP), TRT-4 (RS), TRT-15 (Campinas)]
**Varas mais usadas:** [PLACEHOLDER]
**TST — recurso de revista frequência:** [PLACEHOLDER — alta / média / baixa]

## Convenções coletivas relevantes

Lista de CCTs/ACTs que você cita com frequência. Mantenha referência ao número e órgão registrador (MTE).

| Categoria | CCT/ACT | Vigência | Notas |
|---|---|---|---|
| [PLACEHOLDER] | | | |

## Modelos / templates preferidos

| Tipo de peça | Pasta / arquivo seed | Tom |
|---|---|---|
| Reclamatória trabalhista (cliente CLT) | [PLACEHOLDER] | [formal / direto / agressivo] |
| Defesa empregador | [PLACEHOLDER] | |
| Cálculo de verbas rescisórias | [PLACEHOLDER] | |
| Notificação extrajudicial | [PLACEHOLDER] | |

## Compliance pessoal

**OAB exige inclusão de disclaimer?** Sim — CFOAB Recomendação nº 001/2024
**Output marca obrigatória:** `RASCUNHO PARA REVISÃO — Adv. [nome OAB]`
**Audit trail ativo:** Sim (SQLite local em `~/.briefing-estudio/audit.db`)

---

## Atualizando este arquivo

Re-rodar cold-start interview: `/trabalhista-legal-br:cold-start-interview --redo`

Atualizar manualmente: editar este arquivo direto.

---

*Última atualização: [DATA]*
