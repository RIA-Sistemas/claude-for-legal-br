# trabalhista-legal-br

Plugin jurídico de **Direito do Trabalho brasileiro** para o ecossistema Claude for Legal.

## Status

`STATUS: ALPHA — ESQUELETO INICIAL`

Plugin no formato canônico Anthropic mas ainda sem skills funcionais. Skills MVP serão implementadas na Fase 1 do roadmap, com revisão jurídica externa antes do release de produção.

## O que faz (planejado)

Apoio a advogado trabalhista BR em workflows repetitivos:

- Triagem inicial de reclamatórias trabalhistas
- Análise de contratos de trabalho (CLT, terceirizado PJ, intermitente, MEI)
- Cálculo de verbas rescisórias por modalidade de rescisão
- Análise de pertinência de horas extras, adicionais, intervalos
- Triagem de defesa de empregador

Toda análise observa:

- **CLT pós-Reforma Trabalhista (Lei 13.467/2017)**
- **Súmulas TST** consolidadas
- **Jurisprudência STF** sobre temas trabalhistas (terceirização, autonomia, etc.)
- **Convenções e Acordos Coletivos** específicos do escritório (cold-start interview)

## Skills MVP planejadas (Fase 1, semanas 3-10)

| Skill | Tier | Status |
|---|---|---|
| `calculo-verbas-rescisorias` | T1 — análise pura | TODO |
| `triagem-reclamatoria` | T1 — análise pura | TODO |
| `analise-contrato-trabalho` | T2 — parecer assistido | TODO |

Skills T3 (geração de petição inicial / contestação) só entram em fase posterior, após validação completa do pipeline F0-F8 + audit trail em produção.

## Instalação

```bash
# Via Claude Code CLI
/plugin marketplace add github:RIA-Sistemas/claude-for-legal-br
/plugin install trabalhista-legal-br@claude-for-legal-br
# Reiniciar Claude Code
/trabalhista-legal-br:cold-start-interview
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
