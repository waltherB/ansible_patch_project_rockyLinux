# Ansible Patch Project

## Git Integration
This project uses Git to track patch versions.

### Initialize Git Repo
```
cd ansible_patch_project
git init
git add .
git commit -m "Initial commit"
```

### Workflow
- After patching test environment, commit version.yml:
```
git add patch_versions/version.yml
git commit -m "Updated patch version"
```
- Push to remote for AAP to use:
```
git push origin main
```


## Git Remote Setup and Branch Strategy
- Initialize remote:
```
git remote add origin <your-repo-url>
```
- Use branches:
  - `main` for production-approved patches
  - `test` for test environment updates

Workflow:
1. Patch test environment and commit to `test` branch.
2. Merge `test` into `main` after approval.
3. AAP pulls from `main` for production.
