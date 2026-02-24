# Foundation Monorepo

This repository serves as the baseline architectural foundation mimicking a serverless Node.js backend.

## Technology Stack

- **Monorepo System**: Nx 19.1.0
- **Language**: TypeScript 5.4.5 & Node.js ≥20.14.0
- **Infrastructure**: AWS CDK 2.1029.2

## Architecture Organization

The monorepo organizes packages by operational boundaries rather than functional app/lib splits:

- `/packages/shared`: Cross-cutting code, schemas, types, and AWS interfaces. Contains zero local dependencies and acts as the universal language of the repository.
- `/packages/lambdas/libs`: Shared utilities and helpers strictly optimized for Lambda compute execution.
- `/packages/lambdas/fns`: Serverless compute function bundles. Separated strictly into CDK infrastructure configuration bridges (`index.ts`) and handler logic (`main.ts`).
- `/packages/infra`: AWS Cloud Development Kit (CDK) resource code describing the physical cloud environment and API Gateways.

## Getting Started

1. Install Node.js >= 20.14.0
2. Run `npm install` to resolve dependency trees.
3. Validate architecture constraints via Nx: `npx nx graph`
