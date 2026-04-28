# Contributing to StreamsHub

Thank you for your interest in contributing to the StreamsHub organization.
All contributors are expected to follow the StreamsHub [Code of Conduct](./CODE_OF_CONDUCT.md).

Individual sub-projects within the StreamsHub organization maintain their own contributing guides with project-specific details such as build instructions, coding conventions, and testing requirements.
This document covers organization-wide contribution policies that apply across all StreamsHub sub-projects.

For information on governance, roles, and voting, see the [Governance Policy](./GOVERNANCE.md).

## AI Contribution Policy

### Overview

Contributors may use AI tools, such as Large Language Models (LLMs), code assistants, and coding agents, when contributing to StreamsHub.
As with any development tool, the contributor is responsible for the quality of the result and for understanding what they submit.

**You are the contributor.**
When you submit a Pull Request (PR) to any StreamsHub sub-project, you certify the contribution as your own work.
AI-generated or AI-assisted content does not change this responsibility.

### Understanding and Responsibility

* You must understand your contribution: Do not submit code, documentation, or other content that you do not fully understand. You should be able to explain to reviewers what your contribution does, how it works, and how you verified it.
* Review all AI-generated content: Before submitting, verify that the contribution is correct, tested, and follows the sub-project's contributing guidelines.
* You own what you submit: As the PR author, you are responsible for all changes, regardless of the tools used to create them. You must certify that you wrote or otherwise have the right to submit the code you are contributing by signing your commits.

### Disclosure

#### When disclosure is required

Disclosure is required when AI tools generate substantial content for your contribution.
Using AI features similar to routine IDE capabilities does not require disclosure.

**Does not require disclosure:**

* Autocomplete and code completion suggestions such as arguments, functions names etc.
* Syntax and formatting suggestions
* Variable or method name suggestions

**Requires disclosure:**

* Functions, classes, or significant code blocks
* Test cases or test suites
* Documentation content
* Bug fix implementations

#### How to disclose

Commits with substantial AI assistance must include an `Assisted-by` trailer identifying the tool used.
For example:

```
Assisted-by: GitHub Copilot
Assisted-by: Claude Sonnet 4
```

You can add this trailer using:

```bash
git commit -m "Your commit message

Assisted-by: ToolName"
```

AI tools can also be configured to add this trailer automatically on commit.

If AI tools were used significantly across a PR, note this in the PR description as well to give reviewers additional context.

#### Commit trailer restrictions

AI tools **must not** appear in `Signed-off-by`, `Co-authored-by`, `Co-developed-by`, or similar commit trailers that imply authorship or legal certification.
Only humans can certify the [Developer Certificate of Origin (DCO)](https://developercertificate.org/).
AI is not a legal entity and cannot make this certification.

### What Not to Do

* Do not submit code you do not understand: If you cannot explain the reasoning behind your changes during review, the PR may be closed.
* Do not let AI respond to reviewers on your behalf: When maintainers, component owners, or other contributors provide feedback on your PR, you may use AI tools to help formulate responses, but you must fully understand and take ownership of what you write. Reviewers want to engage with you, not receive generic AI-generated responses.
* Do not submit large, unfocused PRs: AI tools can generate content faster than reviewers can read it. Keep PRs focused and appropriately sized. Maintainers may close pull requests that are too large to review effectively or where the contributor does not appear to understand the changes.
* Do not open multiple AI-generated PRs in rapid succession: Submitting many PRs at once overwhelms reviewers and may result in PRs being closed.
* Avoid unnecessary verbosity: Trim down AI-generated PR descriptions, commit messages, and code comments. Be clear, concise, and specific. Respect the time of maintainers and reviewers.

### Quality Standards

* Meet the same standards: AI-assisted contributions are reviewed to the same standard as any other contribution. Code must be correct, maintainable, well-tested, and consistent with sub-project conventions.
* Ensure licensing compliance: You must ensure that AI-generated content does not introduce material under licenses incompatible with the project's [Apache 2.0 License](./LICENSE).
* Test your changes: All code contributions must be tested according to the sub-project's standards, whether AI-assisted or not.

### AI-Assisted Pull Request Reviews

Automated or AI-assisted reviews can supplement the review process but do not replace review by maintainers or component owners.

* AI reviews do not replace human review: AI-generated review comments can provide useful signals, but they do not satisfy the project's [review requirements](./GOVERNANCE.md#pr-approval-rules).
* Humans make the decisions: Maintainers and component owners make merge decisions following the project's [governance framework](./GOVERNANCE.md#pr-approval-rules).
* Do not invoke AI review tools on project PRs: While you may use AI tools to review your code privately during development, do not invoke AI bots or tools to post review comments on StreamsHub PRs. Where AI-assisted review is desired, maintainers will request it.

### Consequences of Non-Compliance

Pull requests that violate this policy may be closed. This includes:

* PRs where the contributor cannot explain or defend the changes during review.
* PRs with generic, inauthentic responses to reviewer feedback that demonstrate a lack of understanding.
* Large, unfocused PRs that appear to be bulk AI-generated content.

### Questions

If you have questions about this policy or are unsure whether your use of AI tools requires disclosure, please contact the [maintainers](./MAINTAINERS).
