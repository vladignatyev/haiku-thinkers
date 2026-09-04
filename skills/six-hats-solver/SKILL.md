---
name: six-hats-solver
description: Use the six hats method with multiple agents to solve complex logical problems, complete specifications, or generate strategies. Trigger this when you need comprehensive analysis of a problem from multiple perspectives—detective puzzles, strategic decisions, incomplete specifications, code defects, or any situation where rigorous multi-angle thinking unlocks better solutions. The skill spawns six independent agents (one per hat), each analyzing from a distinct viewpoint, then synthesizes their insights into a coherent solution.
compatibility: Requires Workflow tool for multi-agent orchestration
---

# Six Hats Problem Solver

The six hats method (Edward de Bono) structures thinking by separating it into six distinct modes. Instead of trying to think about everything at once, each "hat" focuses on one type of thinking. This skill engages six haiku agents in parallel—each wearing a different hat—to analyze your problem comprehensively, then synthesizes their findings into a unified solution.

## When to Use This Skill

Use this skill whenever you need rigorous multi-perspective analysis:

- **Detective puzzles & logical problems**: Find the solution by examining clues, contradictions, emotions, risks, and creative interpretations
- **Strategic decisions**: Evaluate business moves, product directions, or complex choices
- **Specification completion**: Fill gaps in incomplete documents, designs, or requirements with internal consistency
- **Code fixes & debugging**: Understand a bug from multiple angles—what are the facts, what could go wrong, what's the creative fix?
- **Process design**: Improve workflows, policies, or systems by thinking through all dimensions
- **Risk assessment**: Identify and mitigate threats while staying grounded in facts and exploring opportunities

## How It Works

You provide a problem or incomplete specification. The skill:

1. **Spawns six agents** in parallel, each analyzing from a distinct perspective:
   - **White Hat**: Gathers facts, identifies information gaps, asks clarifying questions
   - **Red Hat**: Explores emotions, intuitions, aesthetic judgments, creative impulses
   - **Black Hat**: Identifies risks, weaknesses, logical flaws, contradictions, worst-case scenarios
   - **Yellow Hat**: Explores benefits, optimistic scenarios, strengths, opportunities, best-case outcomes
   - **Green Hat**: Generates creative alternatives, lateral thinking, new approaches, unconventional solutions
   - **Blue Hat**: Synthesizes all perspectives into a coherent analysis and recommends next steps

2. **Synthesizes insights** into a comprehensive solution that accounts for facts, risks, opportunities, and creative thinking

## Usage

Paste your problem or incomplete specification below, and the skill will guide each agent through their analysis.

### Parameters (Optional)

Control the analysis depth and breadth with these parameters:

**Thoroughness** (how deeply each hat explores):
- `quick` (1-2 minutes): Surface-level insights, brief analysis per hat
- `moderate` (5-10 minutes): Balanced depth, standard analysis [DEFAULT]
- `deep` (15-30 minutes): Exhaustive exploration, comprehensive findings per hat
- **Numeric:** 1-10 scale where 1=quick, 5=moderate, 10=deep

**Breadth** (how wide the exploration spans):
- `narrow` (focused): 1-2 alternatives, concentrate on most likely scenario
- `balanced` (standard): 3-5 alternatives, explore major branches [DEFAULT]
- `wide` (comprehensive): 7+ alternatives, exhaustively map solution space
- **Numeric:** 1-10 scale where 1=narrow, 5=balanced, 10=wide

**Example usage:**
- Quick strategic decision: `thoroughness=quick, breadth=balanced`
- Exhaustive specification: `thoroughness=deep, breadth=wide`
- Rapid bug diagnosis: `thoroughness=moderate, breadth=narrow`

### Input Format

Provide:
- A clear problem statement, puzzle, specification gap, or challenge
- Any relevant context, constraints, or known facts
- What you're trying to accomplish (solve, complete, decide, fix)
- *Optional:* `thoroughness` and `breadth` parameters (see above)

### Output Format

The skill delivers:
- **White Hat analysis**: Known facts, information gaps, clarifications needed
- **Red Hat analysis**: Intuitive reactions, emotional insights, gut assessments
- **Black Hat analysis**: Risks, weaknesses, contradictions, potential failures
- **Yellow Hat analysis**: Benefits, opportunities, strengths, best-case scenarios
- **Green Hat analysis**: Creative alternatives, unconventional approaches, lateral solutions
- **Blue Hat synthesis**: Integrated conclusion, recommended solution or next steps, confidence assessment

## Example

**Input:**
"We're thinking about pivoting to focus on mobile-first for our B2B SaaS platform. Currently 60% desktop, 40% mobile usage. Engineering says it would take 4 months and 2 engineers. Should we do it?"

**Output would include:**
- White Hat: Current stats, engineering capacity, user demographics breakdown
- Red Hat: Founder's excitement about mobile + team concerns about scope
- Black Hat: Risks of neglecting desktop, engineering delays, customer churn during transition
- Yellow Hat: Competitive advantage, future-proofed product, team motivation, market expansion
- Green Hat: Hybrid approach (partial pivot), selective features, phased rollout, partnership options
- Blue Hat: Recommendation balancing all factors with confidence level and decision criteria

## Tips for Best Results

1. **Be specific**: The more detail you provide about the problem, the better each agent's analysis
2. **Include constraints**: Mention budget, timeline, resource limits—these matter to the analysis
3. **State your goal clearly**: Are you trying to decide, complete, fix, or understand?
4. **Trust the diversity**: The contradiction between hats (Black vs Yellow) is a feature, not a bug—it highlights real tensions
5. **Use the Blue Hat synthesis**: That's where the real value is—where multiple perspectives crystallize into actionable insight

---

## How to Use This Skill (For Claude)

When invoked, follow this process:

### Step 0: Parse Parameters
Extract `thoroughness` and `breadth` from the user's input (or use defaults):
- **Thoroughness default:** `moderate` (5-10 minute analysis per hat)
- **Breadth default:** `balanced` (3-5 alternatives explored)

Map values to agent instructions:
- **thoroughness=quick** (1-5): Brief per-hat analysis, minimal expansion
- **thoroughness=moderate** (5-6): Standard depth, explore main branches
- **thoroughness=deep** (7-10): Exhaustive analysis, deep exploration of edge cases

- **breadth=narrow** (1-3): Focus on 1-2 most likely scenarios/solutions
- **breadth=balanced** (5-6): Explore 3-5 key alternatives
- **breadth=wide** (8-10): Generate 7+ alternatives, exhaustive exploration

### Step 1: Parse the Problem
Read the user's problem statement and identify:
- What type of problem (puzzle, strategy, specification, bug, etc.)
- What constraints exist
- What the desired outcome is
- Extract thoroughness and breadth parameters (or use defaults)

### Step 2: Spawn Six Agents in Parallel

Use the Workflow tool (or Agent tool if Workflow unavailable) to spawn six independent agents, one per hat. Each agent should receive the problem PLUS the thoroughness/breadth parameters to guide their analysis depth:

**Agent 1 - White Hat (Facts)**
- Task: Analyze the problem objectively, identifying all known facts
- Focus: Data gathering, information gaps, assumptions vs certainties
- **Thoroughness adjustment:**
  - Quick: List 3-5 key facts and top gap
  - Moderate: List facts systematically, identify 5-8 gaps (DEFAULT)
  - Deep: Exhaustive fact inventory, 10+ gaps with follow-up questions
- Output: Factual summary with clear gaps and clarifying questions

**Agent 2 - Red Hat (Emotions)**
- Task: Provide intuitive, emotional, aesthetic perspective
- Focus: Gut reactions, creative impulses, emotional stakes for stakeholders
- **Thoroughness adjustment:**
  - Quick: 1-2 emotional reactions only
  - Moderate: Stakeholder emotions for 3-4 personas (DEFAULT)
  - Deep: Deep emotional landscape for all stakeholders, emotional triggers, biases
- Output: Intuitive assessment, emotional landscape, aesthetic judgments

**Agent 3 - Black Hat (Critical)**
- Task: Identify all weaknesses, risks, and potential failures
- Focus: What could go wrong, logical flaws, contradictions, worst-case scenarios
- **Breadth adjustment:**
  - Narrow: Top 2-3 risks only
  - Balanced: 4-6 major risk categories (DEFAULT)
  - Wide: 7+ risk angles, including unlikely but catastrophic scenarios
- Output: Comprehensive risk and weakness analysis

**Agent 4 - Yellow Hat (Optimistic)**
- Task: Explore benefits, opportunities, and best-case scenarios
- Focus: Strengths, positive outcomes, value creation, why this could succeed
- **Breadth adjustment:**
  - Narrow: 1-2 main benefits
  - Balanced: 3-4 opportunity classes (DEFAULT)
  - Wide: 6+ benefit categories, including second-order effects
- Output: Opportunity analysis and optimistic scenarios

**Agent 5 - Green Hat (Creative)**
- Task: Generate alternative approaches and unconventional solutions
- Focus: Lateral thinking, new angles, creative combinations, breaking constraints
- **Breadth adjustment:**
  - Narrow: 1-2 alternatives only
  - Balanced: 3-5 creative alternatives (DEFAULT)
  - Wide: 7+ alternatives including radical/unconventional approaches
- **Thoroughness adjustment:**
  - Quick: Brief idea descriptions
  - Moderate: Full concept + pros/cons (DEFAULT)
  - Deep: Detailed exploration of each alternative with implementation considerations
- Output: Alternative solutions and creative approaches

**Agent 6 - Blue Hat (Synthesis)**
- Task: Wait for other agents' outputs, then synthesize all perspectives
- Focus: Integration, pattern-finding, coherent conclusion, actionable next steps
- **Thoroughness adjustment:**
  - Quick: Quick recommendation + 1 action
  - Moderate: Integrated conclusion, recommendation, 3-5 next steps (DEFAULT)
  - Deep: Detailed integration showing how hats influenced decision, confidence analysis, comprehensive action plan
- Output: Integrated analysis and clear recommendation

### Step 3: Gather Outputs
Collect all six agent analyses. They should be independent perspectives, not debating each other.

### Step 4: Present Results
Format the complete analysis for the user, organized by hat with each perspective clearly labeled. Include:
- Each hat's analysis (5 independent perspectives)
- Blue Hat's synthesis tying everything together
- Clear recommendation or next steps from the integrated view

### Key Principles
- **Independence**: Each agent thinks independently without knowing the others' outputs (except Blue Hat)
- **Completeness**: Every hat gets to fully express its perspective
- **Synthesis**: Blue Hat doesn't average or compromise—it finds the genuine integrated insight
- **Clarity**: Contradictions between hats are preserved and explained, not eliminated
