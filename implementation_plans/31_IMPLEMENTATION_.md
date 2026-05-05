# Replace main Branch with prePhone

The goal is to replace the `main` branch with the `prePhone` branch, effectively making `main` point to the same commit as `prePhone`. This is often done when a feature branch (or a specific state) should become the new primary state of the repository.

## User Review Required

> [!WARNING]
> This operation involves a `git reset --hard`, which will overwrite any unique commits on the `main` branch that are not in `prePhone`. Please ensure that no important work on `main` will be lost.

> [!IMPORTANT]
> If the `main` branch is pushed to a remote repository, a force push (`git push --force`) will be required to update the remote. This can disrupt other collaborators if they have based work on the old `main`.

## Proposed Changes

The following steps will be taken to perform the branch replacement:

1. **Verify Clean State**: Ensure there are no uncommitted changes in the current working directory.
2. **Switch to main**: Checkout the `main` branch.
3. **Reset main to prePhone**: Use `git reset --hard prePhone` to align `main` with `prePhone`.
4. **Push Changes (Optional/As Needed)**: Force push to the remote `main` if required.

## Checklist

- [x] Ensure working directory is clean (`git status`)
- [x] Switch to the `main` branch (`git checkout main`)
- [x] Reset `main` to match `prePhone` (`git reset --hard prePhone`)
- [x] (Optional) Force push to remote (`git push origin main --force`)

## Verification Plan

### Automated Tests
- Run `git log main..prePhone` and `git log prePhone..main` to ensure both branches point to the same commit.

### Manual Verification
- Check the application state on the `main` branch to ensure it matches the expected state from `prePhone`.
