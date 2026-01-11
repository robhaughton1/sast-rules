## SAST Rules
A collection of custom Semgrep rules focused on identifying insecure patterns in JavaScript and Node.js applications.

## Purpose
This repository is a personal static analysis lab where I write and maintain custom Semgrep rules. 
The goal is to understand how vulnerabilities appear in code and how to detect them using pattern-based analysis.

## Running the Rules (for future reference)
Install Semgrep:

    pip install semgrep

Run all rules in this repository:

    semgrep --config ./semgrep-rules .

    ## Example Vulnerable Code

## Rules

### 1. no-eval.yaml
Detects any usage of `eval()` in JavaScript. 
`eval()` executes arbitrary code and can lead to code injection vulnerabilities.

### 2. exec-command.yaml 
Will detect usage of `child_process.exec()` in Node.js, a common sink for command injection.


