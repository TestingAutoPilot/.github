# Security Policy

AutoPilot ships **code that drives real applications** — the platform runners, the
command-line tool, and the MCP server. A plan describes intent, but the runner acts on
the machine it runs on: it clicks, types, launches apps, and (on some backends) runs
shell commands a plan asks for.

That makes two classes of flaw high-impact: anything that lets a **crafted plan** drive
an application or the host in a way the author did not intend, and anything in a runner
or the MCP server that exposes the machine running it.

## Reporting a vulnerability

Do **not** open a public issue. Report privately through
[GitHub Security Advisories](https://github.com/TestingAutoPilot) on the affected repo,
or by email to **jason.schwefel78@gmail.com**.

Please include the repo, a plan or steps that reproduce the issue, and the platform and
version you observed it on.
