# Brown Library GitHub Best practices
## Security

Main security message:

Never Commit Sensitive Information: Avoid committing passwords, API keys, server paths, database-structure info (where reasonably possible), and other confidential data to your repository -- even if the repository is private. 

How to reliably do this?

- Keep private things out of the github code directory: 
- Things to keep out of the github code directory: Private settings, environmental-variable-shell-scripts, and log-files (which can sometimes contain sensitive info). One common pattern is to have a "project_outer_directory" that contains these things (as well as the "project_code_directory"), and have that "project_code_directory" the one that gets committed to github. 
- Utilize Environment Variables: Store sensitive information in environment variables, which are not tracked in version control. Then load these from your code.
- Do not depend on the .gitignore file for security: Rather, get in the habit of thinking of the .gitignore file as keeping messy-unnecessary-cruft out of github (like virtual-environments), not as basic security. Instead, keep the sensitive info out of the github directory in the first place.

## Other recommended GitHub practices...
- Include a README
- Really helpful areas: Purpose, Usage, Installation
- Add a "Description"
- Include "dependencies" in such a way that github can auto-scan them and notify you of vulnerabilities
- If you have a dotenv with private info—as noted above it should not be in the repo—but it's useful to have a "sample_dotenv.txt" file for users to get a sense of what kind of info is required.
- Main branch is special.
- It should always work.
- There should be a "release" for every version of the code actually deployed. (That makes it easier to know which commit to revert back to if there's a problem.)

See also:

- [Best practices for Django projects at BUL](https://github.com/Brown-University-Library/django_template_42_project)

_This document is a draft & will be undergoing revisions._