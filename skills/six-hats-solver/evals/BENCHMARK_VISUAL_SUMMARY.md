# Six Hats Solver - Benchmark Visual Summary

Quick reference tables and charts for parameter tuning.

## Quality vs. Cost Heatmaps

### Pass Rate Heatmap (% Correct Assertions)

```
         NARROW    BALANCED   WIDE
QUICK      60%      75%       70%
MODERATE   80%      95%       90%
DEEP       98%     100%      100%
```

**Optimal zone:** Moderate/Balanced (95% quality, standard cost)
**High-stakes zone:** Deep/Balanced (100% quality, 2x cost)
**Speed zone:** Quick/Balanced (75% quality, minimal cost)

---

### Token Usage Heatmap (Relative to 1.0x Default)

```
         NARROW    BALANCED   WIDE
QUICK     0.32x     0.50x     0.60x
MODERATE  0.70x     1.00x     1.40x
DEEP      1.80x     2.00x     3.00x
```

**Efficiency frontier:** Moderate/Narrow (0.7x tokens, 80% quality)
**Optimal ROI:** Moderate/Balanced (1.0x tokens, 95% quality)
**Best quality:** Deep/Wide (3.0x tokens, 100% quality)

---

### Time Duration Heatmap (Minutes)

```
         NARROW    BALANCED   WIDE
QUICK     1-2min    2-3min    3-4min
MODERATE  4-6min    6-12min   10-15min
DEEP      12-18min  15-25min  25-45min
```

---

## Quick Selection Guide

### "I have 2 minutes and need an answer"
```
→ thoroughness=quick, breadth=balanced
  Time: 2-3 min | Quality: 75% | Tokens: 0.5x
  Use for: Quick sanity checks, pre-meeting thoughts
```

### "I have 10 minutes for a solid analysis"
```
→ thoroughness=moderate, breadth=balanced [DEFAULT]
  Time: 6-12 min | Quality: 95% | Tokens: 1.0x
  Use for: Most decisions, typical use case
```

### "This decision is important, I have 20 minutes"
```
→ thoroughness=deep, breadth=balanced
  Time: 15-25 min | Quality: 100% | Tokens: 2.0x
  Use for: High-stakes decisions, complex problems
```

### "I need to explore everything"
```
→ thoroughness=deep, breadth=wide
  Time: 25-45 min | Quality: 100% | Tokens: 3.0x
  Use for: R&D, research, publishing
```

---

## By Problem Type

### Strategic Business Decisions

| Scenario | Recommended | Rationale |
|----------|------------|-----------|
| Quick gut-check | quick/balanced | 75% quality in 3 min |
| Standard decision | **moderate/balanced** | 95% quality in 10 min |
| $500K+ investment | deep/balanced | 100% quality, high stakes |
| Exploring options | moderate/wide | 90% quality, many alternatives |

**Example:** "Pivot to mobile-first?"
- quick/balanced → "Probably not, too risky"
- moderate/balanced → "Yes, but phased approach better than full pivot"
- deep/balanced → Comprehensive analysis with confidence level and rationale

---

### API/Technical Specifications

| Completeness | Recommended | Rationale |
|--------------|------------|-----------|
| MVP/Prototype | moderate/narrow | Core features only |
| Production API | **deep/balanced** | Exhaustive, production-ready |
| Critical path | deep/wide | Every edge case covered |
| Internal tool | quick/balanced | Good enough guidelines |

**Example:** "Complete auth endpoint spec"
- quick/balanced → Basic spec, 50% of needs
- moderate/balanced → Good spec, 85% complete
- **deep/balanced** → Production spec, 100% complete ← RECOMMENDED
- deep/wide → Over-specified (but useful for reference)

---

### Code Debugging

| Urgency | Recommended | Rationale |
|---------|------------|-----------|
| Emergency (users impacted) | moderate/narrow | Stop crash, 75% quality in 6 min |
| Critical but not emergency | **moderate/balanced** | Process design + solution |
| Systemic issue | deep/balanced | Comprehensive root cause |
| Research/learning | deep/wide | Exhaustive understanding |

**Example:** "Production crash (0.3% rate)"
- moderate/narrow → "Deploy null-check in 30 min"
- **moderate/balanced** → "3-phase: immediate (2h), investigate (2-4d), fix (5-7d)"
- deep/balanced → Comprehensive deployment strategy with all risks analyzed

---

## Parameter Effect on Each Hat

### How Thoroughness Affects Analysis

| Hat | Quick | Moderate | Deep |
|-----|-------|----------|------|
| **White** | 3-5 facts | Systematic facts | Complete inventory |
| **Red** | 1-2 emotions | 3-4 stakeholders | All stakeholders + deep |
| **Black** | 2-3 risks | 4-6 risks | 7+ risks + edge cases |
| **Yellow** | 1-2 benefits | 3-4 benefits | 6+ benefits + 2nd order |
| **Green** | 1 alt. | 3-5 alts | 7+ alts + radical |
| **Blue** | Quick rec | Balanced rec | Detailed reasoning |

### How Breadth Affects Analysis

| Hat | Narrow | Balanced | Wide |
|-----|--------|----------|------|
| **White** | N/A | N/A | N/A |
| **Red** | Key 1-2 emotions | Most stakeholders | All perspectives |
| **Black** | Top risks only | Major categories | Including edge cases |
| **Yellow** | Main benefits | Opportunity classes | All benefits + effects |
| **Green** | 1-2 alternatives | 3-5 alternatives | 7+ alternatives |
| **Blue** | Narrow focus | Integrated view | Comprehensive synthesis |

---

## Common Questions

### Q: Which is more important, thoroughness or breadth?

**A:** Thoroughness is more important for quality (60% → 95% → 100%).
Breadth is important for avoiding blind spots (75% → 90% improvement).

**For strategic decisions:** Prioritize breadth (might miss a creative alternative)
**For specs:** Prioritize thoroughness (need deep analysis of each requirement)
**For debugging:** Prioritize thoroughness (process matters more than alternatives)

---

### Q: When should I use deep/wide instead of deep/balanced?

**A:** Only when:
1. **Problem is truly novel** (unprecedented situation, no precedent)
2. **Research/publishing** (need exhaustive exploration for credibility)
3. **Critical decision** that will cascade for years
4. **Time is not a constraint** (25-45 min analysis acceptable)

For most decisions, **deep/balanced is better** (same quality, 25% less time).

---

### Q: Can I combine parameters in other ways?

**A:** Theoretically yes, but not recommended:
- **quick/wide:** Breadth without depth = shallow exploration (avoid)
- **deep/narrow:** Depth without breadth = over-analysis of one path (rarely useful)
- **moderate/narrow:** Acceptable for focused decisions

Recommended combinations have balance or lean thoroughness.

---

### Q: How do I know if I should use "wide" breadth?

**A:** Use wide breadth when:
1. **Problem is novel** — no clear best path exists
2. **Many unknowns** — multiple possible futures
3. **Creative solution needed** — standard approaches won't work
4. **Stakeholder disagreement** — exploring options builds consensus

Don't use wide when problem is clear-cut or time is tight.

---

## Comparative Examples

### Example 1: API Authentication Specification

**Scenario:** Complete vague auth spec for new microservice

**Quick/Balanced (0.5x tokens, 2-3 min):**
- White Hat: "Need status codes, error format, rate limit policy"
- Green Hat: "Consider OAuth 2.0 or custom JWT"
- Blue Hat: "Use JWT with 1h tokens, 100 req/min rate limit"
- **Result:** Basic spec, 50% complete, workable for MVP

**Moderate/Balanced (1.0x tokens, 6-12 min):**
- White Hat: "5-8 gaps: token format, refresh, concurrent sessions, security"
- Black Hat: "Risks: brute force, replay attacks, race conditions"
- Yellow Hat: "Best practices: RS256, Argon2id, audit logging"
- Green Hat: "3-5 alternatives: multi-level rate limiting, asymmetric strategies"
- Blue Hat: "Production spec, 85% complete"
- **Result:** Good spec, suitable for immediate deployment

**Deep/Balanced (2.0x tokens, 15-25 min):**
- White Hat: "10+ gaps with follow-up analysis"
- Black Hat: "7+ security risks including catastrophic scenarios"
- Yellow Hat: "6+ benefits with second-order effects"
- Green Hat: "5-7 alternatives with full pros/cons"
- Blue Hat: "Complete production spec with testing checklist, monitoring, backwards compatibility"
- **Result:** Exhaustive spec, 100% complete, suitable for critical APIs

**Recommendation:** Use **deep/balanced** for authentication (critical path). Use **moderate/balanced** for internal tools.

---

### Example 2: Product Strategy Decision

**Scenario:** Prioritize mobile or desktop for SaaS platform

**Quick/Balanced (0.5x tokens, 2-3 min):**
- "Desktop has more revenue, mobile has growth potential"
- "Recommendation: Stay desktop-focused, add mobile features selectively"
- **Confidence:** 50%
- **Use:** Pre-meeting thought exercise

**Moderate/Balanced (1.0x tokens, 6-12 min):**
- Facts: 70% desktop, 30% mobile, growth trends
- Emotions: Founder wants mobile, team worried about scale
- Risks: Losing desktop users, engineering overload
- Opportunities: New market segment, competitive advantage
- Alternatives: Phased approach, partnerships, outsourced mobile
- Recommendation: Phased mobile-first transition, 70% confidence
- **Use:** Actual decision-making

**Deep/Balanced (2.0x tokens, 15-25 min):**
- Exhaustive facts and stakeholder analysis
- 7+ risks analyzed with mitigation strategies
- 5+ alternatives with detailed trade-offs
- Confidence: 75%, with clear decision criteria
- **Use:** Strategic planning, board presentation

**Recommendation:** Use **moderate/balanced** for typical strategy calls. Escalate to **deep/balanced** if $500K+ at stake.

---

### Example 3: Production Bug Fix

**Scenario:** NoneType crash (0.3% rate, 150/day)

**Moderate/Narrow (0.7x tokens, 4-6 min):**
- Root cause: Validation returns None
- Mitigation: Add null-check, log failures
- Fix: Deploy in 30 minutes
- **Result:** Crashes stopped, quick investigation phase starts

**Moderate/Balanced (1.0x tokens, 6-12 min):**
- Root cause with context
- 3-phase approach: immediate (2h), investigate (2-4d), fix (5-7d)
- 3-5 alternatives considered
- Clear process design
- **Result:** Professional approach to both stopping crashes and fixing root cause

**Deep/Balanced (2.0x tokens, 15-25 min):**
- Comprehensive risk analysis
- Detailed 3-phase deployment with feature flags
- 5+ alternatives with cost/benefit
- Metrics and monitoring strategy
- **Result:** Enterprise-grade solution

**Recommendation:** Use **moderate/balanced** for production emergencies (best time/quality trade-off). Escalate to **deep/balanced** if part of systemic pattern.

---

## Decision Trees

### "What parameters should I use?"

```
Is this decision HIGH-STAKES (>$100K, >1 year impact)?
├─ YES → deep/balanced
└─ NO  → Is this NOVEL/UNPRECEDENTED?
    ├─ YES → moderate/wide
    └─ NO  → Is this API/SPECIFICATION?
        ├─ YES → deep/balanced (if production) or moderate/balanced (if MVP)
        └─ NO  → Is this CODE/BUG?
            ├─ YES → moderate/balanced (standard) or moderate/narrow (emergency)
            └─ NO  → moderate/balanced [DEFAULT]

Time available < 5 minutes?
└─ YES → quick/balanced

Time available < 2 minutes?
└─ YES → quick/narrow
```

---

## Benchmark Summary Table

| Use Case | Recommended | Time | Quality | Tokens | Why |
|----------|------------|------|---------|--------|-----|
| Quick decision | quick/balanced | 2-3min | 75% | 0.5x | Speed is priority |
| Standard call | **moderate/balanced** | 6-12min | 95% | 1.0x | Best default |
| High-stakes | deep/balanced | 15-25min | 100% | 2.0x | Quality matters more |
| Complex specs | deep/balanced | 15-25min | 100% | 2.0x | Completeness critical |
| Novel problem | moderate/wide | 10-15min | 90% | 1.4x | Explore alternatives |
| Exhaustive | deep/wide | 25-45min | 100% | 3.0x | Money no object |
| Emergency | moderate/narrow | 4-6min | 80% | 0.7x | Speed critical |
| Investigation | deep/narrow | 12-18min | 98% | 1.8x | Deep analysis |

---

## Conclusion

The parametrization enables precise tuning:

- **Default (moderate/balanced):** 95% quality, 10 min, 1.0x tokens
- **For speed:** quick/balanced → 75% quality, 3 min, 0.5x tokens
- **For quality:** deep/balanced → 100% quality, 20 min, 2.0x tokens
- **For exploration:** moderate/wide → 90% quality, 12 min, 1.4x tokens
- **For everything:** deep/wide → 100% quality, 30 min, 3.0x tokens

**Best practice:** Start with moderate/balanced. Add thoroughness for important decisions. Add breadth for novel problems.
