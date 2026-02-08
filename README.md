# Valu- 📊

**Valuation Agents for the Fermi Forecasting Platform**

This repository contains specialized valuation and strategic analysis agents built for the [Fermi](https://github.com/Replicant-Partners/fermi) forecasting platform.

## Overview

Valu- provides intelligent agents that evaluate companies, industries, and investment opportunities using structured analytical frameworks and data-driven methodologies. These agents leverage the Fermi Active Dreaming Memory (ADM) system to build knowledge graphs and provide evidence-based forecasts.

## Agents

### Company Strategic Analyzer (v1.1.0)

**Purpose:** Evaluate any company's business model, competitive advantages, operational efficiency, and growth catalysts to determine its structural strength as an investment opportunity.

**Status:** ✅ Blueprint Complete (Pre-Runtime)

**Key Capabilities:**
- Business model evaluation
- Competitive advantage analysis using Porter's Five Forces
- Operational efficiency assessment
- Growth catalyst identification
- Management quality evaluation
- Structural risk identification
- Jobs-to-be-Done framework for customer value analysis

**Frameworks:**
- Porter's Five Forces
- Jobs-to-be-Done (Clayton Christensen/HBR)
- Unit economics analysis
- Supply chain evaluation
- Management incentive alignment

**Ontology:**
- 41 entities
- 54 relationships
- 5 core analysis domains

[📖 Full Documentation](./agents/company_strategic_analyzer/)

## Getting Started

### Prerequisites

- Fermi runtime (when available)
- API keys for data sources:
  - SEC API (https://sec-api.io)
  - Yahoo Finance API
  - Financial Modeling Prep (https://financialmodelingprep.com)

### Installation

```bash
# Clone the repository
git clone https://github.com/Replicant-Partners/Valu-.git
cd Valu-

# Navigate to an agent directory
cd agents/company_strategic_analyzer

# Review the documentation
cat README.md
cat QUICKSTART.md
```

### Agent Structure

Each agent follows the Fermi template structure:

```
agents/<agent_name>/
├── agent_card.json          # Agent configuration
├── ontology.mermaid         # Entity-relationship diagram
├── README.md                # Main documentation
├── QUICKSTART.md           # Deployment guide
├── FRAMEWORKS.md           # Framework explanations (if applicable)
├── VALIDATION_CHECKLIST.md # Design validation
└── CHANGELOG.md            # Version history
```

## Usage Examples

### Company Strategic Analyzer

```
# Competitive advantage analysis
"Analyze Tesla's competitive advantages in the EV market and assess their sustainability over the next 5 years"

# Operational efficiency
"Evaluate Costco's vertical integration strategy and the operational efficiencies it creates"

# Growth catalysts
"What are NVIDIA's key growth catalysts for 2026-2028 and what needs to go right?"

# Management quality
"Assess Microsoft's management team quality and incentive alignment"

# Porter's Five Forces
"Apply Porter's Five Forces to analyze the streaming media industry and Netflix's position within it"

# Jobs-to-be-Done
"Use Jobs-to-be-Done framework to analyze what job customers hire Peloton to do and identify opportunity gaps"
```

## Repository Structure

```
Valu-/
├── README.md                          # This file
├── agents/                            # Agent directory
│   └── company_strategic_analyzer/    # Strategic analysis agent
│       ├── agent_card.json
│       ├── ontology.mermaid
│       ├── README.md
│       ├── QUICKSTART.md
│       ├── FRAMEWORKS.md
│       ├── VALIDATION_CHECKLIST.md
│       ├── CHANGELOG.md
│       └── AGENT_SUMMARY.md
└── docs/                              # Shared documentation (future)
```

## Roadmap

### Current Agents
- ✅ Company Strategic Analyzer v1.1.0

### Planned Agents
- 📋 DCF Valuation Agent - Discounted cash flow modeling
- 📋 Comparable Company Analyzer - Peer valuation multiples
- 📋 M&A Target Screener - Acquisition opportunity identification
- 📋 Sector Deep Dive Agent - Industry-specific analysis (SaaS, Biotech, etc.)
- 📋 ESG Evaluator - Environmental, Social, Governance assessment
- 📋 Financial Statement Analyzer - Deep dive into 10-K/10-Q filings
- 📋 Market Sentiment Agent - News, social media, and sentiment analysis

### Planned Frameworks
- Blue Ocean Strategy
- Resource-Based View (RBV/VRIN)
- BCG Growth-Share Matrix
- Value Chain Analysis
- Business Model Canvas
- Platform Business Models

## Development Status

**Phase:** Pre-Runtime Blueprint

The Fermi platform runtime is not yet available for agent execution. However, all agents in this repository are:
- ✅ Fully designed and documented
- ✅ Ontology complete
- ✅ Validation checklist passed
- ⏳ Ready for deployment when runtime launches

## Contributing

We welcome contributions! To add a new valuation agent:

1. Follow the [Fermi agent template structure](https://github.com/Replicant-Partners/fermi/tree/main/agents/templates)
2. Complete the [design checklist](https://github.com/Replicant-Partners/fermi/blob/main/agents/templates/DESIGN_CHECKLIST.md)
3. Submit a pull request with your agent directory

## Resources

- **Fermi Platform:** https://github.com/Replicant-Partners/fermi
- **Agent Templates:** https://github.com/Replicant-Partners/fermi/tree/main/agents/templates
- **Getting Started Guide:** https://github.com/Replicant-Partners/fermi/blob/main/agents/templates/GETTING_STARTED.md

## License

Community tier - free to use and modify.

## Contact

For questions, suggestions, or collaboration:
- Open an issue in this repository
- Contribute to the Fermi project: https://github.com/Replicant-Partners/fermi

---

**Built with the Fermi Agent Framework**  
*Structured forecasting through Active Dreaming Memory*
