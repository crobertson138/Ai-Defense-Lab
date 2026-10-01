# Lesson 01 — AI Security Fundamentals

**Date:** September 30, 2026
**Project:** AI Defense Lab
**Status:** Conceptual learning — no software experiments performed yet

## Objective

Understand how large language models operate and why AI systems
require independent security controls.

## Concepts Studied

### How large language models work

Large language models process text as tokens. Transformer-based
models use attention mechanisms to process relationships between
tokens and generate outputs. Training adjusts model parameters;
inference uses the trained model to produce responses.

### Model security versus system security

An AI model may be manipulated into requesting an unauthorized
action. This does not necessarily mean the surrounding system
must execute that action.

### Prompt injection

An attacker may place instructions inside lower-trust material
such as webpages, documents, or tool responses. If an AI treats
that content as authoritative instructions, it may attempt
actions outside its intended task.

### Defense in depth

Security should not depend on a single protective measure.
Independent authorization, restricted tool access, network
controls, monitoring, and output protections can reduce the
consequences of model mistakes.

### Least privilege

AI agents should receive only the data and capabilities
necessary for their assigned tasks.

## WolfBot Case Study

WolfBot is a hypothetical wildlife research assistant. We
considered an attacker attempting to manipulate WolfBot into
retrieving restricted wolf-location records and sending them
outside the organization.

Our proposed defense is to prevent unnecessary access to
restricted data, enforce tool permissions outside the model,
and apply additional checks to generated outputs.

## Simulated Red-Team Scenario

A teaching example considered 100 malicious inputs,
12 unauthorized actions attempted, and 0 unauthorized
actions executed because a gateway blocked them.

**Important:** These figures were hypothetical examples,
not measured experimental results.

## My Key Takeaways

- A trusted tool may return untrusted content.
- Authentication establishes identity; authorization
  determines permitted actions.
- A model's decision to attempt an action is different
  from the system allowing it.
- Preventing unnecessary access to sensitive information
  is preferable to relying only on output filtering.
- AI-generated modifications should undergo independent
  evaluation and authorization before deployment.

## Next Steps

1. Design WolfBot's authentication and authorization architecture.
2. Create a simulated database with fictional wildlife records.
3. Implement a Python authorization gateway.
4. Develop controlled prompt-injection tests and record actual results.
