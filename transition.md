## What not to do when transitioning to TypeScript
1.) Do not implement functional changes at the same time
2.) Do not attempt with low test coverage
3.) Don't let `perfect` be the enemy of the good (don't over type things, don't over tighten)
4.) Don't forget to test your types
5.) Don't publish types for a consumer while they're in a "weak" state

## Compiling in "Loose Mode"
- Start with tests passing
- Rename all .js to .ts, allowing implicit any
- Fix only things that are not type-checking, or causing compile errors
- Be careful to avoid changing behavior
- Get tests passing again

## Explicit Any
- Start with tests passing
- Ban implicit any ==> `"noImplicitAny": true`
- Where possible, provide a specific and appropriate type
    - Import tpyes for dependencies from DefinitelyTyped
    - otherwise explicit any\
- Get tests passing again

## Squash explicit anys, enable strict mode
- Incrementally, in small chunks...
- Enable strict mode:
```ts
"strictNullChecks": true, // Prevents null from being value in any 'type'
"strict": true,
"strictFunctionTypes": true,
"strictBindCallApply": true
```
- Replace explicit anys w/ more appropriate types
- Try really hard to unsafe casts