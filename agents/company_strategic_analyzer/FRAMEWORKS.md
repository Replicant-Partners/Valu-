# Strategic Analysis Frameworks

## Overview

The Company Strategic Analyzer Agent v1.1.0 now includes two world-class strategic frameworks:

1. **Porter's Five Forces** - Industry structure and competitive dynamics analysis
2. **Jobs-to-be-Done (JTBD)** - Customer-centric value creation framework from HBR/Clayton Christensen

These frameworks complement the original analysis dimensions and provide structured methodologies for understanding competitive positioning and customer value.

---

## 1. Porter's Five Forces Framework

### Purpose
Assess the structural attractiveness of an industry and understand the competitive forces that shape profitability and strategic positioning.

### The Five Forces

#### 1.1 Competitive Rivalry
**What it measures:** Intensity of competition among existing players

**Key factors:**
- Number of competitors and market concentration
- Industry growth rate (slow growth → intense rivalry)
- Degree of differentiation (commodity → intense rivalry)
- Switching costs for customers
- Exit barriers (high barriers → firms stay and compete)

**Ontology entities:** `COMPETITIVE_RIVALRY`, `COMPETITOR`

**Example (Streaming Media):**
- High intensity: Netflix, Disney+, HBO Max, Amazon Prime, Apple TV+, Paramount+
- Slow subscriber growth amplifies competition
- Content differentiation exists but consumers multi-home
- Low switching costs
- High exit barriers (content investments)

#### 1.2 Threat of New Entrants
**What it measures:** How easily new competitors can enter the industry

**Key factors:**
- Capital requirements (high → lower threat)
- Economies of scale and learning curve effects
- Brand loyalty and switching costs
- Regulatory barriers and licenses
- Access to distribution channels
- Expected retaliation from incumbents

**Ontology entities:** `THREAT_OF_NEW_ENTRANTS`, `BARRIER_TO_ENTRY`

**Example (Pharmaceutical):**
- Very low threat: $1B+ drug development costs, 10+ year timelines
- Massive regulatory barriers (FDA approval)
- Patent protection
- Strong brand loyalty (doctor prescription habits)

#### 1.3 Threat of Substitutes
**What it measures:** Pressure from alternative products/services that fulfill the same customer need

**Key factors:**
- Price-performance tradeoff of substitutes
- Switching costs to alternatives
- Buyer propensity to substitute
- Emerging technologies or business models

**Ontology entities:** `THREAT_OF_SUBSTITUTES`

**Example (Uber/Lyft):**
- Moderate-high threat: Public transit, car ownership, biking, scooters, autonomous vehicles
- Substitutes vary by use case (commuting vs late-night vs airport)
- Low switching costs between options

#### 1.4 Bargaining Power of Suppliers
**What it measures:** Leverage suppliers have to raise prices or reduce quality

**Key factors:**
- Supplier concentration vs industry concentration
- Switching costs to alternative suppliers
- Importance of the buyer to supplier's business
- Differentiation of supplier inputs
- Threat of forward integration (supplier becoming competitor)

**Ontology entities:** `BARGAINING_POWER_SUPPLIERS`, `SUPPLY_CHAIN`

**Example (Apple):**
- Low-moderate power: Apple is massive customer for component suppliers
- Some supplier concentration (TSMC for chips, Samsung for displays)
- Apple actively multi-sources and vertically integrates (M-series chips)
- High switching costs for specialized components

#### 1.5 Bargaining Power of Buyers
**What it measures:** Leverage customers have to push prices down or demand better quality

**Key factors:**
- Buyer concentration (few large buyers → high power)
- Switching costs for buyers
- Price sensitivity and availability of substitutes
- Importance of product quality to buyer's business
- Threat of backward integration (buyer making it themselves)
- Buyer information level

**Ontology entities:** `BARGAINING_POWER_BUYERS`

**Example (Enterprise Software - Salesforce):**
- Moderate power: Individual customers can switch to competitors
- High switching costs (CRM data, workflows, integrations, training)
- Price sensitivity varies (startups vs enterprises)
- No backward integration threat (complex to build)

### Output: Industry Attractiveness Score

The five forces synthesize into an **overall industry attractiveness score** (0.0 = very unattractive, 1.0 = very attractive):

- **High attractiveness**: Low rivalry, high barriers to entry, few substitutes, weak suppliers/buyers
- **Low attractiveness**: Intense rivalry, low barriers, many substitutes, powerful suppliers/buyers

### Ontology Structure

```
COMPANY ||--|| PORTER_FIVE_FORCES
  ├── COMPETITIVE_RIVALRY
  ├── THREAT_OF_NEW_ENTRANTS
  ├── THREAT_OF_SUBSTITUTES
  ├── BARGAINING_POWER_SUPPLIERS
  └── BARGAINING_POWER_BUYERS
```

### Usage Example

**Query:** "Apply Porter's Five Forces to analyze the streaming media industry and Netflix's position within it"

**Expected output:**
- Rivalry intensity: 8.5/10 (high) - Multiple well-funded competitors
- New entrants: 6/10 (moderate) - Content costs are barrier but tech giants can enter
- Substitutes: 7/10 (high) - YouTube, TikTok, gaming, piracy
- Supplier power: 7/10 (high) - Content studios have leverage
- Buyer power: 8/10 (high) - Low switching costs, subscription fatigue
- **Industry attractiveness: 3.5/10 (unattractive)**

---

## 2. Jobs-to-be-Done (JTBD) Framework

### Purpose
Understand the underlying "job" customers are trying to accomplish when they "hire" a product or service, focusing on customer outcomes rather than product features.

### Core Concept

> "People don't want a quarter-inch drill, they want a quarter-inch hole."
> 
> — Theodore Levitt

Customers don't buy products; they **hire** solutions to make progress in specific circumstances. Understanding the job reveals innovation opportunities and competitive threats.

### The Three Job Dimensions

#### 2.1 Functional Jobs
**What it is:** The practical, objective task the customer needs to accomplish

**Examples:**
- **Peloton:** "Get an effective cardiovascular workout without leaving home"
- **Uber:** "Get from point A to point B safely and conveniently"
- **Dropbox:** "Access my files from any device"
- **Starbucks (morning):** "Get caffeinated quickly on my way to work"

**Ontology entity:** `FUNCTIONAL_JOB`

#### 2.2 Emotional Jobs
**What it is:** How the customer wants to feel or avoid feeling

**Examples:**
- **Peloton:** "Feel accomplished, motivated, part of a community"
- **Uber:** "Feel safe, avoid stress of parking/directions"
- **Dropbox:** "Feel secure that my work won't be lost"
- **Starbucks:** "Feel ready to tackle the day, treat myself"

**Ontology entity:** `EMOTIONAL_JOB`

#### 2.3 Social Jobs
**What it is:** How the customer wants to be perceived by others

**Examples:**
- **Peloton:** "Be seen as health-conscious and committed to fitness"
- **Tesla:** "Signal environmental values and tech-savviness"
- **Apple:** "Project creativity, sophistication, status"
- **Patagonia:** "Demonstrate environmental responsibility"

**Ontology entity:** `SOCIAL_JOB`

### Job Outcomes & Opportunity Analysis

For each job, map **desired outcomes** and score them:
- **Importance to customer** (0-10): How critical is this outcome?
- **Current satisfaction** (0-10): How well are existing solutions performing?

**Opportunity Score = Importance + (Importance - Satisfaction)**

**High-opportunity areas:**
- High importance, low satisfaction → **Underserved** (innovation opportunity)
- Low importance, high satisfaction → **Overserved** (simplification opportunity)
- High importance, high satisfaction → **Appropriately served** (defend position)

**Ontology entity:** `JOB_OUTCOME`

### Supporting Elements

#### Product Solutions
Current products/services that address the job

**Ontology entity:** `PRODUCT_SOLUTION`

**Example (transportation job):**
- Personal car ownership
- Uber/Lyft
- Public transit
- Car rental
- Biking/scooters

#### Competing Solutions
Alternative ways customers currently solve the job (including non-consumption)

**Ontology entity:** `COMPETING_SOLUTION`

**Example (home fitness job):**
- Gym membership
- YouTube fitness videos (free)
- Outdoor running/cycling
- Home equipment (dumbbells, resistance bands)
- Group fitness classes
- Personal trainer
- **Non-consumption:** "I just don't work out"

#### Obstacles
Barriers preventing customers from getting the job done well

**Ontology entity:** `OBSTACLE`

**Example (Peloton):**
- Cost ($1,500+ bike + $44/month subscription)
- Space requirements (dedicated room/area)
- Intimidation factor (public leaderboards)
- Motivation maintenance (using it consistently)

#### Value Proposition
How the solution uniquely addresses the job better than alternatives

**Ontology entity:** `VALUE_PROPOSITION`

**Example (Peloton):**
- **Functional:** Studio-quality classes at home, instructor guidance, performance tracking
- **Emotional:** Motivating instructors, achievement badges, music-driven experience
- **Social:** Leaderboards, friend connections, aspirational brand

### Ontology Structure

```
BUSINESS_MODEL ||--o{ CUSTOMER_JOB
  ├── FUNCTIONAL_JOB (task/outcome)
  ├── EMOTIONAL_JOB (feelings)
  └── SOCIAL_JOB (perception)

CUSTOMER_JOB
  ├── JOB_OUTCOME (importance × satisfaction)
  ├── PRODUCT_SOLUTION (current offerings)
  ├── COMPETING_SOLUTION (alternatives)
  ├── OBSTACLE (barriers)
  └── VALUE_PROPOSITION (differentiation)
```

### Usage Example

**Query:** "Use Jobs-to-be-Done framework to analyze what job customers hire Peloton to do and identify opportunity gaps"

**Expected output:**

**Jobs identified:**
- **Functional:** Get convenient, effective workout at home (Importance: 9, Satisfaction: 7)
- **Emotional:** Feel motivated and accomplished (Importance: 8, Satisfaction: 7)
- **Social:** Signal fitness commitment (Importance: 6, Satisfaction: 8)

**Job outcomes:**
1. "Complete workout in <45 minutes" - Importance: 10, Satisfaction: 9 (appropriately served)
2. "Feel motivated to start workout" - Importance: 9, Satisfaction: 7 (underserved)
3. "Achieve fitness goals" - Importance: 10, Satisfaction: 6 (underserved) ⚠️
4. "Maintain consistency over time" - Importance: 9, Satisfaction: 5 (underserved) ⚠️
5. "Avoid gym commute time" - Importance: 8, Satisfaction: 10 (appropriately served)

**Opportunity gaps:**
- **Achieving measurable fitness goals:** High importance (10), low satisfaction (6) → Opportunity score: 14
- **Maintaining long-term consistency:** High importance (9), low satisfaction (5) → Opportunity score: 13

**Competing solutions:**
- Gym membership: Lower convenience, higher variety
- YouTube fitness: Free but lacks structure/accountability
- Outdoor running: Free, space-efficient, but weather-dependent
- Personal trainer: High accountability, high cost

**Obstacles:**
- $1,500+ upfront cost
- Requires dedicated space
- Motivation decreases after initial excitement

---

## Integration with Existing Analysis

### Porter's Five Forces + Competitive Advantage
Use Five Forces to understand **industry structure**, then assess how the company's competitive advantages protect it from each force.

**Example:** Tesla's vertical integration (battery production) reduces bargaining power of suppliers.

### JTBD + Growth Catalysts
Identify underserved jobs to spot **growth opportunities**.

**Example:** If "healthy meal prep without cooking time" is underserved, a meal kit or prepared meal company could expand into ready-to-eat.

### JTBD + Business Model
Validate that the business model aligns with the actual jobs customers need done.

**Example:** WeWork initially thought they were in the "office space" job, but customers were hiring them for "flexible, community-oriented workspace" → Different value proposition.

### Porter's Five Forces + Structural Risk
Forces that are strong threats become **structural risks**.

**Example:** High bargaining power of buyers (low switching costs) → Customer concentration risk.

---

## Ontology Updates Summary

### New Entities Added: 17

**Porter's Five Forces (6 entities):**
1. `PORTER_FIVE_FORCES` - Overall framework assessment
2. `COMPETITIVE_RIVALRY` - Rivalry intensity metrics
3. `THREAT_OF_NEW_ENTRANTS` - Entry barrier analysis
4. `THREAT_OF_SUBSTITUTES` - Substitute product pressure
5. `BARGAINING_POWER_SUPPLIERS` - Supplier leverage
6. `BARGAINING_POWER_BUYERS` - Customer leverage

**Jobs-to-be-Done (11 entities):**
7. `CUSTOMER_JOB` - Core job statement
8. `FUNCTIONAL_JOB` - Practical task
9. `EMOTIONAL_JOB` - Desired feelings
10. `SOCIAL_JOB` - Desired perception
11. `JOB_OUTCOME` - Measurable outcomes
12. `PRODUCT_SOLUTION` - Current offerings
13. `VALUE_PROPOSITION` - Differentiation
14. `OBSTACLE` - Barriers to job completion
15. `COMPETING_SOLUTION` - Alternative approaches

### New Relationships Added: 19

- COMPANY → PORTER_FIVE_FORCES (1 relationship)
- PORTER_FIVE_FORCES → 5 force components (5 relationships)
- Cross-linkages: COMPETITIVE_RIVALRY ↔ COMPETITOR, THREAT_OF_NEW_ENTRANTS ↔ BARRIER_TO_ENTRY, etc. (3 relationships)
- BUSINESS_MODEL → CUSTOMER_JOB (1 relationship)
- CUSTOMER_JOB → 3 job types + outcomes + solutions + obstacles (9 relationships)

### Total Ontology Size
- **Entities:** 41 (was 28)
- **Relationships:** 54 (was 35)

---

## Example Queries by Framework

### Porter's Five Forces Queries

1. "Analyze the smartphone industry using Porter's Five Forces and assess Apple's positioning"
2. "What are the competitive forces in cloud computing and how do they affect AWS's profitability?"
3. "Evaluate the threat of new entrants in the electric vehicle market"
4. "How does supplier bargaining power affect semiconductor companies like NVIDIA?"

### Jobs-to-be-Done Queries

1. "What jobs do customers hire Airbnb to do, and how does this differ from traditional hotels?"
2. "Identify opportunity gaps in the financial services jobs that Robinhood addresses"
3. "Analyze the functional, emotional, and social jobs for luxury watches (Rolex)"
4. "What competing solutions exist for the job Spotify addresses, and what are their strengths?"

### Combined Framework Queries

1. "Use both Porter's Five Forces and JTBD to analyze DoorDash's competitive position and growth opportunities"
2. "How do the jobs customers hire Netflix to do relate to the threat of substitutes in Porter's analysis?"
3. "Assess whether Shopify's value proposition adequately addresses underserved job outcomes given competitive rivalry"

---

## References

### Porter's Five Forces
- Porter, M.E. (1979). "How Competitive Forces Shape Strategy." *Harvard Business Review*
- Porter, M.E. (2008). "The Five Competitive Forces That Shape Strategy." *Harvard Business Review*

### Jobs-to-be-Done
- Christensen, C.M., Hall, T., Dillon, K., & Duncan, D.S. (2016). "Know Your Customers' 'Jobs to Be Done'." *Harvard Business Review*
- Ulwick, A.W. (2005). "What Customers Want: Using Outcome-Driven Innovation to Create Breakthrough Products and Services"
- Christensen, C.M. (2016). "Competing Against Luck: The Story of Innovation and Customer Choice"

---

**Version:** 1.1.0  
**Last Updated:** 2026-02-07  
**Frameworks:** Porter's Five Forces + Jobs-to-be-Done
