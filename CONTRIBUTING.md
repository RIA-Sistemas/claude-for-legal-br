# Como contribuir

## Antes de começar

Este repositório segue **pipeline de aprovação F0-F8** documentado no repo [`briefing-estudio`](https://github.com/RIA-Sistemas/briefing-estudio) (`docs/skills/APROVACAO.md`). Skills jurídicas têm padrão de qualidade alto — não dá pra "apenas abrir PR" como em projeto de software comum.

Leia antes de contribuir:

1. [`PRINCIPIOS.md`](https://github.com/RIA-Sistemas/briefing-estudio/blob/main/docs/skills/PRINCIPIOS.md) — filosofia, Método de Validação em 3 etapas, anti-alucinação
2. [`COMPLIANCE.md`](https://github.com/RIA-Sistemas/briefing-estudio/blob/main/docs/skills/COMPLIANCE.md) — riscos OAB / LGPD / Sigilo, bloqueadores absolutos para produção
3. [`APROVACAO.md`](https://github.com/RIA-Sistemas/briefing-estudio/blob/main/docs/skills/APROVACAO.md) — pipeline F0-F8 formal
4. [`TEMPLATE.md`](https://github.com/RIA-Sistemas/briefing-estudio/blob/main/docs/skills/TEMPLATE.md) — boilerplate de skill jurídica

## Tipos de contribuição aceitos

| Tipo | Aceito sem revisão jurídica? |
|---|---|
| Correção de typo / README / documentação | Sim |
| Hook técnico (audit trail, validação de formato) | Sim |
| Agent técnico (anti-alucinação, citação) | Sim |
| **Skill jurídica nova** | Não — exige revisor jurídico externo qualificado (Tier 1) ou + jurista sênior (Tier 2-3) |
| **Edição de skill jurídica** | Não — exige re-revisão proporcional à mudança |
| Edição de `CLAUDE.md` practice profile | Sim (afeta defaults, não output substantivo) |

## Tier system

Skills são classificadas por risco:

- **Tier 1** — análise pura (lê e estrutura, não gera conteúdo jurídico autônomo)
- **Tier 2** — geração assistida (parecer, notificação extrajudicial)
- **Tier 3** — peça processual (petição inicial, contestação, recurso)
- **Tier 4** — especializações de alto risco (HC, MS, criminal, rescisória)

Tier 1 pode ir pra beta com revisão mais leve. Tier 3+ exige **todos os 6 bloqueadores absolutos** do `COMPLIANCE.md §3` implementados antes do release.

## Pull Request workflow

1. **Issue antes do PR** — descreva o que pretende fazer. Mantenedores avaliam se faz sentido e indicam revisor jurídico se aplicável.
2. **Branch separada** — `feature/<area>-<skill-name>` ou `fix/<scope>`
3. **PR em rascunho** enquanto desenvolve. Reviewer técnico avalia formato Anthropic; revisor jurídico avalia conteúdo.
4. **Eval suite** — toda skill jurídica nova precisa de golden set com **mínimo 5 casos** anonimizados validados por advogado externo
5. **Sign-off** — campo `aprovado_por` no frontmatter da skill referencia OAB do revisor que assinou
6. **Audit trail** — skill em produção deve estar coberta pelo hook `post-tool-use.sh` (já infra do plugin)
7. **Merge** — só após technical review + legal review + eval pass

## Convenção de commit

Conventional commits em PT-BR:

```
feat(trabalhista): adiciona skill calculo-verbas-rescisorias
fix(previdenciario): corrige fórmula RMI Reforma 2019
docs(readme): atualiza tabela de plugins MVP
refactor(shared): extrai validação CPF pra skill compartilhada
```

## Code of Conduct

Ver [CODE_OF_CONDUCT.md](./CODE_OF_CONDUCT.md). Discriminação, assédio ou comportamento agressivo não toleramos. Reports a suporte@riasistemas.com.br.

## Licença das contribuições

Ao abrir PR, você concorda em licenciar seu código sob Apache 2.0. Não exigimos CLA, mas o GitHub registra a autoria.

## Dúvidas

- Técnicas: [GitHub Issues](https://github.com/RIA-Sistemas/claude-for-legal-br/issues)
- Compliance / jurídicas: suporte@riasistemas.com.br
- Parcerias institucionais (OAB, AB2L, IBDP): suporte@riasistemas.com.br
