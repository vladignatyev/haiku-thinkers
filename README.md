# Six Hats Solver Skill

A multi-agent framework for solving complex logical problems using the Edward de Bono six hats thinking method.

## Overview

This skill engages multiple haiku agents to analyze problems from six distinct perspectives:

- **White Hat:** Facts, information gaps, and clarifying questions
- **Red Hat:** Emotions, intuitions, creative impulses, and aesthetic judgments
- **Black Hat:** Critical thinking, risks, weaknesses, and contradictions
- **Yellow Hat:** Optimism, benefits, opportunities, and best-case scenarios
- **Green Hat:** Creativity, lateral thinking, and alternative approaches
- **Blue Hat:** Synthesis, integration, and actionable recommendations

## When to Use

✅ **Excellent ROI:**
- Strategic business decisions (growth vs stability, pivot vs focus)
- Complex specifications needing exhaustive completeness and internal consistency
- Production debugging with process design priorities
- Risk assessments and opportunity analysis
- Detective puzzles and logical problems

❌ **Not Ideal For:**
- Simple clarification tasks (overkill)
- Tasks with strict latency requirements (4-5x slower than direct reasoning)
- Straightforward lookups or summaries

## Skill Files

```
skills/six-hats-solver/
├── SKILL.md                    # Skill instructions for Claude
├── references/
│   └── six_hats_method.md     # Framework reference documentation
└── evals/
    └── evals.json              # Test cases for evaluation
```

## Key Results from Testing

| Aspect | Six Hats | Baseline | Improvement |
|--------|----------|----------|------------|
| Quality (Pass Rate) | 95.5% | 63.6% | +31.9pp |
| Avg. Tokens | 36,333 | 24,100 | +50.8% |
| Avg. Time | 91.1s | 19.0s | 4.8x slower |

**Quality Wins By Problem Type:**
1. Strategic Decisions: 100% vs 40% (+60pp) - emotional context and creative alternatives
2. Specifications: 100% vs 83% (+17pp) - security risks, testing guidance, monitoring
3. Code Debugging: 100% vs 67% (+33pp) - process design over quick fixes
4. Logic Puzzles: 100% vs 75% (+25pp) - alternative theories and comprehensive analysis

## Example Usage

### Strategic Decision
**Problem:** "We're at $2M ARR with 4 engineers. Aggressive growth (+$500K fundraising) or lean profitability?"

**Six Hats Analysis:**
- White Hat: Quantifies unknowns (burn rate, CAC, LTV, market timing)
- Red Hat: Explores founder anxiety, team stress, stakeholder emotions
- Black Hat: Analyzes competing risks (execution, dilution, competitive threat)
- Yellow Hat: Articulates opportunities (scale dominance vs sustainability + control)
- Green Hat: Proposes 5 alternatives (hybrid funding, partnerships, services)
- Blue Hat: Recommends modified Option A with 75% confidence and phased rollout

### API Specification
**Problem:** "Complete this vague auth endpoint spec"

**Six Hats Analysis:**
- White Hat: Identifies 12+ gaps (token format, refresh, concurrent sessions, logging)
- Red Hat: UX perspective (mobile vs desktop, error clarity)
- Black Hat: Security risks (brute force, token theft, race conditions)
- Yellow Hat: Best practices (JWT RS256, Argon2id, audit logging)
- Green Hat: Creative approaches (multi-level rate limiting, asymmetric strategies)
- Blue Hat: Production-ready spec with testing checklist and monitoring

### Code Debugging
**Problem:** "Production crash: validation returns None (0.3%, 150/day)"

**Six Hats Analysis:**
- White Hat: Documents facts (crash rate, impact, constraints)
- Red Hat: Urgency and team stress
- Black Hat: Risks of band-aids, wrong diagnosis
- Yellow Hat: Opportunity to collect data via logging
- Green Hat: 5 alternatives (shadow validation, sampling, state machine)
- Blue Hat: 3-phase approach (immediate stop → investigation → permanent fix)

## Documentation

- **EVALUATION_SUMMARY.md** - Detailed test results and analysis for all 4 test cases
- **benchmark.json** - Quantitative metrics, pass rates, token usage, timing

## Installation

The skill is available in Claude Code's skill registry. To use:

1. **In Claude Code:** Use the `/six-hats-solver` command on any complex problem
2. **In Claude.ai:** Type your problem and mention "six hats method" to trigger the skill

## How It Works

1. **Input:** You describe a problem, decision, or specification
2. **White Hat Agent:** Gathers facts, identifies information gaps
3. **Red Hat Agent:** Explores emotions and intuitions
4. **Black Hat Agent:** Analyzes risks and weaknesses
5. **Yellow Hat Agent:** Explores benefits and opportunities
6. **Green Hat Agent:** Generates creative alternatives
7. **Blue Hat Agent:** Synthesizes all perspectives into actionable recommendations

All agents work in parallel and independently, then Blue Hat integrates their findings.

## Performance Trade-offs

**Why it's slow (4.8x):**
- Multiple agents run in parallel
- Each explores one perspective deeply
- Synthesis requires understanding all viewpoints

**Why it's worth it (for complex problems):**
- Emotional and logical angles are both explored
- Risks AND opportunities both surface (not just one)
- Creative alternatives emerge that direct reasoning misses
- Confidence levels and rationale provided, not just answers

## Recommended Next Steps

1. Try on a strategic decision or specification you're currently working on
2. Compare results to your direct reasoning
3. Use on high-stakes problems where quality > speed
4. Provide feedback on use cases with highest value

---

**Created with:** Multi-agent orchestration using haiku models and six hats thinking framework
**Tested on:** Detective puzzles, strategic decisions, API specifications, code debugging
**Quality Improvement:** 31.9 percentage points over baseline reasoning
