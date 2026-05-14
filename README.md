# Claude for Legal BR

Plugins jurídicos brasileiros para o ecossistema [Claude for Legal](https://github.com/anthropics/claude-for-legal) da Anthropic.

Mantido pela **RIA Systems LTDA** ([Briefing Jurídico](https://app.riasistemas.com.br)) sob licença Apache 2.0.

## Status

`STATUS: ALPHA — PRÉ-LANÇAMENTO`

Repositório em construção. Esqueleto inicial dos 2 plugins MVP no formato canônico. Skills serão implementadas a partir de **semana 3 da Fase 1** do roadmap (ver `briefing-estudio` `docs/architecture/refactor-roadmap.md`).

**Não usar em produção** — output ainda não passou pelo pipeline de aprovação F0-F8 (revisão jurídica externa + eval suite + audit trail + sign-off).

## Pra que serve

O ecossistema Claude for Legal da Anthropic entrega plugins de prática jurídica focados em direito estadunidense (FRCP, ABA Op-512, jurisprudência US). O `claude-for-legal-br` traz o equivalente brasileiro: CLT pós-Reforma 2017, INSS pós-Reformas 2019 e 2023, CPC, CTN, CDC, jurisprudência STF/STJ/TST/TRFs.

Cada plugin é uma "área de prática" empacotada com:

- **Skills** de análise, parecer e geração de minutas
- **Agents** internos pra validação (anti-alucinação, compliance OAB, citação)
- **Hooks** pra audit trail e validação automática
- **References** com leis, súmulas e jurisprudência consolidada por área
- **Practice profile** que aprende o playbook do escritório no primeiro uso (cold-start interview)

Todo output é **rascunho assistido**, nunca peça definitiva. A responsabilidade técnica é do advogado signatário, conforme **CFOAB Recomendação nº 001/2024** e **Resolução CNJ 615/2025**.

## Plugins disponíveis

| Plugin | Área | Status | Skills MVP planejadas |
|---|---|---|---|
| [`trabalhista-legal-br`](./trabalhista-legal-br) | Direito do Trabalho | Esqueleto | `calculo-verbas-rescisorias`, `triagem-reclamatoria`, `analise-contrato-trabalho` |
| [`previdenciario-legal-br`](./previdenciario-legal-br) | Direito Previdenciário | Esqueleto | `triagem-bpc-loas`, `analise-carta-inss`, `calculo-tempo-contribuicao` |

Pasta [`shared/`](./shared) contém skills, agents e hooks compartilhados entre os plugins (cálculos monetários, audit trail, anti-alucinação).

## Como instalar

### Via Claude Code CLI

```bash
# Registrar este marketplace
/plugin marketplace add github:RIA-Sistemas/claude-for-legal-br

# Instalar plugin desejado (escolher user scope quando perguntado)
/plugin install trabalhista-legal-br@claude-for-legal-br
/plugin install previdenciario-legal-br@claude-for-legal-br

# Reiniciar Claude Code, depois rodar cold-start de cada plugin
/trabalhista-legal-br:cold-start-interview
/previdenciario-legal-br:cold-start-interview
```

### Via Briefing Estúdio (recomendado pra advogados não-CLI)

O [Briefing Estúdio](https://github.com/RIA-Sistemas/briefing-estudio) é um app desktop (Mac/Windows) que envolve o Claude Code e instala estes plugins automaticamente. Não exige terminal nem conhecimento técnico.

Download da versão atual: [riasistemas.com.br/estudio](https://riasistemas.com.br/estudio) *(em breve)*

## Compliance

- **CFOAB Recomendação nº 001/2024** — uso de IA por advogado, transparência, supervisão humana
- **Resolução CNJ 615/2025** — uso de IA pelo Poder Judiciário e órgãos auxiliares
- **LGPD (Lei 13.709/2018)** — todo processamento é local (no Estúdio) ou via OAuth do advogado. Não há trânsito de dados de cliente pela infra RIA.
- **Sigilo profissional (OAB)** — output é privilegiado, audit trail local mantém histórico sob controle do advogado

Disclaimer obrigatório aparece em todo output (configurável no `CLAUDE.md` do plugin).

## Contribuir

Veja [CONTRIBUTING.md](./CONTRIBUTING.md). Antes de abrir PR de nova skill jurídica, leia o pipeline F0-F8 de aprovação documentado no repo `briefing-estudio` (`docs/skills/APROVACAO.md`).

Issues e propostas via [GitHub Issues](https://github.com/RIA-Sistemas/claude-for-legal-br/issues).

## Licença

[Apache 2.0](./LICENSE) — uso comercial permitido, sem royalties. RIA Systems mantém o repo e a curadoria; comunidade pode adaptar/forkar.

## Mantido por

[RIA Systems LTDA](https://riasistemas.com.br) — legaltech brasileira, criadora do [Briefing Jurídico](https://app.riasistemas.com.br) (~350 escritórios ativos, MRR R$ 50K, 1M+ interações IA).

Contato: suporte@riasistemas.com.br
