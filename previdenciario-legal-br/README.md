# previdenciario-legal-br

Plugin jurídico de **Direito Previdenciário brasileiro** para o ecossistema Claude for Legal.

## Status

`STATUS: ALPHA — ESQUELETO INICIAL`

Plugin no formato canônico Anthropic mas ainda sem skills funcionais. Skills MVP serão implementadas na Fase 1 do roadmap, com revisão jurídica externa antes do release de produção.

## O que faz (planejado)

Apoio a advogado previdenciarista BR em workflows repetitivos:

- Triagem de elegibilidade para BPC-LOAS (Benefício de Prestação Continuada)
- Análise de carta de indeferimento do INSS — extração de motivos e fundamentos contestáveis
- Cálculo de tempo de contribuição a partir de CNIS, carnês e extratos
- Análise de pertinência de aposentadoria (idade, tempo, especial, professor)
- Parecer sobre auxílio-doença, salário-maternidade, pensão por morte
- Minuta de recurso administrativo (CRPS) antes do judicial

Toda análise observa:

- **Reforma da Previdência (EC 103/2019)** — regras de transição
- **Reforma Trabalhista impacto previdenciário** (Lei 13.467/2017)
- **Pacote Trabalhista 2023** quando aplicável
- **LOAS (Lei 8.742/1993)** e atualizações
- **Decretos INSS** e Instruções Normativas vigentes
- **Jurisprudência STF/STJ/TNU/TRFs** consolidada

## Skills MVP planejadas (Fase 1, semanas 3-10)

| Skill | Tier | Status |
|---|---|---|
| `triagem-bpc-loas` | T1 — análise pura | TODO |
| `analise-carta-inss` | T1 — análise pura | TODO |
| `calculo-tempo-contribuicao` | T1 — análise pura | TODO |

Skills T2 (parecer/recurso) e T3 (peça judicial) entram em fase posterior, após validação completa do pipeline F0-F8 + audit trail em produção.

## Volatilidade jurisprudencial

Área **mais volátil** que trabalhista — Reformas 2019 e 2023 + temas STF/STJ recentes exigem revisão semestral de skills. Plugin acoplado ao cookbook `legislacao-previdenciaria-watcher` (Fase 2) que monitora STF/STJ/INSS e notifica quando alguma skill precisa update.

## Instalação

```bash
# Via Claude Code CLI
/plugin marketplace add github:RIA-Sistemas/claude-for-legal-br
/plugin install previdenciario-legal-br@claude-for-legal-br
# Reiniciar Claude Code
/previdenciario-legal-br:cold-start-interview
```

## Compliance

- Toda output marca-se como `RASCUNHO PARA REVISÃO DO ADVOGADO`
- Citações de jurisprudência marcadas `[verificar contra fonte primária]` quando vêm de model knowledge
- Audit trail local em `~/.briefing-estudio/audit.db`
- Disclaimer CFOAB Rec. 001/2024 aplicado em todo deliverable

## Como contribuir

Pipeline F0-F8 obrigatório antes de qualquer release. Ver [CONTRIBUTING.md](../CONTRIBUTING.md) do monorepo.

## Licença

Apache 2.0 — ver [LICENSE](../LICENSE).
