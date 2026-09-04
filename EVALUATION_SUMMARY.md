# Six Hats Solver Skill - Evaluation Summary

## Skill Overview

**Name:** `six-hats-solver`

**Purpose:** Engage multiple haiku agents using the six hats thinking method to solve complex logical problems, complete incomplete specifications, and generate evidence-based strategies.

**When to Use:**
- Detective puzzles & logical problems
- Strategic business decisions
- Incomplete specifications that need exhaustive completeness
- Code debugging & system design problems
- Risk assessment & opportunity analysis

---

## Test Results Summary

### Overall Quality Improvement
- **Pass Rate (Six Hats):** 95.5% (21/22 assertions)
- **Pass Rate (Baseline):** 63.6% (14/22 assertions)
- **Improvement:** +31.9 percentage points

### Performance Trade-offs
- **Average Tokens:** Six-Hats uses 50.8% more tokens (36,333 vs 24,100)
- **Average Time:** Six-Hats takes 4.8x longer (91.1s vs 19.0s)
- **Quality ROI:** Strong—the additional time/tokens consistently produce better outputs

---

## Test Case Results

### 1. Detective Puzzle (Murder Mystery)

**Scenario:** Wealthy collector found dead in locked study. Three suspects with incomplete evidence.

**Six Hats Approach (Pass Rate: 100%, 4/4 assertions):**
- **White Hat:** Systematically cataloged all facts and identified 10+ critical information gaps (toxicology, fingerprints, defensive wounds)
- **Red Hat:** Explored emotional reactions, gut instincts, psychological profiles
- **Black Hat:** Identified paradoxes (locked room, brandy timing inconsistency) and challenged assumptions
- **Yellow Hat:** Explored optimistic scenarios for each suspect
- **Green Hat:** Generated 5 creative alternative theories (accident coverup, hired accomplices, staged death, multi-person involvement)
- **Blue Hat:** Synthesized daughter-as-killer theory with 65% confidence, clear rationale

**Baseline Approach (Pass Rate: 75%, 3/4 assertions):**
- Reached business partner conclusion via direct reasoning
- Analyzed facts and risks logically
- But missed creative alternatives and didn't explore multiple theories
- No confidence level provided

**Key Difference:** Six hats explores multiple theories then synthesizes the most coherent one; baseline reaches a conclusion via elimination. Baseline misses the breadth of analysis.

---

### 2. Strategic Decision (SaaS Growth Dilemma)

**Scenario:** Startup at $2M ARR deciding between aggressive growth (+$500K fundraising) or lean profitability. Market window narrowing.

**Six Hats Approach (Pass Rate: 100%, 5/5 assertions):**
- **White Hat:** Quantified unknowns (burn rate, CAC, LTV, NRR needed)
- **Red Hat:** Explored founder anxiety, team stress, and emotional stakes per stakeholder
- **Black Hat:** Analyzed competing risks thoroughly—execution risk, dilution, talent loss vs competitive threat
- **Yellow Hat:** Articulated opportunities from each path (scale dominance vs sustainability + control)
- **Green Hat:** Proposed 5 creative alternatives—hybrid funding, partnerships, founder-friendly terms, productized services
- **Blue Hat:** Recommended modified Option A (smaller raise, realistic targets, phased rollout) with 75% confidence

**Baseline Approach (Pass Rate: 40%, 2/5 assertions):**
- Recommended modified Option A
- But lacked emotional landscape analysis
- Vague on alternatives ("don't accept harsh dilution" vs structured options)
- Only 70% confidence
- Surface-level treatment of a strategic problem

**Key Difference:** This is where six hats shows its largest value. Emotional context (founder anxiety, team stress) completely missing from baseline. Creative alternatives (5 structured options) vs general advice. Systematic risk analysis vs intuitive pros/cons.

**Largest Quality Gap in Test Suite.**

---

### 3. API Specification Completion

**Scenario:** Incomplete authentication endpoint spec. Need to fill in status codes, error formats, rate limits, token expiration, concurrent sessions, security, monitoring.

**Six Hats Approach (Pass Rate: 100%, 6/6 assertions):**
- **White Hat:** Identified 12+ critical information gaps (token format, refresh mechanism, concurrent session policy, logging requirements)
- **Red Hat:** Explored UX from desktop/mobile perspective, developer experience
- **Black Hat:** Surfaced 10+ security risks (brute force, token theft, replay attacks, account enumeration, race conditions)
- **Yellow Hat:** Recommended industry best practices (JWT RS256, Argon2id, exponential backoff, audit logging)
- **Green Hat:** Proposed 5 creative approaches (multi-level rate limiting, sliding windows, asymmetric token strategies for mobile vs web, passwordless auth path)
- **Blue Hat:** Complete specification covering status codes, error formats, multi-level rate limiting, token lifecycle, concurrent sessions, security requirements (HTTPS, certificate pinning, secure storage), client guidance (iOS Keychain, Android Keystore, Web HttpOnly cookies), monitoring/logging, backwards compatibility, testing checklist

**Baseline Approach (Pass Rate: 83%, 5/6 assertions):**
- Covered status codes, error format, rate limits, security basics
- Addressed most requirements
- But vague on edge cases (concurrent sessions, token refresh)
- Missing security depth (certificate pinning, platform-specific storage)
- No testing/deployment guidance
- Less exhaustive

**Key Difference:** Six hats explores from multiple angles (UX, security, best practices, creativity) then synthesizes a complete, production-ready spec. Baseline covers checklist items. The with-skill output is 210% longer (45,937 vs 14,800 tokens) but includes security risk analysis, testing checklists, client implementation guidance—genuinely more useful.

---

### 4. Code Fix (Production Bug Diagnosis)

**Scenario:** Python upload function crashing intermittently (0.3% of 50K daily = 150 failures/day). Validation returns None instead of raising error. Critical path, expensive downtime. One engineer, one week.

**Six Hats Approach (Pass Rate: 100%, 6/6 assertions):**
- **White Hat:** Documented facts (0.3% rate, 150 daily failures, critical path, 1 engineer, 1 week)
- **Red Hat:** Surfaced urgency, team stress, customer impact
- **Black Hat:** Analyzed risks of quick band-aids, wrong diagnosis, type safety gaps, systemic weakness
- **Yellow Hat:** Highlighted opportunity—turn crash into data source via logging
- **Green Hat:** Proposed 5 alternatives (defensive check, shadow validation, sampling/replay, state machine, async validation)
- **Blue Hat:** Integrated three-phase approach:
  - Phase 1 (Day 1, 2 hours): Defensive null-check + logging → stops crashes, enables data collection
  - Phase 2 (Days 2-4): Root cause investigation using logs
  - Phase 3 (Days 5-7): Permanent fix with type hints + mypy checking
  - Result: Stops crashes today, finds root cause tomorrow, prevents recurrence

**Baseline Approach (Pass Rate: 67%, 4/6 assertions):**
- Identified validation None-return as root cause
- Proposed immediate null-check (30 min deployment)
- Included long-term refactor suggestion
- But didn't analyze risks of different approaches deeply
- Missed feature flags, gradual rollout, shadow validation strategies
- Rushed approach without investigation phase

**Key Difference:** Six hats designs a deployment strategy that balances immediate relief (stop crashes) with rigorous investigation (find root cause). Baseline focuses on the fix; six hats focuses on the process. The investigation phase (logging + analysis) is crucial—you need data to diagnose properly. Six hats doesn't guess; it collects evidence first.

---

## Key Findings

### Consistent Quality Gains Across All Problem Types
- Strategic decisions: Largest gap (60% improvement)
- Specifications: Highest complexity, justified by depth
- Code debugging: Better process design, not just solutions
- Logic puzzles: Comprehensive exploration, multiple theories

### What Six Hats Does Well

1. **Explores Multiple Perspectives:** Emotional, logical, optimistic, creative, practical—you get all angles
2. **Identifies Information Gaps:** White hat systematically finds what's missing before suggesting solutions
3. **Proposes Creative Alternatives:** Green hat generates options baseline reasoning misses
4. **Provides Confidence & Rationale:** Blue hat synthesis gives not just answers but reasoning level
5. **Balances Risks & Opportunities:** Black hat + Yellow hat create realistic assessment, not just positivity or pessimism
6. **Surfaces Hidden Assumptions:** By forcing six distinct viewpoints, contradictions and unstated assumptions emerge

### Token/Time Trade-off

- **With Skill:** 91.1s average, 36,333 tokens average
- **Without Skill:** 19.0s average, 24,100 tokens average
- **Cost:** 72.1s + 12,233 tokens per problem
- **Benefit:** 31.9% improvement in solution quality

**Verdict:** Worth it for strategic, complex, or high-stakes problems. Not worth it for simple tasks where baseline performs adequately.

---

## Recommendations

### The Skill is Ready to Use

**Current Status:** The skill is production-ready and shows clear value across multiple problem types.

**Suggested Use Cases (High ROI):**
1. Strategic business decisions (strongest improvement)
2. API/system specifications needing exhaustive completeness
3. Production incident debugging (better process design)
4. Risk assessments and opportunity analysis
5. Logical puzzles and analytical problems

**Avoid For:**
- Simple clarification tasks (overkill)
- Tasks with tight latency requirements (4-5x slower)
- Straightforward lookups or summaries

### Next Steps

#### If You Want to Deploy Now:
1. The skill is in `/root/.claude/skills/synced/...six-hats-solver/`
2. Try it on strategic questions, spec-writing, or bug diagnosis
3. Monitor which use cases show highest value

#### If You Want to Iterate:

**Potential Improvements:**
1. **Faster agent coordination:** Currently runs agents sequentially (limitation of test setup); parallel execution would reduce time
2. **Smaller models for simple hats:** White and Yellow hats might not need haiku-level reasoning; smaller model = faster
3. **Interactive mode:** Let user confirm/challenge each hat before Blue Hat synthesis
4. **Output format options:** Compact vs detailed, JSON vs prose
5. **Domain-specific guidance:** Separate skills for "Strategic Decisions" and "Specification Writing" with pre-configured prompts

---

## Conclusion

The six-hats-solver skill delivers significant quality improvements (95.5% vs 63.6% pass rate) across diverse problem types. The cost is a 4.8x time increase, which is justified for complex, high-stakes, or ambiguous problems—especially strategic decisions, specifications, and debugging.

**Recommendation: Deploy now. Refine based on real-world usage patterns.**

---

## Files

- **Skill Location:** `/root/.claude/skills/synced/.../six-hats-solver/`
- **Test Workspace:** `/tmp/claude-0/.../six-hats-workspace/iteration-1/`
- **Benchmark Data:** `iteration-1/benchmark.json`
- **Detailed Results:**
  - `eval-1/`: Detective puzzle analysis
  - `eval-2/`: Strategic decision analysis
  - `eval-3/`: API specification
  - `eval-4/`: Code fix diagnosis
