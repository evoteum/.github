# Engineering Philosophy

> In order to do more, you must have the discipline to do less.
>
> --*Tristram Oaten, [The Unreasonable Effectiveness Of Plain Text](https://www.youtube.com/watch?v=WgV6M1LyfNY)*

## We are Open
At **evoteum**, we believe in **practical innovation**. We like to solve real-world problems in the open.

## Everything as Code
We are staunch proponents of *Everything as Code*.

If it can be defined in code, it *must* be defined in code. We really do mean *everything*, including but not limited to,  

- **Organisation structure:** repositories, teams, permissions.
- **Governance:**
  - business policies in [OPA](https://www.openpolicyagent.org/) or Kyverno.
- **Knowledge:**
  - documentation in [Markdown](https://www.markdownguide.org/)
  - diagrams in [PUML](https://plantuml.com/)
  - feature requests in [Gherkin](https://cucumber.io/).

Our belief is simple: if it matters, it belongs in code.

That way, we ensure that everything we do is:  
- **Versioned**: every change has history, authorship, and accountability.  
- **Reviewable**: changes can be proposed, discussed, and approved before merging.  
- **Testable**: code can be validated automatically, reducing reliance on manual checks.  
- **Reproducible**: environments and outcomes can be recreated reliably from code.  
- **Automated**: manual toil is eliminated, reducing human error and saving time.  
- **Resistant to complexity bias**: we avoid adding tools unnecessarily by preferring code and conventions over extra moving parts.

## Test everything

Behaviour Driven Development means we start with Cucumber tests, but we do not stop there. We use,
- unit tests
- security tests
- deployment tests
- resilience tests

This ensures our testing is reliable and reduces manual steps.
