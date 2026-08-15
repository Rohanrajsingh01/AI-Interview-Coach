# Definition of Done

A user story is **Done** when *all* of the following are true.

1. **Implementation complete** — every acceptance criterion is implemented on a feature branch.
2. **Relevant tests pass** — unit tests for new logic exist and pass; integration tests are added where the story crosses module boundaries.
3. **No known critical defects** — no Severity-1 or Severity-2 bugs remain for the implemented behaviour.
4. **Code reviewed** — at least one team member other than the author has reviewed the change.
5. **Documentation updated** — `README.md`, relevant `docs/` files, and inline comments reflect the change.
6. **Changes committed** — the feature branch is committed with a meaningful message (Conventional Commits: `feat:`, `fix:`, `chore:`, `docs:`, `test:`).
7. **Merged into `main`** — the change is merged.
8. **Demo evidence recorded** — for user-visible stories, a screenshot, anonymised sample, or short written transcript of the demo is linked from the work item.
9. **Sprint evidence recorded** — the story is moved to **Completed** in `docs/product-backlog.md` with the merge commit hash noted.

## Constraints

- Personal CVs, recorded audio / video, faces, and participant data are **never** committed, even as demo evidence. Demo artefacts must be synthetic or fully anonymised.
- A partially complete story is either **carried over** with explicit re-planning in the next sprint or **split** into smaller stories whose completed pieces are marked Done individually.

A story is **not** Done if any of the checklist items above are unmet. It stays **In Progress** and remains in the active sprint.