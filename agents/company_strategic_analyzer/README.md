# Company Strategic Analyzer Agent

**Version:** 1.0.0  
**Type:** Research Agent  
**Status:** Pre-Runtime (Blueprint Ready)

## Overview

The Company Strategic Analyzer Agent evaluates businesses through a comprehensive structural lens to determine their strength as investment opportunities. It goes beyond financial metrics to assess the fundamental drivers of competitive advantage, operational excellence, growth potential, and risk exposure.

## Purpose

Evaluate any company's business model, competitive advantages, operational efficiency, and growth catalysts to determine its structural strength as an investment opportunity.

## Core Questions Answered

1. **Competitive Advantage**: What is this company's core competitive advantage and how sustainable is it against new entrants and existing competitors?

2. **Operational Structure**: How is the company's vertical integration or supply chain structured, and what operational efficiencies or risks does that create?

3. **Growth Catalysts**: What are the key growth catalysts for this company in the next 2-3 years, and what has to go right for them to materialize?

4. **Management Quality**: How does the management team's track record and incentive alignment affect the company's ability to execute its strategy?

5. **Structural Risks**: What are the biggest structural risks to this business model — including currency exposure, regulatory changes, and market concentration?

## Capabilities

### Analysis Domains

- **Business Model Evaluation**
  - Revenue stream analysis and predictability
  - Cost structure and margin profile
  - Unit economics and scalability
  - Value proposition strength

- **Competitive Positioning**
  - Moat identification and durability assessment
  - Barrier to entry analysis
  - Competitive threat evaluation
  - Market share dynamics

- **Operational Assessment**
  - Supply chain structure and resilience
  - Vertical integration analysis
  - Operational efficiency metrics
  - Cost optimization opportunities

- **Growth Analysis**
  - Catalyst identification with probability scores
  - Success factor mapping
  - Timeline projections
  - Market position evolution

- **Management Evaluation**
  - Executive track record analysis
  - Incentive alignment assessment
  - Tenure and stability metrics
  - Strategic decision-making quality

- **Risk Identification**
  - Structural risk categorization
  - Exposure quantification
  - Mitigation strategy evaluation
  - Scenario analysis

## Execution Strategy

**Hybrid Approach**: LLM (Claude 3.5 Sonnet) + MCP APIs

- **LLM**: Analysis synthesis, qualitative assessment, competitive evaluation
- **MCP APIs**: 
  - SEC EDGAR for regulatory filings (10-K, 10-Q, 8-K, proxies)
  - Yahoo Finance for market data and financial metrics
  - Financial Modeling Prep for peer comparisons and ratios
- **Temperature**: 0.4 (balanced analysis)

## Ontology Structure

The agent maintains a comprehensive knowledge graph with 28 core entities and 35 relationships:

### Primary Entities

- **COMPANY**: Core company information (ticker, sector, market cap)
- **BUSINESS_MODEL**: Value proposition, customer segments, margin profile
- **COMPETITIVE_ADVANTAGE**: Moat factors and sustainability assessments
- **MANAGEMENT_TEAM**: Leadership quality and structure
- **EXECUTIVE**: Individual leaders with track records and compensation
- **GROWTH_CATALYST**: Identified opportunities with probability scores
- **STRUCTURAL_RISK**: Risk factors with severity and mitigation strategies
- **SUPPLY_CHAIN**: Integration structure and efficiency metrics
- **MARKET_POSITION**: Competitive positioning and market share

### Key Relationships

- Company → Business Model → Revenue Streams & Cost Structure
- Company → Competitive Advantages → Moat Factors → Sustainability Assessment
- Company → Management Team → Executives → Track Record & Incentive Alignment
- Company → Growth Catalysts → Success Factors & Timeline
- Company → Structural Risks → Risk Factors → Mitigation Strategies
- Business Model → Supply Chain → Vertical Integration → Operational Efficiency

See `ontology.mermaid` for the complete entity-relationship diagram.

## Example Usage

### Example 1: Competitive Advantage Analysis

**Query:**
```
Analyze Tesla's competitive advantages in the EV market and assess their sustainability over the next 5 years
```

**Expected Output:**
- Battery technology leadership assessment (cost per kWh, energy density)
- Manufacturing scale advantages (Gigafactory capacity, learning curve effects)
- Brand strength evaluation (consumer perception, loyalty metrics)
- Software/autonomy moat analysis (data advantage, FSD capabilities)
- Threats from legacy automakers (Ford, GM) and Chinese competitors (BYD, NIO)
- Sustainability scores for each advantage (0.0-1.0)
- Confidence levels for assessments

**Entities Generated:** COMPANY, COMPETITIVE_ADVANTAGE, MOAT_FACTOR, SUSTAINABILITY_ASSESSMENT, COMPETITOR, BARRIER_TO_ENTRY

---

### Example 2: Operational Efficiency Analysis

**Query:**
```
Evaluate Costco's vertical integration strategy and the operational efficiencies it creates
```

**Expected Output:**
- Kirkland Signature private label analysis (revenue contribution, margin impact)
- Distribution center efficiency metrics (inventory turns, cost per unit)
- Supplier relationship structure (concentration, terms, partnerships)
- Cost advantages vs traditional retail (operating expense ratio comparison)
- Risks from supply concentration (geographic, supplier-specific)
- Efficiency scores benchmarked against peers

**Entities Generated:** COMPANY, BUSINESS_MODEL, SUPPLY_CHAIN, VERTICAL_INTEGRATION, OPERATIONAL_EFFICIENCY, COST_STRUCTURE

---

### Example 3: Growth Catalyst Identification

**Query:**
```
What are NVIDIA's key growth catalysts for 2026-2028 and what needs to go right?
```

**Expected Output:**
- AI/datacenter growth trajectory (TAM expansion, adoption curves)
- Customer concentration analysis (hyperscaler dependencies)
- New market opportunities (automotive, edge AI, metaverse)
- Competitive threats assessment (AMD, custom chips from Google/Amazon)
- Manufacturing dependencies (TSMC relationship, CoWoS capacity)
- Regulatory risks (export controls, geopolitical factors)
- Success probabilities for each catalyst (0.0-1.0)
- Critical success factors and current status

**Entities Generated:** COMPANY, GROWTH_CATALYST, SUCCESS_FACTOR, TIMELINE, MARKET_POSITION, STRUCTURAL_RISK

---

### Example 4: Management Quality Assessment

**Query:**
```
Assess Microsoft's management team quality and incentive alignment
```

**Expected Output:**
- Satya Nadella's transformation track record (cloud transition, GitHub/LinkedIn acquisitions)
- Executive team tenure and stability (average tenure, key departures)
- Compensation structure analysis (base vs equity, performance metrics)
- Stock ownership levels (insider ownership percentage, share purchases/sales)
- Strategic decision-making quality (Azure positioning, OpenAI partnership)
- Alignment scores with long-term value creation

**Entities Generated:** COMPANY, MANAGEMENT_TEAM, EXECUTIVE, TRACK_RECORD, INCENTIVE_ALIGNMENT

---

### Example 5: Risk Identification

**Query:**
```
Identify the biggest structural risks to Airbnb's business model
```

**Expected Output:**
- Regulatory risks by major markets (short-term rental restrictions, taxation)
- Platform disintermediation threats (hosts going direct, booking alternatives)
- Supply concentration in key cities (top 10 cities revenue exposure)
- Brand/trust vulnerabilities (safety incidents, discrimination issues)
- Competitive positioning vs hotels and VRBO (price, inventory, experience)
- Mitigation strategies and effectiveness ratings
- Overall risk severity scores

**Entities Generated:** COMPANY, BUSINESS_MODEL, STRUCTURAL_RISK, RISK_FACTOR, MITIGATION_STRATEGY, MARKET_POSITION

## Performance Targets

- **Average Confidence**: ≥0.75
- **Accuracy Rate**: ≥82%
- **Max Execution Time**: 8 seconds
- **Cost per Query**: ~$0.15 USD

## Data Sources

- **SEC EDGAR**: 10-K, 10-Q, 8-K filings, proxy statements
- **Yahoo Finance**: Stock prices, financial ratios, market metrics
- **Financial Modeling Prep**: Company financials, peer comparisons, DCF models
- **LLM Analysis**: Synthesis, competitive frameworks, qualitative assessment

## Limitations

1. **Data Access**: Cannot access real-time market data or intraday price movements
2. **Information Scope**: Relies on publicly disclosed information; no access to proprietary data or management interviews
3. **Subjective Assessments**: Qualitative evaluations (e.g., management quality) require judgment and may vary
4. **Prediction Constraints**: Cannot predict macroeconomic conditions or black swan events
5. **Geographic Coverage**: International companies may have limited English-language disclosure
6. **Historical Nature**: Past performance does not guarantee future results

## Output Format

All analysis outputs follow the ontology schema with:
- **Structured Data**: JSON-formatted entity relationships
- **Quantified Assessments**: Scores (0.0-1.0), percentages, dollar amounts
- **Confidence Levels**: For major conclusions and predictions
- **Evidence Citations**: SEC filing references, data sources
- **Comparative Context**: Industry benchmarks and peer comparisons

## Human Review Required

This agent is designed to augment, not replace, human judgment. Key areas requiring human oversight:

- Final investment decisions
- Qualitative nuances in management assessment
- Interpretation of regulatory and legal risks
- Validation of quantitative assumptions
- Integration with macroeconomic views
- Portfolio construction considerations

## Batch Processing

The agent supports batch analysis for:
- Portfolio company reviews
- Sector screening
- Peer group comparisons
- Watchlist monitoring
- Quarterly update cycles

## Ontology Evolution

The agent can evolve its ontology based on:
- New analytical frameworks discovered
- Emerging risk factors (e.g., climate, cyber)
- Evolving competitive dynamics
- User feedback and refinements

## Installation & Setup

### Prerequisites

1. **MCP Server Setup** (when runtime available):
   ```bash
   # SEC API MCP Server
   pip install sec-api-mcp
   export SEC_API_KEY="your_key_here"
   
   # Yahoo Finance MCP Server
   npm install -g yahoo-finance-mcp
   export YAHOO_API_KEY="your_key_here"
   
   # Financial Modeling Prep MCP Server
   npm install -g fmp-mcp
   export FMP_API_KEY="your_key_here"
   ```

2. **API Keys Required**:
   - SEC API Key (https://sec-api.io)
   - Yahoo Finance API Key
   - Financial Modeling Prep API Key (https://financialmodelingprep.com)

### Configuration

All configuration is stored in `agent_card.json`. Key settings:

- **Model**: claude-3-5-sonnet-20241022
- **Temperature**: 0.4
- **MCP Servers**: sec-filings, yahoo-finance, financial-modeling-prep

## Development Status

**Current Phase**: Pre-Runtime Blueprint

This agent is fully designed and documented but awaiting Fermi platform runtime availability. You can:
- ✅ Review and refine the ontology
- ✅ Adjust example queries
- ✅ Modify system prompts
- ✅ Test query design
- ⏳ Execute live analysis (pending runtime)

## Contributing

To suggest improvements or report issues:
1. Propose ontology enhancements
2. Add example queries
3. Refine system prompts
4. Suggest additional data sources

## Version History

### v1.0.0 (2026-02-07)
- Initial release
- 28 entities, 35 relationships
- 5 example query templates
- Hybrid LLM + MCP execution strategy
- Comprehensive competitive, operational, growth, management, and risk analysis capabilities

## License

Community tier agent - free to use and modify.

## Support

For questions or feedback:
- Review the Fermi documentation: https://github.com/Replicant-Partners/fermi
- Check the design checklist: `DESIGN_CHECKLIST.md`
- Consult the getting started guide: `GETTING_STARTED.md`

---

**Built with the Fermi Agent Framework**  
*Structured forecasting through Active Dreaming Memory*
