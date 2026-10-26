Lesson 8 — Defense in Depth, Incident Response, and Network Segmentation

Project: AI Defense Lab — WolfBot
Lesson type: Conceptual cybersecurity exercises

Objective

Learn how multiple independent security controls can protect an AI system when an attacker compromises an application, steals credentials, or attempts to move between systems.

1. Defense in Depth

Defense in depth means using multiple independent security controls rather than relying on a single protection.

For WolfBot, these include:

Multi-factor authentication for human administrators

Database authorization

Least-privilege service accounts

Network segmentation

Credential expiration and revocation

Security monitoring and incident response

What I learned: Compromising WolfBot should not automatically compromise every system it communicates with.

2. Authentication vs. Authorization

In one scenario, an attacker compromised WolfBot's application server and stole its database credentials.

My response: The attacker should not gain access to highly restricted records. I suggested requiring two-factor authentication.

What I learned: MFA is valuable for authenticating human administrators, but database authorization must independently restrict what an authenticated application account can access.

Even valid credentials should not grant permissions beyond those assigned to the account.

3. Credential Security

The attacker attempted to reuse stolen credentials.

My response: Create a barrier that prevents the attacker from logging in again with those credentials.

What I learned: This can be accomplished through credential revocation, rotation, and expiration.

Short-lived credentials reduce the time stolen credentials remain useful. However, a compromised server must also be secured so the attacker cannot simply steal replacement credentials.

4. Incident Response

The attacker retained control of WolfBot's application server even after its credentials were revoked.

My response: Shut down the compromised system to prevent further damage.

What I learned: The first priority is containment. Where practical, isolating the server from the network can stop further malicious activity while preserving evidence.

A typical response includes containment, investigation, eradication, and recovery.

5. Zero Trust and Network Segmentation

WolfBot was operating on the same internal network as an unrelated employee payroll database.

My response: WolfBot should not be able to connect to the payroll database at all. The systems should be kept separate.

What I learned: Network segmentation, firewalls, and access control lists can prevent unnecessary communication between systems.

Zero Trust means that network location alone does not establish authorization.

6. Lateral Movement

An attacker attempted to use a shared internal file server as a stepping stone from WolfBot toward the payroll database.

My answer: Lateral movement.

What I learned: Attackers may attempt to move between compromised systems to reach additional resources.

Network security must account for indirect paths, not just direct connections.

7. Security Architecture Decisions

For the future WolfBot simulation:

WolfBot will have narrowly scoped permissions.

Authorization will be enforced outside the AI model.

Database accounts will have limited privileges.

Administrative functions will be separated from ordinary research operations.

Network access will be restricted to necessary services.

Security-relevant actions will be logged.

Compromised credentials and services must be containable.

8. Personal Takeaway

The most important lesson is that no single security control should be responsible for protecting an entire system.

Even when an attacker compromises an application or obtains legitimate credentials, independent controls should limit the damage.

Security must be designed around the possibility that individual defenses will fail.

9. Exercise Limitations

These were conceptual security scenarios, not live penetration tests.

No real database was attacked, no network was compromised, and no security measurements were collected.

Future Python exercises will test selected security controls in a controlled simulation.
