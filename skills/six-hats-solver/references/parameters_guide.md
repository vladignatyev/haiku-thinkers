# Six Hats Solver - Parameters Guide

Control the depth and breadth of analysis using two key parameters.

## Parameters Overview

### Thoroughness (Depth of Analysis)

Controls how deeply each hat explores their perspective. Higher thoroughness = more comprehensive per-hat analysis.

| Level | Time | Scope | Best For |
|-------|------|-------|----------|
| **quick** (1-3) | 1-2 min | Surface-level | Rapid decisions, time-critical |
| **moderate** (5-6) | 5-10 min | Balanced | Most problems [DEFAULT] |
| **deep** (8-10) | 15-30 min | Exhaustive | High-stakes decisions, specs |

**What changes with thoroughness:**

| Hat | Quick | Moderate | Deep |
|-----|-------|----------|------|
| **White** | 3-5 facts, 1 gap | Systematic facts, 5-8 gaps | Complete inventory, 10+ gaps with follow-ups |
| **Red** | 1-2 emotions | 3-4 stakeholder views | All stakeholders, emotional triggers |
| **Black** | 2-3 top risks | 4-6 risk categories | 7+ risk angles, catastrophic scenarios |
| **Yellow** | 1-2 benefits | 3-4 opportunities | 6+ benefit categories, second-order effects |
| **Green** | 1-2 ideas | 3-5 alternatives | 7+ alternatives, radical options |
| **Blue** | Quick rec, 1 action | Integrated conclusion, 3-5 steps | Detailed reasoning, confidence analysis, full plan |

### Breadth (Width of Exploration)

Controls how many alternatives and perspectives are explored. Higher breadth = more options considered.

| Level | Scope | Best For |
|-------|-------|----------|
| **narrow** (1-3) | Focus on likely scenarios | Rapid decisions, clear problems |
| **balanced** (5-6) | Explore major branches | Most problems [DEFAULT] |
| **wide** (8-10) | Exhaustive scenario mapping | Complex problems, novel situations |

**What changes with breadth:**

| Hat | Narrow | Balanced | Wide |
|-----|--------|----------|------|
| **Black** | 2-3 main risks | 4-6 major categories | 7+ including unlikely but catastrophic |
| **Yellow** | 1-2 main benefits | 3-4 opportunity classes | 6+ including second-order effects |
| **Green** | 1-2 alternatives | 3-5 creative options | 7+ including radical/unconventional |

## Common Parameter Combinations

### Strategic Decisions

**Quick decision (time-limited):**
```
thoroughness=quick, breadth=balanced
```
- Get 1-2 emotional perspectives per stakeholder
- 4-6 major risks
- 3-5 reasonable alternatives
- Fast recommendation with immediate next steps
- **Use when:** Board meeting in 1 hour, need direction now

**Thorough decision (important choice):**
```
thoroughness=deep, breadth=wide
```
- Deep emotional landscape for all stakeholders
- 7+ risk angles including catastrophic
- 7+ alternatives including radical options
- Detailed reasoning showing how perspectives influenced decision
- **Use when:** $500K+ investment, years of consequences

### Specifications

**Quick spec (MVP version):**
```
thoroughness=quick, breadth=narrow
```
- Core facts only
- 2-3 main risks
- 1-2 key alternatives
- Brief recommendations
- **Use when:** Building prototype, iterate quickly

**Exhaustive spec (production API):**
```
thoroughness=deep, breadth=wide
```
- Complete information audit
- 7+ security risks, 6+ operational risks
- 7+ creative solutions (multi-level rate limiting, asymmetric strategies, etc.)
- Comprehensive testing and deployment guidance
- **Use when:** Spec needs to last 2+ years, impacts many teams

### Code Debugging

**Rapid diagnosis:**
```
thoroughness=moderate, breadth=narrow
```
- Key facts about the crash
- 2-3 most likely causes
- Quick immediate fix
- Fastest time to production patch
- **Use when:** 0.3% crash rate, 150 users/day affected, need stop-gap in 2h

**Thorough investigation:**
```
thoroughness=deep, breadth=balanced
```
- Exhaustive fact gathering
- Root cause analysis
- 3-5 creative fix approaches (shadow validation, sampling, etc.)
- Complete testing strategy
- **Use when:** Recurring pattern, systemic issue, need permanent solution

### Logic Puzzles / Investigation

**Quick solve:**
```
thoroughness=moderate, breadth=narrow
```
- Key facts and 2-3 main suspects
- Top risks in each theory
- Most likely scenario
- **Use when:** For fun, casual analysis

**Exhaustive analysis:**
```
thoroughness=deep, breadth=wide
```
- Complete evidence inventory
- All stakeholder emotions and biases
- 7+ theories including unlikely ones
- Second-order effects of each scenario
- **Use when:** Detective work, academic analysis, publishing

## Parameter Guidance by Problem Type

### Strategic/Business Decisions
- **High stakes** ($500K+, 5+ year impact): `deep, wide`
- **Medium stakes** ($50-500K, 1-5 years): `moderate, balanced`
- **Low stakes** (<$50K, <1 year): `quick, balanced`
- **Time-constrained**: Add 1-2 levels of quick

### Specifications
- **MVP/prototype**: `quick, narrow`
- **Production core services**: `moderate, balanced`
- **High-impact APIs** (auth, payments): `deep, wide`
- **Add 1 breadth level** for multi-platform support

### Debugging/Code Issues
- **Production emergency** (users impacted): `moderate, narrow` → publish → `deep, balanced` for root cause
- **Intermittent bug**: `moderate, balanced`
- **Systemic issue**: `deep, wide`

### Risk Assessment
- **Routine risk review**: `moderate, balanced`
- **New vendor/dependency**: `moderate, wide`
- **Security assessment**: `deep, wide`
- **Compliance audit**: `deep, balanced` (deep for thoroughness, not wide for false positives)

## Performance Expectations

### Time Impact (Relative to Default `moderate/balanced`)

| Parameters | Relative Time | Typical Duration |
|------------|---------------|------------------|
| quick, narrow | 0.3x | 1-2 min |
| quick, balanced | 0.4x | 2-3 min |
| quick, wide | 0.5x | 3-4 min |
| moderate, narrow | 0.7x | 4-6 min |
| moderate, balanced | 1.0x | 6-12 min [DEFAULT] |
| moderate, wide | 1.5x | 10-15 min |
| deep, narrow | 1.8x | 12-18 min |
| deep, balanced | 2.5x | 15-25 min |
| deep, wide | 4.0x | 25-45 min |

### Token Impact (Relative to Default)

| Parameters | Relative Tokens | Multiplier |
|------------|-----------------|-----------|
| quick, narrow | 0.4x | 40% |
| quick, balanced | 0.5x | 50% |
| moderate, narrow | 0.7x | 70% |
| moderate, balanced | 1.0x | 100% [DEFAULT] |
| moderate, wide | 1.4x | 140% |
| deep, balanced | 2.0x | 200% |
| deep, wide | 3.0x | 300% |

## Interpretation by Hat

How each hat interprets the parameters:

### White Hat (Facts)
- **Thoroughness**: How many gaps to identify (3 vs 8 vs 15)
- **Breadth**: N/A (facts don't have alternatives—consistency across all settings)

### Red Hat (Emotions)
- **Thoroughness**: How many stakeholders, how deep into their emotional landscape
- **Breadth**: How many perspectives per stakeholder (just reaction vs deep analysis)

### Black Hat (Risks)
- **Thoroughness**: How detailed each risk analysis is
- **Breadth**: How many different risk categories/scenarios to explore

### Yellow Hat (Opportunities)
- **Thoroughness**: How detailed opportunity exploration (surface vs deep)
- **Breadth**: How many different opportunity categories

### Green Hat (Creativity)
- **Thoroughness**: How fully fleshed out each alternative is
- **Breadth**: How many alternatives to generate (constrained vs exhaustive)

### Blue Hat (Synthesis)
- **Thoroughness**: How detailed the integration and confidence analysis
- **Breadth**: How many considerations in the final recommendation

## Examples

### Example 1: Quick Strategic Pivot Decision
**Query:** `thoroughness=quick, breadth=balanced: "Should we pivot to mobile-first? 60% desktop now, 40% mobile. Engineering says 4 months, 2 engineers."`

**Expected output (2-3 min):**
- White Hat: Key metric, major gaps (user retention, churn by platform)
- Red Hat: Founder excitement, team concerns
- Black Hat: Desktop abandonment risk, engineering delays
- Yellow Hat: Market advantage, future-proof product
- Green Hat: 3-4 alternatives (phased approach, outsource mobile, partnerships)
- Blue Hat: Quick recommendation (suggest phased approach) + 1 immediate action

### Example 2: Exhaustive API Specification
**Query:** `thoroughness=deep, breadth=wide: "Complete this authentication endpoint spec: accepts email/password, returns token, handles invalid credentials, rate limiting, works mobile/desktop"`

**Expected output (25-30 min):**
- White Hat: 12+ gaps systematically identified with follow-up questions
- Red Hat: UX from mobile dev, desktop dev, user, security engineer perspectives
- Black Hat: 7+ security risks, 4+ operational risks (brute force, token theft, replay, rate limit bypass, etc.)
- Yellow Hat: 6+ benefits (industry standards, performance, security posture, developer experience)
- Green Hat: 7+ creative approaches (multi-level rate limiting, asymmetric strategies, passwordless paths, etc.)
- Blue Hat: Production-ready spec with testing checklist, monitoring, logging, backwards compat

## Tips

1. **Start moderate, adjust based on need:** Most problems benefit from `moderate, balanced`. Add thoroughness for high-stakes, add breadth for novel/complex situations.

2. **Don't confuse parameters:** High thoroughness makes each hat more detailed; high breadth makes the analysis wider (more alternatives). You need both for exhaustive work.

3. **Time budget:** Check the time expectations table before choosing parameters. A `deep, wide` analysis takes 40+ minutes.

4. **Token budget:** If you're hitting usage limits, scale back breadth first (fewer alternatives), then thoroughness.

5. **Iteration strategy:** For complex problems, start `moderate, balanced` to get baseline. Then run `deep, wide` on the highest-uncertainty parts.
