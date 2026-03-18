# Research Prompt Template

Use this template to generate prompts for external research tools (GPT Deep Research, Perplexity, Gemini).

---

## Template

```
RESEARCH CONTEXT:
I am scoping a new product: {brief product description}.
The product targets {target users} who currently {current problem/workaround}.

RESEARCH GOAL:
{Specific research objective — what you want to learn}

SPECIFIC QUESTIONS:
1. {Sub-question 1}
2. {Sub-question 2}
3. {Sub-question 3}
4. {Sub-question 4}
5. {Sub-question 5}

EXPECTED OUTPUT:
Please provide:
- {Output format item 1, e.g., "A comparison table of top 5 competitors"}
- {Output format item 2, e.g., "Specific data points on market size"}
- {Output format item 3, e.g., "Direct quotes from user reviews"}

SCOPE:
- Focus on {geographic scope}
- Time range: {e.g., "Last 2 years"}
- Include both established players and emerging startups
- Prioritize {what matters most, e.g., "actionable data over general trends"}
```

---

## Guidelines

1. **Be specific about the product context.** The more the research tool knows about what you're building, the more relevant its findings will be.

2. **One research goal per prompt.** Don't combine "competitor analysis" with "pricing strategy" — split them into separate prompts for better depth.

3. **Ask for evidence, not opinions.** Request specific data points, user quotes, pricing pages, and feature lists rather than general assessments.

4. **Define the output format.** Research tools produce better results when you tell them exactly what structure you want back (tables, bullet lists, etc.).

5. **Include scope constraints.** Geographic focus, time range, and company size filters help narrow results to what's relevant.

---

## Example: Competitor Analysis Prompt

```
RESEARCH CONTEXT:
I am scoping a new product: an AI-powered project management tool for small design agencies (5-20 people). The product targets design team leads who currently juggle Asana, Slack, and spreadsheets to track project progress and client feedback.

RESEARCH GOAL:
Identify and analyze the top 5-8 project management tools used by design agencies, focusing on features specific to creative workflows.

SPECIFIC QUESTIONS:
1. Which project management tools are most popular among design agencies specifically?
2. How do these tools handle client feedback and approval workflows?
3. What are the most common complaints from design teams about their current PM tools?
4. Are there any AI-powered PM tools targeting creative teams? What AI features do they offer?
5. What pricing models do these tools use, and what's the typical cost for a 10-person team?

EXPECTED OUTPUT:
- A comparison table: Tool | Target Market | Key Features | AI Features | Pricing (10 users) | G2 Rating
- Top 5 user pain points from reviews (with source links)
- List of any tools with AI features specifically for creative/design workflows

SCOPE:
- Global market, English-language tools
- Last 2 years of reviews and product updates
- Include both established players (Asana, Monday) and niche creative tools
- Prioritize tools that design agencies actually use, not general PM tools
```
