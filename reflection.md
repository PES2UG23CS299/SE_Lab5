REFLECTION: 
1. Which issues were the easiest to fix, and which were the hardest? Why? 
The easiest issues to fix were missing docstrings and line-length violations . These 
required straightforward textual additions or line breaks without affecting program 
logic. 
The logging format warnings were also easy once I understood that Pylint prefers 
lazy % formatting instead of f-strings within logging statements. 
The hardest issues involved broad exception handling and input validation. These 
required reasoning about what exceptions might realistically occur and refactoring 
the code to safely catch specific exceptions without breaking functionality. Properly 
restructuring those parts took more time and testing. 
2. Did the static analysis tools report any false positives? If so, describe one example. 
There was a minor case that felt like a false positive from Pylint regarding the global 
keyword usage . While technically correct that globals can be risky, in this small, 
single-file program it was necessary to maintain shared state . The tool flagged it as a 
design concern, but in this specific context it wasn’t an actual problem or security 
issue. 
3. How would you integrate static analysis tools into your actual software development 
workflow? 
I would integrate Pylint, Flake8, and Bandit directly into a Continuous Integration (CI) 
pipeline . Each commit or pull request would automatically trigger these tools to 
enforce code quality standards. 
Locally, I would also configure pre-commit hooks so that developers get immediate 
feedback before pushing changes. 
This approach ensures consistent quality control, catches potential bugs early, and 
helps the team maintain clean, secure, and readable code.
4. What tangible improvements did you observe in the code quality, readability, or 
potential robustness after applying the fixes? 
The code became much cleaner and more consistent, especially with proper 
docstrings, standardized logging, and shorter line lengths. 
By replacing except: with specific exceptions, error handling became safer and more 
predictable. 
Using input validation improved robustness against invalid or unsafe data. 
The removal of unsafe functions like eval() improved security. 
Overall, the program is now easier to maintain, more readable, and less 
error-prone—qualities that would significantly help in a real production environment.
