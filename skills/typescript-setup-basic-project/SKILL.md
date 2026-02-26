---
name: typescript-setup-basic-project
description: Set up a basic TypeScript project with compilation and type checking
version: 1.0.0
metadata:
  skill_forge:
    domain: "typescript"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [typescript, javascript, development, types]
    category: development
---

# TypeScript Basic Project Setup

## When to Use
When you need to add static typing to a JavaScript project or start a new TypeScript project from scratch.

## Prerequisites
- Node.js installed (version 14 or higher)
- npm or yarn package manager

## Procedure
1. Create project directory: `mkdir my-typescript-project && cd my-typescript-project`
2. Initialize npm project: `npm init -y`
3. Install TypeScript globally: `npm install -g typescript`
4. Install TypeScript as dev dependency: `npm install --save-dev typescript`
5. Create TypeScript config: `npx tsc --init`
6. Create source directory: `mkdir src`
7. Create a sample TypeScript file: `echo 'function greet(name: string): string { return `Hello, ${name}!`; } console.log(greet("World"));' > src/index.ts`
8. Compile TypeScript: `npx tsc`
9. Run compiled JavaScript: `node dist/index.js`

## Verification
- Check that `tsconfig.json` was created
- Verify TypeScript compiles without errors: `npx tsc --noEmit`
- Confirm output directory contains compiled `.js` files

## Pitfalls
- Missing tsconfig.json will cause compilation issues
- Type errors will prevent compilation by default
- Ensure output directory matches tsconfig.json settings

## Sources
- https://www.typescriptlang.org/
- https://www.w3schools.com/typescript/typescript_intro.php
- https://www.npmjs.com/package/typescript