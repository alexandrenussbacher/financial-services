---
name: fato-relevante
description: >
  Interpreta fatos relevantes e comunicados ao mercado de empresas brasileiras (CVM/B3)
  sob a ótica do investidor institucional. Avalia impacto na narrativa IR, reação
  esperada do mercado e ações recomendadas para a equipe de RI.
tools: Read, Write
---

# Fato Relevante — Skill de Análise

Veja definição completa em:
../../plugins/agent-plugins/ir-roadshow-agent/skills/fato-relevante-analyzer/SKILL.md

## Gatilhos de Uso

Esta skill é acionada automaticamente quando:
- Um comunicado CVM é colado no contexto
- O usuário usa o comando `/fato-relevante`
- O IR Roadshow Agent precisa avaliar comunicados recentes da empresa

## Alertas de Alta Prioridade

Sinalizar imediatamente para o advisor sênior da BRG se o comunicado mencionar:
- Mudança de controle acionário
- Reestruturação de dívida ou covenant breach
- Investigação CVM, CADE ou Receita Federal
- Saída de CEO, CFO ou membro do Conselho
- Revisão de guidance para baixo acima de 10%
- Cancelamento de IPO ou follow-on planejado
