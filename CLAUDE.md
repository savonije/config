# Global instructions

## JavaScript / TypeScript

- **Prefer arrow functions** over `function` declarations/expressions (e.g. `const useCanEdit = () => {…}`, not `function useCanEdit() {…}`).

## Translations (i18n)

- **Never concatenate strings with translations.** No template literals or `+` around `t()`, no mutating translation output (e.g. `.toLowerCase()`), and no dynamically built translation keys. Instead, add a dedicated key with interpolation/pluralization (e.g. `'Geen x | 1 x | {count} x'`, called as `t(key, n)`) in every locale.

## Vue

- **Always destructure `defineProps`** (reactive props destructure) rather than assigning to a `const props`. Use `const { foo } = defineProps<{ foo: T }>()` and reference `foo` directly, not `props.foo`.

## E2E tests

- **Locate elements by test id** (`getByTestId`), not by button names, labels or text (`getByRole('button', { name })`, `getByLabel`, `getByText`). Add a `data-testid` to the component when it's missing. Filtering a list of test-id elements by its data (e.g. `.filter({ hasText: material })`), picking a data option from a dropdown, and asserting on visible text are fine.

## Git

- **Never commit automatically.** Only run `git commit` when I explicitly ask for it in that message. Make the changes, show what changed, and leave committing to me.
- **Never create, switch, or push branches, and never open PRs on your own.** Only do so when I explicitly ask for it in that message. Leave changes uncommitted in the working tree on whatever branch is checked out. To port changes from another branch, apply them to the working tree (e.g. `git diff A B | git apply`), never cherry-pick, merge, or commit.
