# Git Hooks

This directory contains Git hooks for automating GitFlow processes.

## Available Hooks

### pre-commit
Checks if each directory in the repository has a README file.

**Location:** `.git/hooks/pre-commit`

**What it does:**
- Scans all directories (excluding .git)
- Warns if a directory is missing a README file
- Allows commit to proceed with warnings

### post-merge
Logs merges into the main branch.

**Location:** `.git/hooks/post-merge`

**What it does:**
- Detects merges into the main branch
- Logs merge details to `.git/merge.log`
- Records: date, branch, user, commit hash, and message

## Installation

To install these hooks in your local repository:
```bash
# Copy pre-commit hook
cp hooks/pre-commit .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit

# Copy post-merge hook
cp hooks/post-merge .git/hooks/post-merge
chmod +x .git/hooks/post-merge
```

## Testing

### Test pre-commit hook
```bash
# Create directory without README
mkdir test_dir
echo "test" > test_dir/file.txt
git add test_dir/
git commit -m "Test commit"
# Should show warning about missing README
```

### Test post-merge hook
```bash
# Create and merge a feature
git flow feature start test-feature
echo "test" >> README.md
git add README.md
git commit -m "Test change"
git flow feature finish test-feature

# Merge to main
git checkout main
git merge develop

# Check the log
cat .git/merge.log
```

## Hook Details

### Pre-commit Hook
- **Trigger:** Before each commit
- **Purpose:** Ensure documentation standards
- **Action:** Warns but doesn't block commits

### Post-merge Hook
- **Trigger:** After successful merge
- **Purpose:** Audit trail for main branch
- **Action:** Logs merge information

## Notes

- Hooks are stored in `.git/hooks/` and are not tracked by Git
- Share hooks via the `hooks/` directory
- Team members must install hooks manually
- Hooks can be bypassed with `git commit --no-verify` (not recommended)

## Author

Billy Mwangi
