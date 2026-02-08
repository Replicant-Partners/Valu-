# Company Strategic Analyzer - Quick Start Guide

## What You Have

A complete **Fermi agent blueprint** ready for deployment when the Fermi runtime becomes available.

## File Structure

```
company_strategic_analyzer/
├── agent_card.json           # Agent configuration (model, MCP servers, metadata)
├── ontology.mermaid          # Entity-relationship diagram (28 entities, 35 relationships)
├── README.md                 # Comprehensive documentation
├── VALIDATION_CHECKLIST.md   # Design validation (all steps ✅)
└── QUICKSTART.md            # This file
```

## What This Agent Does

Evaluates companies' **structural investment strength** by analyzing:

1. **Competitive Advantages** - Moats, sustainability, barriers to entry
2. **Operational Efficiency** - Supply chain, vertical integration, cost structure
3. **Growth Catalysts** - Opportunities, timelines, success factors
4. **Management Quality** - Track records, incentive alignment, execution capability
5. **Structural Risks** - Regulatory, currency, market concentration, competitive threats

## Example Queries

```
"Analyze Tesla's competitive advantages in the EV market and assess their sustainability over the next 5 years"

"Evaluate Costco's vertical integration strategy and the operational efficiencies it creates"

"What are NVIDIA's key growth catalysts for 2026-2028 and what needs to go right?"

"Assess Microsoft's management team quality and incentive alignment"

"Identify the biggest structural risks to Airbnb's business model"
```

## Current Status

**Phase**: Pre-Runtime Blueprint ✅

- ✅ Agent fully designed and documented
- ✅ Ontology complete (28 entities, 35 relationships)
- ✅ Execution strategy defined (Claude Sonnet + MCP APIs)
- ✅ Test cases and validation complete
- ⏳ Awaiting Fermi platform runtime release

## What You Can Do Now

### 1. Review the Design
- Open `ontology.mermaid` to see the entity-relationship diagram
- Review `agent_card.json` to understand configuration
- Read `README.md` for detailed capabilities

### 2. Refine the Agent
- Adjust example queries in `agent_card.json`
- Modify system prompt for different analytical styles
- Add/remove entities in `ontology.mermaid`
- Update performance targets

### 3. Prepare for Deployment

**Get API Keys**:
```bash
# SEC API (https://sec-api.io)
export SEC_API_KEY="your_key_here"

# Yahoo Finance API
export YAHOO_API_KEY="your_key_here"

# Financial Modeling Prep (https://financialmodelingprep.com)
export FMP_API_KEY="your_key_here"
```

**Install MCP Servers** (when available):
```bash
# SEC API MCP Server
pip install sec-api-mcp

# Yahoo Finance MCP Server
npm install -g yahoo-finance-mcp

# Financial Modeling Prep MCP Server
npm install -g fmp-mcp
```

### 4. Test Query Design

Create a list of companies you want to analyze:
- Large-cap established companies (AAPL, MSFT, GOOGL)
- Mid-cap growth companies (PLTR, SNOW, DDOG)
- Small-cap with limited data
- International companies (ASML, TSM)
- Pre-revenue growth companies

Document expected insights for each to calibrate the agent.

## When Runtime is Available

### 1. Deploy the Agent
```bash
# Follow Fermi deployment instructions
fermi agent deploy company_strategic_analyzer/
```

### 2. Run Initial Tests
```bash
# Test with well-known companies
fermi query company_strategic_analyzer "Analyze Microsoft (MSFT)"
```

### 3. Calibrate Performance
- Review confidence scores vs actual accuracy
- Adjust temperature if needed (currently 0.4)
- Refine system prompt based on output quality
- Update ontology if new patterns emerge

### 4. Monitor Usage
- Track execution time (target: <8 seconds)
- Monitor costs (target: ~$0.15/query)
- Check confidence levels (target: ≥0.75)
- Review accuracy rate (target: ≥82%)

## Integration Ideas

This agent can feed into:

1. **Portfolio Optimizer Agent** - Provides fundamental strength scores
2. **Risk Aggregator Agent** - Supplies company-specific risk assessments
3. **Valuation Agent** - Informs DCF assumptions and quality adjustments
4. **Sector Comparison Agent** - Enables peer benchmarking
5. **Thesis Validator Agent** - Tests investment hypotheses

## Customization Options

### Change Model
Edit `agent_card.json`:
```json
"model": "claude-3-5-sonnet-20241022"  // or "claude-opus-4-6" for deeper analysis
```

### Adjust Temperature
```json
"temperature": 0.4  // Lower (0.2) for consistency, higher (0.6) for creativity
```

### Add More Data Sources
Add to `mcp_servers` array in `agent_card.json`:
```json
{
  "name": "custom-data-source",
  "command": "node",
  "args": ["custom-mcp/index.js"],
  "env": {"API_KEY": "${CUSTOM_API_KEY}"}
}
```

### Modify System Prompt
Edit the `system_prompt` field in `agent_card.json` to change:
- Analytical frameworks used (Porter's, SWOT, etc.)
- Output verbosity
- Risk tolerance perspective
- Industry focus

## Support & Resources

- **Fermi Documentation**: https://github.com/Replicant-Partners/fermi
- **Agent Templates**: https://github.com/Replicant-Partners/fermi/tree/main/agents/templates
- **Getting Started Guide**: https://github.com/Replicant-Partners/fermi/blob/main/agents/templates/GETTING_STARTED.md

## Version Info

- **Agent Version**: 1.0.0
- **Created**: 2026-02-07
- **Tier**: Community
- **Status**: Blueprint Ready

## Next Steps

1. ✅ **Design Complete** - All files created and validated
2. ⏳ **Runtime Release** - Wait for Fermi platform availability
3. 🔜 **Setup & Deploy** - Install MCP servers, obtain API keys
4. 🔜 **Test & Calibrate** - Run initial queries, tune performance
5. 🔜 **Iterate & Improve** - Refine based on real-world usage

---

**You're ready!** When Fermi runtime launches, you can deploy this agent immediately.
