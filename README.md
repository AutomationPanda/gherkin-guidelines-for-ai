# Gherkin Guidelines for AI Specs, Agents, and Skills

[`gherkin-guidelines.md`](gherkin-guidelines.md)
provides guidelines for writing _good_ Gherkin scenarios.
Read it to learn how to formulate robustly readable scenarios by hand.
Feed it as context to AI specs, agents, and skills to generate scenarios for acceptance criteria and test cases.


## Quick start

1. **Get the file.** Copy [`gherkin-guidelines.md`](gherkin-guidelines.md) into your repo, or work from this repository’s copy.
2. **Give it to the agent.** Paste the full contents into a chat, add it as project context, or reference it in a prompt (for example, `@gherkin-guidelines.md` in Cursor).
3. **Prompt with scope.** Ask for a `*.feature` (or scenarios) and name the product area, actors, and the behaviors or acceptance criteria you want covered.
4. **Optional:** Point the agent at the **Recommended template** section in `gherkin-guidelines.md` if you want a skeleton structure as a starting point.


## Choices

The guidelines make a few opinionated choices regarding style.
The table below outlines what choices are embedded into the guidelines,
as well as what reasonable alternatives could be.
To select an alternative, edit [`gherkin-guidelines.md`](gherkin-guidelines.md) where choices are made.
(Use AI coding agents to help.)

| Aspect | Choice | Alternatives |
| ------ | ------ | ------------ |
| *Gherkin syntax* | Cucumber-compatible | Other BDD frameworks |
| *Feature file name* | kebab-case | snake_case or UpperCamelCase |
| *Tags* | Not specified | What to use and where to use them |
| *Indentation* | 2 spaces | 4 spaces or tabs |
| *Blank lines* | 1 line between sections | Other line spacing rules |

> [NOTE]
> For a specific Gherkin dialect, you may need to provide examples of syntax
> or even a full language spec for AI to use it properly.


## AI Integration

[`gherkin-guidelines.md`](gherkin-guidelines.md)
should be treated as a context file for AI coding agents like Claude, Cursor, Codex, or Copilot.
There are multiple ways that you could integrate it with AI coding techniques:

- **Pure vibes:** Copy-paste the whole file's contents into an AI chat window and then prompt it to generate Gherkin scenarios based on its rules.

- **Direct reference:** Add this file to your project and reference it directly when prompting to generate Gherkin scenarios: "Following the rules in `@gherkin-guidelines.md`, generate a feature file that ..."

- **Rules:** Add a rule for your AI coding agent to always follow these guidelines when writing and reviewing Gherkin scenarios. Follow the rule conventions of your chosen AI agent.

- **Skills or sub-agents:** Convert this document into a skill or sub-agent and provide it to your AI coding agent.

- **Context engineering:** Create a body of context files that document how the project should be developed. Hook it up to rules, skills, and sub-agents. Add the guidelines to the context files.

> [IMPORTANT]
> Each coding agent has different ways to establish rules and set up context.
> Be sure to read their docs so you know how to set things up properly.
> Otherwise, the agents might ignore these Gherkin guidelines!


## Use Cases

There are a few ways you could use the Gherkin guidelines in your projects:

- **BDD test automation:** If you use a BDD test framework like Gherkin, then you could use the Gherkin guidelines to generate new scenarios or modify existing scenarios. You could also use the guidelines to assist agentic code reviews for test code.

- **Test planning:** Even without a BDD test framework, you could generate functional test specs written in Gherkin to follow good testing practices like Arrange-Act-Assert and test case independence. Then, you could use those specs to generate test scripts using whatever language and test framework you wish.

- **Exploratory testing:** Use [Playwright MCP with agents](https://playwright.dev/mcp/introduction) or [Playwright CLI with skills](https://playwright.dev/agent-cli/introduction) to explore a web app and then record the existing behaviors as Gherkin scenarios to explain what was discovered.

- **Acceptance criteria:** You could generate rich acceptance criteria in the format of Gherkin scenarios for user stories while the user stories are being written. This would force the team to think through behavior patterns and edge cases before any code is written.

- **Spec-driven development:** You could add the guidelines to a project's context files and then define an agentic workflow with humans in the loop to generate feature specs with Gherkin scenarios as part of the reviewable acceptance criteria. Then, implementation would generate both product code and test code from the approved feature specs.


## Example Prompt

```text
Following @gherkin-guidelines.md, write one Cucumber-compatible `*.feature` file for a simple e-commerce web app.

Feature area: Shopping cart
Behaviors to cover (nothing else):
- A signed-in shopper adds one product to the cart from the product page.
- From the cart page, the shopper increases line quantity; the line total reflects the new quantity.
- The shopper removes the item; the cart shows an empty state.

Use concrete product names and prices. Do not write step definitions.
```
