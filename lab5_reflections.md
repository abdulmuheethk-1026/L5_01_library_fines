# Lab 5: Static Code Analysis — Reflections

## 1. What did you learn from using static analysis tools?

I learned that static analysis tools can identify potential problems without requiring the program to be executed. Pylint helped me improve code quality and maintainability, Bandit highlighted insecure coding patterns, and Flake8 helped me follow Python formatting conventions.

## 2. Which issue was the most important to fix, and why?

The use of `eval()` was particularly important because it could execute arbitrary Python expressions. I replaced it with an AST-based evaluator that accepts only selected arithmetic operations and the permitted `days` variable. This allows the intended fine-calculation rule to work without evaluating arbitrary Python code.

## 3. How did the tools complement one another?

Pylint focused on code quality, naming, documentation, and programming practices. Bandit focused on potential security vulnerabilities. Flake8 identified formatting and style violations. Using all three provided a more comprehensive assessment than relying on a single tool.

## 4. What challenges did you face while fixing the issues?

Some fixes required more than changing formatting. For example, replacing `eval()` required implementing a restricted arithmetic evaluator, while removing global-variable warnings required restructuring how the daily fine rate was stored. I also had to correct indentation and blank-line spacing before the tools could report clean results.

## 5. How did you verify that your fixes worked?

I reran all three tools after modifying the source file. Pylint returned a score of 10.00/10, Flake8 produced no reported issues, and Bandit reported no issues identified. I also used Python's compilation check to confirm that the file had no syntax errors.

## 6. How can static analysis be useful in future projects?

Static analysis can be incorporated into regular development workflows and automated checks. Running these tools before committing code can help detect defects, unsafe coding practices, and style violations early, improving software quality and making collaboration easier.

## Conclusion

This lab demonstrated that static analysis is useful for improving software quality, security, and consistency. Combining Pylint, Bandit, and Flake8 helped me identify and correct multiple issues and verify the resulting improvements.