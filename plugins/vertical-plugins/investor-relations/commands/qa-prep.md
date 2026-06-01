# /qa-prep — Simulador de Q&A com Investidores

Simula o escrutínio de analistas e investidores institucionais para preparar a diretoria.

## Como usar

```
/qa-prep [nome da empresa] [contexto: earnings call | roadshow | due diligence | assembleia]
```

## O que este comando produz

1. **15 perguntas críticas** — As mais difíceis, categorizadas por tema
2. **Respostas modelo** — Diretas, com dados concretos
3. **Armadilhas a evitar** — O que NÃO dizer em cada pergunta
4. **Perguntas de oportunidade** — Onde a empresa pode brilhar
5. **Simulação de press conference** — Sequência provável de uma sessão de Q&A real

## Perfis de Investidor Disponíveis

- `sell-side` — Analistas de bancos (BTG, Itaú BBA, XP, JPMorgan)
- `buy-side-local` — Fundos brasileiros (Kapitalo, Verde, SPX, Absolute)
- `buy-side-international` — Fundos internacionais com exposição a Brasil
- `family-office` — Family offices e investidores de alta renda
- `pe` — Private equity e fundos de venture

## Exemplo

```
/qa-prep "Empresa ABC" "roadshow IPO" --perfil buy-side-international
```
