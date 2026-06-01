# IR Roadshow Agent — BRG Capital

> Fork customizado de [anthropics/financial-services](https://github.com/anthropics/financial-services) para Investor Relations no mercado brasileiro.

## O que este agente faz

Dado o nome de uma empresa e o objetivo da captação, o IR Roadshow Agent entrega automaticamente:

| Artefato | Descrição |
|----------|-----------|
| `out/narrative.md` | Equity story completa para roadshow |
| `out/qa-simulator.md` | 15 perguntas difíceis + respostas modelo |
| `out/briefing.md` | Briefing executivo para a reunião |
| `out/roadshow-pack.md` | Pack completo consolidado |

## Por que este agente é diferente dos templates originais

Os agentes originais da Anthropic são calibrados para o mercado americano (SEC, 10-K, 8-K, GAAP). Este fork adiciona:

- **Contexto brasileiro**: CVM, B3, ANBIMA, IFRS com particularidades locais
- **Terminologia local**: CDI, SELIC, NTN-B, spreads, DI futuro
- **Compliance CVM**: Instrução 358 (fato relevante) e 480 (formulário de referência)
- **Perfis de investidor brasileiro**: fundos locais (Verde, SPX, Kapitalo), family offices SP/RJ, investidores estrangeiros com mandato EM
- **Foco da BRG Capital**: M&A, captações mid-market, wealth management

## Como rodar

### Via Claude Code (plugin)
```bash
# Instalar o plugin
# Settings > Plugins > Add plugin
# URL: https://github.com/alexandrenussbacher/financial-services

# Usar os comandos
/earnings MGLU3
/roadshow "Empresa XYZ" IPO "fundos de pensão"
/fato-relevante [cole o texto]
/qa-prep "Empresa ABC" roadshow
```

### Via Managed Agents API
```bash
export ANTHROPIC_API_KEY=sk-ant-...
bash scripts/deploy-managed-agent.sh ir-roadshow-agent
```

## Arquitetura

```
ir-roadshow-agent (orquestrador)
├── narrative-writer     → produz a equity story
├── qa-simulator         → simula o escrutínio de investidores  
└── briefing-writer      → monta o pack da reunião (único com Write)
```

## Guardrails

- Nenhum output é enviado diretamente a investidores
- Todo material é rascunho para revisão do advisor sênior da BRG
- Compliance CVM verificado automaticamente em fatos relevantes
- Zero recomendações de investimento — material de suporte apenas

---

*Baseado em [anthropics/financial-services](https://github.com/anthropics/financial-services) — Apache 2.0*  
*Customização: BRG Capital / Alexandre Nussbacher*
