# Module 31: React Fundamentals

Learn component composition, typed props, state, events, forms, lists, and context by building accessible TeamOps UI elements. Use [React Learn](https://react.dev/learn), [React TypeScript](https://react.dev/learn/typescript), and the Hands on React labs for components through validation.

## Learn

- JSX, function components, props, component boundaries, lists, stable keys, conditional rendering, and lifting state.
- `useState`, controlled form inputs, event handling, state structure, and derived values.
- Context for genuinely shared values, with a safe consumer hook when a provider is required.
- Typing props, state unions, DOM events, children, refs, and style objects.

## Practice Deliverable

Build the catalog TeamOps task list and task form. Use typed task data, a controlled form, client-side validation messages, stable list keys, and accessible labels/status feedback. Include empty and validation-error states before API integration.

## Verify

```bash
npm run typecheck
npm test
npm run lint
```

Manually check keyboard navigation, visible labels, error announcements, and narrow/wide layouts.

## Completion Criteria

- [ ] Props describe a component contract without using `React.FC` by default.
- [ ] State is minimal; values that can be derived are not duplicated in state.
- [ ] Form events and input values are typed correctly.
- [ ] List items have stable data keys, not array indexes where item identity changes.
- [ ] The form works by keyboard and exposes validation errors accessibly.

## Common Mistakes

Mutating state, copying props into state, using effects for calculations, context for all state, index keys in mutable lists, uncontrolled/controlled input switching, and using `as` to bypass a prop error.

## Next

Continue to [Module 32: React Application Development](../02-application-development/).
