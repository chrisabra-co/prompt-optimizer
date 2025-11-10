# Prompt Optimizer for Claude Code

A lightweight slash command for Claude Code that analyzes and optimizes AI prompts using the OTA (Optimize-Then-Answer) Framework. Get better AI responses by transforming vague requests into clear, comprehensive prompts.

## Features

- **Domain Detection** - Automatically identifies prompt domain (code, UX, data, writing, research, finance, product)
- **Clarity Scoring** - Rates prompt clarity from 0-100% based on goal, context, format, criteria, and technical details
- **Risk Detection** - Flags security, privacy, policy, safety, and compliance concerns
- **Smart Questions** - Generates 1-3 targeted questions when clarity < 60%
- **Prompt Enhancement** - Adds domain-specific requirements, output formats, and risk mitigations
- **Zero Context Overhead** - Runs as a slash command without consuming conversation context

## Installation

### Quick Install (Recommended)

1. Download the command file:
```bash
curl -o ~/.claude/commands/optimize-prompt.md \
  https://raw.githubusercontent.com/chrisabra-co/prompt-optimizer/main/.claude/commands/optimize-prompt.md
```

2. Restart Claude Code or reload commands

3. The `/optimize-prompt` command is now available globally!

### Manual Install

1. Clone the repository:
```bash
git clone https://github.com/chrisabra-co/prompt-optimizer.git
cd prompt-optimizer
```

2. Copy the command to your Claude Code configuration:
```bash
mkdir -p ~/.claude/commands
cp .claude/commands/optimize-prompt.md ~/.claude/commands/
```

3. Restart Claude Code

## Usage

### Basic Usage

```bash
# Analyze any prompt
/optimize-prompt [your prompt here]

# Examples
/optimize-prompt help me with my app
/optimize-prompt create a dashboard for analytics
/optimize-prompt write unit tests for auth module
```

### Example: Vague Request

**Input:**
```bash
/optimize-prompt help me with my app
```

**Output:**
```
📊 PROMPT OPTIMIZATION REPORT
================================

🎯 Domain: code
📈 Clarity Score: 25%
⚠️ Risk Flags: None

❓ CLARIFICATION NEEDED
-----------------------
To provide the best response, please answer:
1. What programming language or framework are you using?
2. What specific feature or component are you building?
3. Do you need tests, validation, or security considerations?
```

### Example: Clear Request

**Input:**
```bash
/optimize-prompt Create a REST API for user authentication in Express.js.
Need endpoints for register, login, logout. Use JWT tokens with refresh
token rotation. Store passwords with bcrypt.
```

**Output:**
```
📊 PROMPT OPTIMIZATION REPORT
================================

🎯 Domain: code
📈 Clarity Score: 90%
⚠️ Risk Flags: security

✅ OPTIMIZED PROMPT
-------------------
**Domain:** code

**Original Request:**
Create a REST API for user authentication in Express.js...

**Requirements Based on Domain:**
- Include code summary and complexity notes
- Add security considerations
- Provide test plan and example I/O
- Include error handling strategies
- **CRITICAL:** Address security concerns (authentication, validation, data exposure)

**Output Format:**
- Structured and scannable format
- Include acceptance criteria
- List any assumptions made
- Provide examples where helpful

💡 ENHANCEMENT NOTES
--------------------
- Added: Security requirements, test specifications
- Clarified: Output structure and error handling
- Structure: Domain-specific enhancements applied
```

## How It Works

### 1. Domain Detection
The optimizer uses keyword analysis to identify the primary domain:
- **Code** - Programming, APIs, debugging, implementation
- **UX** - UI design, interfaces, user experience, accessibility
- **Data** - Analytics, statistics, calculations, SQL
- **Writing** - Articles, documentation, content creation
- **Research** - Studies, investigations, comparisons
- **Finance** - ROI, budgets, pricing, revenue
- **Product** - Features, roadmaps, strategy

### 2. Clarity Scoring

| Factor | Weight | Assessment |
|--------|--------|-----------|
| Goal Clarity | 30% | Is there a clear objective? |
| Context | 25% | Are inputs/constraints provided? |
| Format | 15% | Is output format specified? |
| Criteria | 20% | Are success criteria stated? |
| Technical | 10% | Are technical details included? |

### 3. Risk Detection
- **Security** - Authentication, passwords, tokens, vulnerabilities
- **Privacy** - PII, emails, phone numbers, GDPR
- **Policy** - Fake content, bypassing systems, illegal activities
- **Safety** - Harmful or dangerous content
- **Compliance** - Medical/legal/financial advice without expertise

### 4. Smart Questions
When clarity < 60%, generates domain-specific questions:
- Code: Language/framework? Feature details? Testing needs?
- UX: Target users? Platform? Key goals?
- Data: Data structure? Metrics needed? Volume?
- Writing: Audience? Length? Tone?

### 5. Optimization
Adds domain-specific requirements:
- **Code** - Security, tests, error handling, documentation
- **UX** - Accessibility, responsiveness, usability heuristics
- **Data** - Validation, reproducibility, edge cases
- **Writing** - Structure, tone, audience, CTA

## Documentation

### Framework Documentation
- [Optimized Prompts Framework](optimized_prompts.md) - Complete OTA Loop implementation guide
- [Approximation Strategies](APPROXIMATION-STRATEGIES.md) - Advanced techniques for complex prompts
- [Framework Adoption Guide](FRAMEWORK-ADOPTION-GUIDE.md) - Integration patterns and best practices

### Command Customization

The command file is at `.claude/commands/optimize-prompt.md`. You can customize:

1. **Clarity Threshold** - Change when questions are asked (default: 60%)
2. **Question Count** - Adjust number of questions (default: 1-3)
3. **Domain Keywords** - Add domain-specific detection patterns
4. **Risk Patterns** - Extend risk detection rules
5. **Requirements** - Modify domain-specific enhancements

## Benefits

- **Better AI Responses** - Clear prompts generate more accurate, comprehensive outputs
- **Time Savings** - Avoid back-and-forth clarifications
- **Consistency** - Standardized prompt structure across teams
- **Risk Mitigation** - Automatic detection of security and compliance issues
- **Learning Tool** - Teaches effective prompt engineering patterns

## Contributing

Contributions are welcome! Areas for improvement:

- Additional domain detection patterns
- More sophisticated clarity scoring
- Extended risk detection rules
- Internationalization support
- Integration with other AI tools

## License

MIT License - see [LICENSE](LICENSE) file for details

## Support

- **Issues**: [GitHub Issues](https://github.com/chrisabra-co/prompt-optimizer/issues)
- **Documentation**: See the included framework guides
- **Updates**: Watch the repository for new features

## Credits

Based on the original [MCP Prompt Optimizer](https://github.com/grandinh/mcp-prompt-optimizer) by Grandin Harrison. This slash command version was adapted for Claude Code to provide a more lightweight, context-efficient implementation.

---

**Made for better AI interactions with Claude Code**
