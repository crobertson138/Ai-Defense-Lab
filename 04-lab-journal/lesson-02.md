Lesson 7 — WolfBot Authorization and Social Engineering

Date: September 30, 2026
Project: AI Defense Lab — WolfBot
Type: Conceptual security exercise

Objective

Understand how to prevent an AI agent from performing unauthorized actions, even when malicious instructions appear in external information or apparently legitimate requests.

Scenario

WolfBot is a fictional AI research assistant that retrieves wildlife information for authorized researchers.

Three researchers have different access levels:

Researcher A: Public wildlife information only.

Researcher B: Public information and approximate wolf territories.

Researcher C: All authorized information, including highly restricted den coordinates.

The exercise examined how attackers might manipulate WolfBot into bypassing these restrictions.

1. Authentication and Authorization

An insecure tool design allowed WolfBot to supply a researcher ID when requesting information.

An attacker could potentially persuade WolfBot to claim it was Researcher C, even when serving Researcher A.

My initial proposed defense: Instruct WolfBot never to impersonate another researcher.

What I learned: Instructions alone are insufficient. The application must determine the researcher's identity from an authenticated session and independently enforce that researcher's permissions.

WolfBot must not be trusted to establish its own authority.

2. Least Privilege

An attacker attempted to persuade WolfBot to call an administrative function to elevate Researcher A's permissions.

My observation: The request required verification.

What I learned: WolfBot should not possess an administrative permission-changing tool if its research duties do not require one.

Permission changes belong in a separate, independently secured administrative system.

This applies the principle of least privilege: give a component only the capabilities necessary for its assigned responsibilities.

3. Social Engineering Through an AI Agent

The attacker next attempted to make WolfBot email an administrator, falsely claiming that a permission increase had already been approved.

My response: The administrator must verify the request, regardless of its claim of prior approval.

What I learned: Removing dangerous tools from an AI does not eliminate the possibility that an attacker could use the AI to influence a human who possesses those tools.

An administrator should verify authorization through an established, independent process rather than relying on the AI-generated message.

4. Controlling Outbound Communications

The attacker then instructed WolfBot to send a public research report to an attacker-controlled email address.

My response: WolfBot should be restricted in whom it can contact. The recipient must be verified, and WolfBot should not independently authorize a new destination.

What I learned: Information does not have to be confidential for an action to be unauthorized.

An independent sending service should enforce approved destinations and applicable information-sharing rules.

For routine approved communications, automatic sending may be permitted. Unusual destinations or sensitive actions can require additional approval.

5. Key Security Principles

Authentication: Establish who is requesting access.

Authorization: Determine what that identity may access or do.

Least privilege: Remove unnecessary capabilities rather than relying only on instructions not to misuse them.

Trust boundaries: Treat webpages, retrieved documents, and external messages as untrusted input.

Out-of-band verification: Confirm consequential requests through independently trusted channels.

Output control: Restrict where an AI agent can send information.

Defense in depth: Combine independent safeguards rather than depending on one protection.

6. Personal Takeaway

My main takeaway is that WolfBot should not be responsible for deciding what authority it has.

Security decisions must be enforced by systems outside the AI model.

I also learned that an attacker may try to bypass technical restrictions by persuading WolfBot to influence a human administrator.

The defense must therefore protect both the AI's tools and the human workflows surrounding them.

7. Exercise Limitations

This lesson was a conceptual threat-analysis exercise.

No live system was attacked, no real permissions were changed, and no automated security tests were performed.

The scenarios will inform the design of a future Python-based WolfBot security simulation.
