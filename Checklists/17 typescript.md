# TypeScript Mastery Checklist

> A backend-focused TypeScript roadmap covering fundamentals, advanced type systems, Node.js integration, type-safe APIs, production architecture, and advanced TypeScript internals.

---

# 1. TypeScript Fundamentals

- [ ] What is TypeScript?
- [ ] TypeScript vs JavaScript
- [ ] TypeScript compiler
- [ ] Type checking
- [ ] Static typing
- [ ] Type inference
- [ ] Compile-time vs runtime
- [ ] Type erasure
- [ ] `.ts` files
- [ ] `.tsx` files
- [ ] Transpilation
- [ ] TypeScript with Node.js

---

# 2. Basic Types

- [ ] `string`
- [ ] `number`
- [ ] `boolean`
- [ ] `bigint`
- [ ] `symbol`
- [ ] `null`
- [ ] `undefined`
- [ ] `object`
- [ ] `any`
- [ ] `unknown`
- [ ] `never`
- [ ] `void`

### Special Types

- [ ] `any` vs `unknown`
- [ ] `never`
- [ ] `void`
- [ ] `null` vs `undefined`
- [ ] `object` vs `{}`

---

# 3. Type Inference

- [ ] Variable inference
- [ ] Function return inference
- [ ] Parameter inference
- [ ] Array inference
- [ ] Object inference
- [ ] Literal inference
- [ ] Contextual typing
- [ ] Best common type

---

# 4. Type Annotations

- [ ] Variable annotations
- [ ] Function parameter types
- [ ] Return types
- [ ] Object annotations
- [ ] Array annotations
- [ ] Tuple annotations
- [ ] Optional properties
- [ ] Optional parameters
- [ ] Readonly properties

---

# 5. Arrays & Tuples

## Arrays

- [ ] `string[]`
- [ ] `Array<string>`
- [ ] Mixed arrays
- [ ] Readonly arrays
- [ ] Nested arrays

## Tuples

- [ ] Basic tuples
- [ ] Optional tuple elements
- [ ] Rest tuple elements
- [ ] Readonly tuples
- [ ] Named tuple elements

---

# 6. Objects

- [ ] Object type
- [ ] Object properties
- [ ] Optional properties
- [ ] Readonly properties
- [ ] Nested objects
- [ ] Object index signatures
- [ ] Dynamic keys
- [ ] Excess property checking
- [ ] Structural typing

---

# 7. Functions

- [ ] Function parameter types
- [ ] Return types
- [ ] Optional parameters
- [ ] Default parameters
- [ ] Rest parameters
- [ ] Function types
- [ ] Function aliases
- [ ] Callback types
- [ ] Higher-order functions
- [ ] Optional callbacks
- [ ] `this` parameter
- [ ] Function overloads

---

# 8. Type Aliases

- [ ] Basic type aliases
- [ ] Object aliases
- [ ] Function aliases
- [ ] Union aliases
- [ ] Intersection aliases
- [ ] Generic aliases
- [ ] Recursive aliases
- [ ] Alias composition

---

# 9. Interfaces

- [ ] Basic interfaces
- [ ] Optional properties
- [ ] Readonly properties
- [ ] Function interfaces
- [ ] Interface extension
- [ ] Multiple inheritance
- [ ] Interface merging
- [ ] Index signatures
- [ ] Interfaces vs type aliases

---

# 10. Union Types

- [ ] Basic unions
- [ ] String literal unions
- [ ] Number literal unions
- [ ] Boolean unions
- [ ] Object unions
- [ ] Union narrowing
- [ ] Discriminated unions
- [ ] Exhaustive checking

---

# 11. Intersection Types

- [ ] Basic intersections
- [ ] Combining object types
- [ ] Intersection with interfaces
- [ ] Intersection conflicts
- [ ] Intersection vs union

---

# 12. Literal Types

- [ ] String literals
- [ ] Number literals
- [ ] Boolean literals
- [ ] Literal unions
- [ ] `as const`
- [ ] Const assertions

---

# 13. Enums

- [ ] Numeric enums
- [ ] String enums
- [ ] Constant enums
- [ ] Enum members
- [ ] Enum runtime behavior
- [ ] Enums vs unions
- [ ] When to avoid enums

---

# 14. Type Narrowing ⭐⭐⭐⭐⭐

- [ ] `typeof`
- [ ] `instanceof`
- [ ] `in`
- [ ] Equality narrowing
- [ ] Truthiness narrowing
- [ ] Control-flow analysis
- [ ] Discriminated unions
- [ ] Type predicates
- [ ] Assertion functions
- [ ] Exhaustiveness checking

---

# 15. Type Guards

- [ ] Built-in type guards
- [ ] Custom type guards
- [ ] Type predicates
- [ ] `value is Type`
- [ ] Assertion functions
- [ ] `asserts`
- [ ] Runtime validation vs compile-time types

---

# 16. Generics ⭐⭐⭐⭐⭐

- [ ] Generic functions
- [ ] Generic interfaces
- [ ] Generic type aliases
- [ ] Generic classes
- [ ] Multiple type parameters
- [ ] Generic constraints
- [ ] `extends`
- [ ] Default generic parameters
- [ ] Generic inference
- [ ] Generic utility functions
- [ ] Generic API responses
- [ ] Generic repositories

---

# 17. Generic Constraints

- [ ] `T extends`
- [ ] Object constraints
- [ ] Key constraints
- [ ] `keyof`
- [ ] Generic property access
- [ ] Multiple constraints
- [ ] Conditional generic behavior

---

# 18. `keyof`

- [ ] What `keyof` does
- [ ] Object keys
- [ ] Generic keys
- [ ] `keyof typeof`
- [ ] Dynamic property access
- [ ] Type-safe object utilities

---

# 19. `typeof` in TypeScript

- [ ] Runtime `typeof`
- [ ] Type-level `typeof`
- [ ] `typeof variable`
- [ ] `typeof function`
- [ ] `keyof typeof`
- [ ] Extracting types from constants

---

# 20. Indexed Access Types

- [ ] `T[K]`
- [ ] Array element types
- [ ] Nested property types
- [ ] Generic indexed access
- [ ] Combining with `keyof`

---

# 21. Conditional Types ⭐⭐⭐⭐⭐

- [ ] Basic conditional types
- [ ] `T extends U ? X : Y`
- [ ] Generic conditional types
- [ ] Nested conditional types
- [ ] Distributive conditional types
- [ ] Conditional inference
- [ ] `infer`

---

# 22. `infer`

- [ ] Infer function return types
- [ ] Infer function parameters
- [ ] Infer array elements
- [ ] Infer promise values
- [ ] Infer nested types
- [ ] Conditional inference

---

# 23. Mapped Types ⭐⭐⭐⭐⭐

- [ ] Basic mapped types
- [ ] Mapping over keys
- [ ] Optional modifiers
- [ ] Readonly modifiers
- [ ] Key remapping
- [ ] Conditional mapped types
- [ ] Generic mapped types

---

# 24. Template Literal Types

- [ ] Basic template literal types
- [ ] Combining string unions
- [ ] Pattern-based types
- [ ] Event names
- [ ] API route types
- [ ] Key transformations
- [ ] Recursive template literal types

---

# 25. Utility Types ⭐⭐⭐⭐⭐

- [ ] `Partial`
- [ ] `Required`
- [ ] `Readonly`
- [ ] `Record`
- [ ] `Pick`
- [ ] `Omit`
- [ ] `Exclude`
- [ ] `Extract`
- [ ] `NonNullable`
- [ ] `Parameters`
- [ ] `ConstructorParameters`
- [ ] `ReturnType`
- [ ] `InstanceType`
- [ ] `ThisParameterType`
- [ ] `OmitThisParameter`
- [ ] `Awaited`
- [ ] `NoInfer`
- [ ] Build custom utility types

---

# 26. Advanced Object Types

- [ ] Index signatures
- [ ] Mapped types
- [ ] Conditional properties
- [ ] Optional properties
- [ ] Readonly properties
- [ ] Exact object concepts
- [ ] Recursive object types
- [ ] Deep partial
- [ ] Deep readonly
- [ ] Deep required

---

# 27. Classes & OOP

- [ ] Classes
- [ ] Constructors
- [ ] Properties
- [ ] Methods
- [ ] `public`
- [ ] `private`
- [ ] `protected`
- [ ] `readonly`
- [ ] Parameter properties
- [ ] Static members
- [ ] Abstract classes
- [ ] Abstract methods
- [ ] Inheritance
- [ ] Method overriding
- [ ] Getters
- [ ] Setters
- [ ] `implements`
- [ ] Interfaces with classes
- [ ] Polymorphism

---

# 28. Interfaces vs Types

Understand when to use:

- [ ] Interface
- [ ] Type alias
- [ ] Union
- [ ] Intersection
- [ ] Class
- [ ] Generic
- [ ] Discriminated union

Be able to explain:

> Why did I choose an interface here instead of a type?

---

# 29. Type Assertions

- [ ] `as`
- [ ] Angle-bracket syntax
- [ ] `as const`
- [ ] Double assertions
- [ ] When assertions are dangerous
- [ ] Avoiding unnecessary assertions
- [ ] Assertion vs narrowing
- [ ] Assertion vs runtime validation

---

# 30. `unknown`, `any`, and `never` ⭐⭐⭐⭐⭐

- [ ] `any`
- [ ] `unknown`
- [ ] `never`
- [ ] `void`
- [ ] Why `unknown` is safer than `any`
- [ ] When `any` is acceptable
- [ ] Exhaustive `never` checks
- [ ] Functions that never return

---

# 31. Null Safety

- [ ] `strictNullChecks`
- [ ] `null`
- [ ] `undefined`
- [ ] Optional properties
- [ ] Optional chaining
- [ ] Nullish coalescing
- [ ] Non-null assertion
- [ ] Null narrowing
- [ ] Safe API responses

---

# 32. Modules

- [ ] ES modules
- [ ] CommonJS
- [ ] `import`
- [ ] `export`
- [ ] Default exports
- [ ] Named exports
- [ ] Namespace imports
- [ ] Re-exports
- [ ] `import type`
- [ ] `export type`
- [ ] Dynamic imports
- [ ] Module resolution

---

# 33. Type-Only Imports

- [ ] `import type`
- [ ] `export type`
- [ ] Type-only dependencies
- [ ] Runtime vs type imports
- [ ] Avoiding unnecessary runtime imports

---

# 34. `tsconfig.json` ⭐⭐⭐⭐⭐

## Basic

- [ ] `target`
- [ ] `module`
- [ ] `moduleResolution`
- [ ] `lib`
- [ ] `rootDir`
- [ ] `outDir`
- [ ] `include`
- [ ] `exclude`

## Strictness

- [ ] `strict`
- [ ] `noImplicitAny`
- [ ] `strictNullChecks`
- [ ] `strictFunctionTypes`
- [ ] `strictBindCallApply`
- [ ] `strictPropertyInitialization`
- [ ] `noImplicitThis`
- [ ] `alwaysStrict`

## Quality

- [ ] `noUnusedLocals`
- [ ] `noUnusedParameters`
- [ ] `noImplicitReturns`
- [ ] `noFallthroughCasesInSwitch`
- [ ] `noUncheckedIndexedAccess`
- [ ] `exactOptionalPropertyTypes`

---

# 35. TypeScript Compiler

- [ ] `tsc`
- [ ] Compile TypeScript
- [ ] Watch mode
- [ ] `tsc --noEmit`
- [ ] Declaration generation
- [ ] Source maps
- [ ] Incremental compilation
- [ ] Project references
- [ ] Build mode
- [ ] Compiler diagnostics

---

# 36. Type Declarations

- [ ] `.d.ts` files
- [ ] Ambient declarations
- [ ] `declare`
- [ ] Declaring modules
- [ ] Declaring globals
- [ ] Type declaration packages
- [ ] `@types`
- [ ] Writing declarations for JavaScript libraries

---

# 37. JavaScript + TypeScript Interoperability

- [ ] Using JS in TS
- [ ] `allowJs`
- [ ] `checkJs`
- [ ] `// @ts-check`
- [ ] JSDoc types
- [ ] Migrating JS → TS
- [ ] Gradual migration
- [ ] Mixed repositories

---

# 38. Runtime vs Compile-Time ⭐⭐⭐⭐⭐

- [ ] TypeScript types disappear at runtime
- [ ] Runtime values
- [ ] Compile-time types
- [ ] Runtime validation
- [ ] Type assertions do not validate data
- [ ] External API data is untrusted
- [ ] Database data is runtime data
- [ ] User input is runtime data
- [ ] Type-safe boundaries

---

# 39. Runtime Validation

- [ ] Schema validation
- [ ] Runtime type checking
- [ ] DTO validation
- [ ] Request validation
- [ ] Environment variable validation
- [ ] Database result validation
- [ ] External API validation
- [ ] Zod
- [ ] Valibot
- [ ] JSON Schema concepts

---

# 40. Type-Safe Backend Development ⭐⭐⭐⭐⭐

- [ ] Type-safe request bodies
- [ ] Type-safe query parameters
- [ ] Type-safe route parameters
- [ ] Type-safe responses
- [ ] DTOs
- [ ] Service types
- [ ] Repository types
- [ ] Database types
- [ ] API response types
- [ ] Error types
- [ ] Configuration types
- [ ] Environment variable types

---

# 41. TypeScript with Node.js

- [ ] Node.js + TypeScript setup
- [ ] `package.json`
- [ ] `tsconfig.json`
- [ ] Build process
- [ ] Development workflow
- [ ] Watch mode
- [ ] Production compilation
- [ ] Source maps
- [ ] ESM + TypeScript
- [ ] CommonJS + TypeScript
- [ ] Node type definitions
- [ ] `@types/node`
- [ ] Environment configuration

---

# 42. TypeScript with Express / Fastify / NestJS

- [ ] Typed request
- [ ] Typed response
- [ ] Typed middleware
- [ ] Typed controllers
- [ ] Typed services
- [ ] Typed errors
- [ ] Typed route handlers
- [ ] DTOs
- [ ] Validation
- [ ] Generic API responses
- [ ] Type-safe middleware composition

---

# 43. Database Type Safety

- [ ] Type-safe database models
- [ ] Type-safe queries
- [ ] Database-generated types
- [ ] DTO vs database model
- [ ] Repository pattern
- [ ] Type-safe transactions
- [ ] Type-safe migrations
- [ ] ORM types
- [ ] Prisma concepts
- [ ] Drizzle concepts
- [ ] SQL type mapping

---

# 44. Generic Backend Patterns

Build generic abstractions for:

- [ ] Repository
- [ ] Service
- [ ] Pagination
- [ ] API response
- [ ] Result type
- [ ] Error type
- [ ] Cache
- [ ] Queue
- [ ] Event
- [ ] Logger
- [ ] Configuration
- [ ] Database transaction

---

# 45. Result & Error Types

Example:

```ts
type Result<T, E> =
  | { success: true; data: T }
  | { success: false; error: E };
```

- [ ] Result type
- [ ] Success type
- [ ] Error type
- [ ] Discriminated unions
- [ ] Error narrowing
- [ ] Functional error handling
- [ ] Avoiding unnecessary exceptions

---

# 46. Advanced Generics

- [ ] Generic constraints
- [ ] Multiple generics
- [ ] Default generics
- [ ] Generic inference
- [ ] Conditional generics
- [ ] Mapped generics
- [ ] Recursive generics
- [ ] Higher-order generic functions
- [ ] Generic factories
- [ ] Generic repositories
- [ ] Generic API clients

---

# 47. Advanced Type Manipulation

- [ ] `keyof`
- [ ] `typeof`
- [ ] Indexed access
- [ ] Conditional types
- [ ] `infer`
- [ ] Mapped types
- [ ] Template literal types
- [ ] Recursive types
- [ ] Distributive conditional types
- [ ] Key remapping
- [ ] Type transformations

---

# 48. Declaration Merging & Module Augmentation

- [ ] Declaration merging
- [ ] Interface merging
- [ ] Module augmentation
- [ ] Global augmentation
- [ ] Extending third-party types
- [ ] Express request augmentation
- [ ] Custom global types

---

# 49. TypeScript Project Architecture

- [ ] Source structure
- [ ] Domain types
- [ ] DTOs
- [ ] Infrastructure types
- [ ] Shared types
- [ ] Utility types
- [ ] Type boundaries
- [ ] Avoiding circular dependencies
- [ ] Module boundaries
- [ ] Barrel files
- [ ] Monorepo type sharing

---

# 50. TypeScript Monorepos

- [ ] Monorepo concepts
- [ ] Shared packages
- [ ] Shared types
- [ ] Project references
- [ ] Package boundaries
- [ ] Workspace configuration
- [ ] TypeScript build orchestration
- [ ] Turborepo concepts
- [ ] Nx concepts

---

# 51. Testing TypeScript

- [ ] Unit testing
- [ ] Integration testing
- [ ] Type-level testing
- [ ] Runtime testing
- [ ] Mocking
- [ ] Typed mocks
- [ ] Testing generic functions
- [ ] Testing type guards
- [ ] Testing validation schemas
- [ ] Testing API types

---

# 52. Type-Level Testing

- [ ] Compile-time tests
- [ ] Expected errors
- [ ] Type equality
- [ ] Type assertions
- [ ] `@ts-expect-error`
- [ ] Type testing libraries
- [ ] Testing generic utilities

---

# 53. TypeScript Performance

- [ ] Type-checking performance
- [ ] Large project performance
- [ ] Incremental builds
- [ ] Project references
- [ ] Avoiding unnecessarily complex types
- [ ] Recursive type performance
- [ ] Build caching
- [ ] `skipLibCheck`
- [ ] TypeScript diagnostics

---

# 54. TypeScript Tooling

- [ ] TypeScript CLI
- [ ] VS Code TypeScript support
- [ ] IntelliSense
- [ ] ESLint
- [ ] TypeScript ESLint
- [ ] Prettier
- [ ] Husky
- [ ] lint-staged
- [ ] ts-node concepts
- [ ] tsx
- [ ] Build tools
- [ ] Source maps

---

# 55. Code Quality

- [ ] Strict TypeScript
- [ ] Avoid unnecessary `any`
- [ ] Prefer `unknown` for unknown data
- [ ] Avoid excessive type assertions
- [ ] Prefer inference where appropriate
- [ ] Small types
- [ ] Clear interfaces
- [ ] Meaningful names
- [ ] Reusable utility types
- [ ] Avoid over-engineering types
- [ ] Maintainable generics

---

# 56. Common TypeScript Mistakes

- [ ] Excessive `any`
- [ ] Overusing `as`
- [ ] Using non-null assertions everywhere
- [ ] Ignoring `strict`
- [ ] Confusing types with runtime validation
- [ ] Huge generic types
- [ ] Over-engineered utility types
- [ ] Duplicate types
- [ ] Incorrect API assumptions
- [ ] Trusting database types blindly
- [ ] Trusting external API types blindly
- [ ] Confusing interface and class
- [ ] Misusing enums

---

# 57. Advanced TypeScript Concepts

- [ ] Structural typing
- [ ] Nominal typing patterns
- [ ] Variance
- [ ] Covariance
- [ ] Contravariance
- [ ] Bivariance
- [ ] Type compatibility
- [ ] Function compatibility
- [ ] Generic variance
- [ ] Excess property checks
- [ ] Weak types
- [ ] Freshness concepts

---

# 58. TypeScript Internals

- [ ] Compiler architecture
- [ ] Parser
- [ ] AST
- [ ] Type checker
- [ ] Symbol table
- [ ] Type inference
- [ ] Type resolution
- [ ] Declaration files
- [ ] Emit phase
- [ ] Source maps
- [ ] Compiler API basics
- [ ] TypeScript Language Service concepts

---

# 59. TypeScript + API Architecture

- [ ] Shared API contracts
- [ ] Request schemas
- [ ] Response schemas
- [ ] DTOs
- [ ] API version types
- [ ] Error contracts
- [ ] Pagination types
- [ ] Generic API response
- [ ] Runtime validation
- [ ] OpenAPI-generated types
- [ ] Client generation

---

# 60. TypeScript + Event-Driven Systems

- [ ] Event types
- [ ] Event payload types
- [ ] Event envelopes
- [ ] Event versioning
- [ ] Schema evolution
- [ ] Backward compatibility
- [ ] Consumer compatibility
- [ ] Type-safe event handlers
- [ ] Generic event buses

---

# 61. TypeScript + Distributed Systems

- [ ] Typed service contracts
- [ ] Typed messages
- [ ] Typed events
- [ ] Typed RPC
- [ ] Typed configuration
- [ ] Typed error contracts
- [ ] Versioned schemas
- [ ] Runtime validation
- [ ] Backward compatibility

---

# 62. TypeScript Project Practices

- [ ] Use strict mode
- [ ] Keep types close to their domain
- [ ] Separate DTOs from database models
- [ ] Validate external input at boundaries
- [ ] Avoid leaking infrastructure types
- [ ] Keep generic abstractions simple
- [ ] Prefer composition
- [ ] Keep public APIs stable
- [ ] Document complex types
- [ ] Review type complexity

---

# 63. TypeScript Backend Project Practice

## Beginner

- [ ] CLI application
- [ ] Typed Todo API
- [ ] Typed REST API
- [ ] Typed authentication API

## Intermediate

- [ ] Type-safe e-commerce API
- [ ] Type-safe database layer
- [ ] Generic repository
- [ ] Generic pagination
- [ ] Typed error system
- [ ] Runtime validation

## Advanced

- [ ] Type-safe API client
- [ ] Type-safe event bus
- [ ] Type-safe job queue
- [ ] Type-safe authorization system
- [ ] Type-safe multi-tenant backend
- [ ] Shared API contract between frontend/backend

## Production Project

- [ ] TypeScript strict mode
- [ ] Node.js
- [ ] Express / Fastify / NestJS
- [ ] PostgreSQL
- [ ] Redis
- [ ] Authentication
- [ ] Authorization
- [ ] RBAC
- [ ] Runtime validation
- [ ] Typed API contracts
- [ ] Typed database layer
- [ ] Background jobs
- [ ] Message queue
- [ ] Unit tests
- [ ] Integration tests
- [ ] Docker
- [ ] CI/CD
- [ ] Observability
- [ ] AWS deployment

---

# 64. Final TypeScript Mastery Checklist

- [ ] I understand TypeScript's purpose
- [ ] I understand compile-time vs runtime
- [ ] I understand type inference
- [ ] I understand primitive types
- [ ] I understand objects
- [ ] I understand functions
- [ ] I understand interfaces
- [ ] I understand type aliases
- [ ] I understand unions
- [ ] I understand intersections
- [ ] I understand literal types
- [ ] I understand narrowing
- [ ] I can write custom type guards
- [ ] I understand generics
- [ ] I understand `keyof`
- [ ] I understand `typeof`
- [ ] I understand indexed access types
- [ ] I understand conditional types
- [ ] I understand `infer`
- [ ] I understand mapped types
- [ ] I understand template literal types
- [ ] I know TypeScript utility types
- [ ] I understand classes
- [ ] I understand modules
- [ ] I understand `tsconfig`
- [ ] I can configure strict TypeScript
- [ ] I understand declaration files
- [ ] I understand module augmentation
- [ ] I understand runtime validation
- [ ] I can build type-safe Node.js applications
- [ ] I can type Express/Fastify/NestJS applications
- [ ] I can type database interactions
- [ ] I can design reusable generic abstractions
- [ ] I can design type-safe API contracts
- [ ] I can design type-safe event systems
- [ ] I understand advanced type manipulation
- [ ] I can test TypeScript code
- [ ] I can test types themselves
- [ ] I can maintain a large TypeScript project
- [ ] I can debug TypeScript compiler errors
- [ ] I understand TypeScript performance
- [ ] I can migrate JavaScript to TypeScript
- [ ] I can use TypeScript effectively in production backend systems

---

# Recommended Learning Order

## Phase 1 — Basics

1. [ ] TypeScript fundamentals
2. [ ] Basic types
3. [ ] Type inference
4. [ ] Type annotations
5. [ ] Arrays
6. [ ] Tuples
7. [ ] Objects
8. [ ] Functions
9. [ ] Type aliases
10. [ ] Interfaces

## Phase 2 — Core Type System

11. [ ] Union types
12. [ ] Intersection types
13. [ ] Literal types
14. [ ] Enums
15. [ ] Narrowing
16. [ ] Type guards
17. [ ] `unknown`
18. [ ] `never`
19. [ ] Null safety

## Phase 3 — Generics & Type Manipulation

20. [ ] Generics
21. [ ] Generic constraints
22. [ ] `keyof`
23. [ ] `typeof`
24. [ ] Indexed access types
25. [ ] Conditional types
26. [ ] `infer`
27. [ ] Mapped types
28. [ ] Template literal types
29. [ ] Utility types

## Phase 4 — TypeScript Engineering

30. [ ] Classes
31. [ ] Modules
32. [ ] Type-only imports
33. [ ] `tsconfig`
34. [ ] Compiler
35. [ ] Declaration files
36. [ ] JavaScript interoperability
37. [ ] Runtime validation
38. [ ] TypeScript tooling

## Phase 5 — Backend TypeScript

39. [ ] Node.js + TypeScript
40. [ ] Express/Fastify/NestJS + TypeScript
41. [ ] Type-safe APIs
42. [ ] DTOs
43. [ ] Database type safety
44. [ ] Generic repositories
45. [ ] Result/error types
46. [ ] Type-safe authentication
47. [ ] Type-safe authorization
48. [ ] Type-safe events

## Phase 6 — Advanced TypeScript

49. [ ] Advanced generics
50. [ ] Advanced mapped types
51. [ ] Conditional types
52. [ ] Recursive types
53. [ ] Type-level programming
54. [ ] Variance
55. [ ] Declaration merging
56. [ ] Module augmentation
57. [ ] Compiler internals

## Phase 7 — Production Mastery

58. [ ] Large project architecture
59. [ ] Monorepos
60. [ ] Type-safe API contracts
61. [ ] Type-level testing
62. [ ] TypeScript performance
63. [ ] Code quality
64. [ ] Migration strategies
65. [ ] Production backend project

---

# The Most Important TypeScript Mental Model

Don't learn TypeScript as:

```text
JavaScript
+
Types
```

Think of it as:

```text
                 TypeScript
                     │
        ┌────────────┴────────────┐
        │                         │
   Type System               JavaScript Runtime
        │                         │
   ┌────┼────┐              ┌─────┼─────┐
   │    │    │              │     │     │
Types Generics Narrowing   Node.js Browser Runtime
   │    │    │
   └────┼────┘
        │
   Compile Time
        │
        ▼
   JavaScript
        │
        ▼
   Runtime Validation
        │
        ▼
   Production Application
```

## Critical Backend Lesson

TypeScript can describe what your code expects, but it cannot automatically guarantee what your application actually receives at runtime.

Backend applications receive data from:

- Users
- HTTP requests
- Databases
- Queues
- Files
- Environment variables
- External APIs

Therefore the ideal pattern is:

```text
External Data
     ↓
Runtime Validation
     ↓
Trusted Data
     ↓
TypeScript Types
     ↓
Business Logic
     ↓
Database / Services
```

This distinction between **compile-time safety** and **runtime validation** is one of the most important concepts for a backend engineer using TypeScript.
