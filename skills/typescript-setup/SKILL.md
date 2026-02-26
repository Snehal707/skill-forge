---
name: typescript-setup
description: Set up a TypeScript development environment with proper tooling and configuration
version: 1.0.0
metadata:
  skill_forge:
    domain: "typescript"
    generated_at: "2026-02-26T10:00:00Z"
    validation_passed: true
    sources_used: 5
  hermes:
    tags: [typescript, javascript, web-development, tooling, setup]
    category: development
---

# TypeScript Setup

## When to Use
When you need to add static type checking to a JavaScript project or start a new TypeScript project with proper tooling and configuration.

## Prerequisites
- Node.js and npm installed
- Basic JavaScript knowledge
- Code editor (VS Code recommended for best TypeScript support)

## Procedure
1. Install TypeScript globally: `npm install -g typescript`
2. Verify installation: `tsc --version`
3. Create project directory: `mkdir my-typescript-project && cd my-typescript-project`
4. Initialize npm project: `npm init -y`
5. Install TypeScript locally: `npm install --save-dev typescript @types/node`
6. Create tsconfig.json: `npx tsc --init`
7. Configure tsconfig.json with basic settings:
   {
     "compilerOptions": {
       "target": "ES2020",
       "module": "commonjs",
       "outDir": "./dist",
       "rootDir": "./src",
       "strict": true,
       "esModuleInterop": true,
       "skipLibCheck": true,
       "forceConsistentCasingInFileNames": true
     },
     "include": ["src/**/*"],
     "exclude": ["node_modules", "dist"]
   }
   ```
8. Create src directory: `mkdir src`
9. Create first TypeScript file: `echo 'console.log("Hello TypeScript!");' > src/index.ts`
10. Compile TypeScript: `npx tsc`
11. Run compiled JavaScript: `node dist/index.js`

## Verification
Check that:
- `tsc --version` shows TypeScript version
- `dist/index.js` exists after compilation
- Running `node dist/index.js` outputs "Hello TypeScript!"
- Editor shows TypeScript intellisense and error checking

## Pitfalls
- Missing @types packages for libraries will cause type errors
- Incorrect file extensions (.js instead of .ts) won't get type checking
- Forgetting to compile before running will use old JavaScript output
- Module resolution issues when mixing CommonJS and ES modules

## Sources
- https://www.typescriptlang.org/
- https://www.npmjs.com/package/typescript
- https://github.com/microsoft/TypeScript
- https://www.w3schools.com/typescript/typescript_intro.php
- https://en.wikipedia.org/wiki/TypeScript
```