---
name: setup-typescript-project
description: Initialize a new TypeScript project with proper configuration and type checking
version: 1.0.0
metadata:
  skill_forge:
    domain: "typescript"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [typescript, javascript, types, setup, configuration]
    category: development
---

# Setup TypeScript Project

## When to Use
When starting a new JavaScript project that needs type safety, better tooling, or when converting an existing JavaScript project to TypeScript.

## Prerequisites
- Node.js installed (version 12 or higher)
- npm or yarn package manager
- Code editor with TypeScript support (VS Code recommended)

## Procedure
1. Initialize new project: `npm init -y`
2. Install TypeScript: `npm install -D typescript @types/node`
3. Create TypeScript config: `npx tsc --init`
4. Create source directory: `mkdir src`
5. Create example TypeScript file: `echo 'const greeting: string = "Hello TypeScript!"; console.log(greeting);' > src/index.ts`
6. Add build script to package.json: `npm pkg set scripts.build="tsc"`
7. Add dev script: `npm pkg set scripts.dev="tsc --watch"`
8. Compile TypeScript: `npm run build`
9. Run compiled JavaScript: `node dist/index.js`

## Verification
- Check that `tsconfig.json` exists with proper configuration
- Verify `dist/` directory contains compiled `.js` files
- Confirm type checking works by adding invalid type and running `npx tsc --noEmit`
- Test that VS Code shows type information on hover

## Pitfalls
- Missing @types packages for third-party libraries will cause type errors
- Incorrect module resolution in tsconfig.json can break imports
- Using `any` type defeats the purpose of TypeScript's type safety
- Not enabling strict mode misses many type-checking benefits

## Sources
- https://www.typescriptlang.org/
- https://www.typescriptlang.org/docs/handbook/tsconfig-json.html
- https://www.npmjs.com/package/typescript
- https://github.com/microsoft/TypeScript
- https://www.w3schools.com/typescript/typescript_intro.php