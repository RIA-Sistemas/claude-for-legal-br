# shared/

Skills, agents e hooks **compartilhados entre os plugins** do `claude-for-legal-br`.

Tudo que é genuinamente genérico (não depende de área de prática) mora aqui pra evitar duplicação. Plugins individuais referenciam via path relativo ou via mecânica do marketplace (TBD na Fase 1).

## Estrutura

```
shared/
├── skills/        # cálculos monetários, formatação de citações, validação CPF/CNPJ, etc.
├── agents/        # validators anti-alucinação, citação, compliance OAB
└── hooks/         # audit trail SQLite, pre-tool validation
```

## Convenção de naming

Skills compartilhadas devem ter prefixo claro indicando que são genéricas:

- `calculo-juros-mora` — não `trabalhista:calculo-juros-mora` (esse fica no plugin)
- `formata-cpf` — não `previdenciario:formata-cpf`
- `audit-trail-write` — hook genérico

## Status

`STATUS: PLACEHOLDER`

Conteúdo será adicionado durante a Fase 1 conforme necessidade real surgir nos plugins. Não criar shared skills **antecipando** uso — apenas quando 2+ plugins genuinamente precisarem da mesma lógica.

## Como referenciar de dentro de um plugin

(TBD — definir na Fase 1, PR 1.2)

Convenção provisória: copiar conteúdo via script de build, ou usar import via path relativo se Anthropic suportar.
