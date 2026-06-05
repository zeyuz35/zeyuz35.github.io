## 2025-06-05 - Do not fix incidental pre-existing errors
**Learning:** The repository contains pre-existing YAML parsing errors in markdown frontmatter in `_publications/2025-Disentangling.md` which cause `jekyll build` failures.
**Action:** Since these errors are unrelated to the primary task of fixing typos in the markdown generators, I should ignore them and not attempt to fix them to preserve the surgical nature of the PR.
