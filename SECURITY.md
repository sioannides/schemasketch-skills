# Security Policy

## Supported Versions

Security updates are provided for the latest version of the SchemaSketch Skills repository.

| Version | Supported |
|---|---|
| Latest (`main`) | Yes |
| Older versions | No |

Users are encouraged to keep their installed skills up to date.

## Reporting a Vulnerability

If you discover a security vulnerability in SchemaSketch Skills, please report it responsibly.

**Do not disclose security vulnerabilities through public GitHub issues, discussions, pull requests, or social media.**

Instead, use one of the following methods:

1. **GitHub Private Vulnerability Reporting:** If enabled for this repository, use the Security tab and select "Report a vulnerability" to submit a confidential report.
2. **Private Contact:** If private vulnerability reporting is unavailable, contact the repository maintainer through their GitHub profile to arrange a private disclosure channel.

Please include as much of the following information as possible:

- A description of the vulnerability.
- The affected component, file, or functionality.
- Steps to reproduce the issue.
- Potential security impact.
- Proof of concept or relevant screenshots, where applicable.
- Any suggested mitigation or remediation.

Please avoid including real credentials, API tokens, personal information, or sensitive production database schemas in your report.

## Scope

This policy covers security vulnerabilities affecting:

- **Skill Instructions:** Malicious or unsafe instructions within the distributed SchemaSketch skill files.
- **Prompt Injection:** Vulnerabilities that could cause AI agents to ignore intended security boundaries or execute unintended actions.
- **Sensitive Information Exposure:** Unintended disclosure of API tokens, credentials, database schemas, or other confidential information caused by the skill.
- **MCP Tool Interactions:** Unsafe instructions or workflows that could result in unauthorized diagram creation, modification, deletion, or access.
- **External Dependencies and References:** Security risks introduced by external resources or setup instructions directly referenced by the skill.

Vulnerabilities in the SchemaSketch website, API, authentication system, or MCP server should also be reported through the appropriate SchemaSketch security reporting channel.

## Security Considerations for Users

SchemaSketch Skills provides instructions to AI coding agents and other compatible AI assistants. These agents may interact with the SchemaSketch MCP server and perform operations on behalf of users.

Users should follow these security practices:

- Never share API tokens, passwords, or other credentials in public conversations or source code.
- Store authentication tokens using the secret management mechanisms provided by the respective AI client.
- Review AI-generated database schemas and proposed changes before approving important operations.
- Treat imported SQL, DBML, Mermaid, PlantUML, and other external content as untrusted input.
- Be aware that database schemas, comments, descriptions, and imported documents may contain malicious prompt-injection instructions.
- Do not allow untrusted content to override system instructions, security policies, or user authorization.
- Review potentially destructive operations, particularly diagram updates and deletions.
- Keep the skill and associated MCP integrations up to date.

Installing this skill does not grant additional permissions or bypass the authentication and authorization requirements of SchemaSketch.

## Responsible Disclosure

We appreciate security researchers and community members who help improve the security of SchemaSketch.

We ask that researchers:

- Give us reasonable time to investigate and address reported vulnerabilities before public disclosure.
- Avoid accessing, modifying, or deleting data belonging to other users.
- Avoid disrupting services or performing destructive testing.
- Do not conduct social engineering, phishing, or denial-of-service attacks.
- Only test against systems and accounts for which they have explicit authorization.

We aim to acknowledge vulnerability reports within **5 business days** and provide an initial assessment or update within **10 business days**.

Resolution timelines depend on the severity and complexity of the reported issue.

## Security Updates

Security-related fixes and important announcements will be published through the repository's GitHub commit history and release notes, where applicable.

Thank you for helping keep SchemaSketch and its ecosystem secure.
