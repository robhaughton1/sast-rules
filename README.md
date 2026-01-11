# SAST Rules

A collection of custom Semgrep rules designed to detect insecure patterns in JavaScript and Node.js applications. This repository serves as a personal static analysis lab where I practice writing rules, understanding vulnerability patterns, and building foundational SAST intuition.

## Running the Rules

Install Semgrep:

    pip install semgrep

Run all rules in this repository:

    semgrep --config ./semgrep-rules .

## Rules

### 1. no-eval.yaml
Detects any usage of `eval()` in JavaScript.  
`eval()` executes arbitrary code and can lead to code injection vulnerabilities.

### 2. no-child-exec.yaml
Detects calls to `child_process.exec()` in Node.js.  
This function executes shell commands and may allow command injection if untrusted input reaches it.

## Example Vulnerable Code

```js
// Example flagged by no-eval.yaml
const userInput = req.query.value;
eval(userInput);

// Example flagged by no-child-exec.yaml
const cmd = req.body.command;
child_process.exec(cmd);
