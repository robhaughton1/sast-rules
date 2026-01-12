# SAST Rules

A collection of custom Semgrep rules designed to detect insecure patterns in JavaScript and Node.js applications. This repository serves as a personal static analysis lab where I practice writing rules, understanding vulnerability patterns, and building foundational SAST intuition.

## Running the Rules

Install Semgrep:

    pip install semgrep

Run all rules in this repository:

    semgrep --config ./semgrep-rules .

## Rules

### 1. python-string-concatenation
Detects any usage of string concatenation in Python
This is a simple rule suggesting there is a less messy way to create strings.

// Example flagged by python-string-concatenation
print("Hello" + name)
// Example not flagged
print(f"Hello {name}")
