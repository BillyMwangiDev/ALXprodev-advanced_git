# ALXprodev-advanced_git

Advanced Git workflows and GitFlow practices

## GitFlow Workflow

This repository uses GitFlow for branch management.

### Branch Structure

- **main**: Production-ready code
- **develop**: Integration branch for features
- **feature/**: Feature branches
- **release/**: Release preparation branches
- **hotfix/**: Emergency fixes for production

### Setup
```bash
# Install git-flow
sudo apt install git-flow -y

# Initialize git-flow
git flow init -d
```

## GitFlow Commands

### Features
```bash
# Start a new feature
git flow feature start feature-name

# Finish a feature
git flow feature finish feature-name
```

### Releases
```bash
# Start a release
git flow release start version

# Finish a release
git flow release finish version
```

### Hotfixes
```bash
# Start a hotfix
git flow hotfix start version

# Finish a hotfix
git flow hotfix finish version
```

## Author

Billy Mwangi
- GitHub: [@BillyMwangiDev](https://github.com/BillyMwangiDev)

## Project

Part of ALX DevOps Advanced Git training
Testing hooks

## Git Hooks

This repository uses custom Git hooks for automation:

### Pre-commit Hook
- Checks if directories have README files
- Located at: `.git/hooks/pre-commit`

### Post-merge Hook
- Logs merges into main branch
- Located at: `.git/hooks/post-merge`
- Log file: `.git/merge.log`

### Installation
```bash
# Copy hooks from hooks/ directory
cp hooks/pre-commit .git/hooks/pre-commit
cp hooks/post-merge .git/hooks/post-merge

# Make executable
chmod +x .git/hooks/pre-commit
chmod +x .git/hooks/post-merge
```

See `hooks/README.md` for detailed documentation.
