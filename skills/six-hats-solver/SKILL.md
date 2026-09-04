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

### Input Format

Provide:
- A clear problem statement, puzzle, specification gap, or challenge
- Any relevant context, constraints, or known facts
- What you're trying to accomplish (solve, complete, decide, fix)

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

### Step 1: Parse the Problem
Read the user's problem statement and identify:
- What type of problem (puzzle, strategy, specification, bug, etc.)
- What constraints exist
- What the desired outcome is

### Step 2: Spawn Six Agents in Parallel

Use the Workflow tool (or Agent tool if Workflow unavailable) to spawn six independent agents, one per hat. Each agent should receive:

**Agent 1 - White Hat (Facts)**
- Task: Analyze the problem objectively, identifying all known facts
- Focus: Data gathering, information gaps, assumptions vs certainties
- Output: Factual summary with clear gaps and clarifying questions

**Agent 2 - Red Hat (Emotions)**
- Task: Provide intuitive, emotional, aesthetic perspective
- Focus: Gut reactions, creative impulses, emotional stakes for stakeholders
- Output: Intuitive assessment, emotional landscape, aesthetic judgments

**Agent 3 - Black Hat (Critical)**
- Task: Identify all weaknesses, risks, and potential failures
- Focus: What could go wrong, logical flaws, contradictions, worst-case scenarios
- Output: Comprehensive risk and weakness analysis

**Agent 4 - Yellow Hat (Optimistic)**
- Task: Explore benefits, opportunities, and best-case scenarios
- Focus: Strengths, positive outcomes, value creation, why this could succeed
- Output: Opportunity analysis and optimistic scenarios

**Agent 5 - Green Hat (Creative)**
- Task: Generate alternative approaches and unconventional solutions
- Focus: Lateral thinking, new angles, creative combinations, breaking constraints
- Output: Alternative solutions and creative approaches

**Agent 6 - Blue Hat (Synthesis)**
- Task: Wait for other agents' outputs, then synthesize all perspectives
- Focus: Integration, pattern-finding, coherent conclusion, actionable next steps
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
