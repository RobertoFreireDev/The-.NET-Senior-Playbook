# The .NET Senior Playbook — Chapters & Interview Questions

## Study Plan

### Part 1 — C# Language Fundamentals

2. Types and Type System
3. Operators, Statements, Expressions
4. OOP: Classes, Inheritance, Polymorphism
5. Records, Anonymous Types, Tuples
6. Generics and Variance
7. Collections

### Part 2 — C# Functional & Query

8. Delegates, Events, Lambdas
9. LINQ
10. Pattern Matching
11. Nullable Reference Types

### Part 3 — C# Async, Threading, Locking & Memory

12. C# Error Handling
13. Async/Await and Tasks
14. Threading and Synchronization
15. Memory Management and GC

### Part 4 — C# Advanced & Low-Level

16. Reflection and Dynamic
17. Span, Memory, Pipelines
18. Serialization
19. C# Version Features
20. .NET Runtime, CLR, JIT, AOT
21. Performance and Benchmarking

### Part 5 — .NET Tooling

22. BCL and IO
23. NuGet
24. MSBuild and csproj
25. .NET CLI

### Part 6 — ASP.NET Core Foundations

26. Types of Web Projects in ASP.NET Core
27. Application Host
28. Controllers
29. Minimal APIs
30. Middlewares
31. Filters

### Part 7 — API Design & Architecture

32. REST Fundamentals
33. API Versioning
34. Validation
35. Mapping

### Part 8 — Configuration & Reliability

36. Configuration and Options Pattern
37. Error Handling
38. Logging
39. Health Checks
40. Dependency Injection (DI)

### Part 9 — Security & Identity

41. Authentication and Authorization
42. ASP.NET Core Identity
43. ASP.NET Core Security

### Part 10 — Data, Performance & Infrastructure

44. Entity Framework Core
45. Caching
46. Response Compression
47. Rate Limiting

### Part 11 — Advanced Topics

48. API Documentation
49. Real-Time Communication with SignalR
50. Task Scheduling
51. Event Messaging
52. APIs and SDK
53. OpenTelemetry
54. Static Files
55. Building and Deploying .NET Apps

---

## Interview Questions

### Bucket 1 — C# and .NET

#### Ch 1 — Types and Type System (5)

- **Q1.** What is the difference between a value type and a reference type in C#?
- **Q2.** What is the difference between `float`, `double`, and `decimal` — and when would you use each?
- **Q3.** What is the difference between `string` and `StringBuilder`, and when is each appropriate?
- **Q4.** What is boxing and unboxing? Show a small example and explain the cost.
- **Q5.** What is a `ref struct`? What restrictions apply and what problem does it solve?

#### Ch 2 — Operators, Statements, Expressions (2)

- **Q6.** What is the null-coalescing operator (`??`) and the null-conditional operator (`?.`)?
- **Q7.** What does a `foreach` loop compile to under the hood?

#### Ch 3 — OOP: Classes, Inheritance, Polymorphism (5)

- **Q8.** What is the difference between an abstract class and an interface?
- **Q9.** What is polymorphism, and how does C# support it via `virtual` / `override`?
- **Q10.** What is a primary constructor (C# 12) and how does it differ from a traditional constructor?
- **Q11.** What are init-only setters and what problem do they solve?
- **Q12.** How does the runtime dispatch a virtual call (vtable lookup) vs. an interface call?

#### Ch 4 — Records, Anonymous Types, Tuples (3)

- **Q13.** What is a record in C# and how does it differ from a class?
- **Q14.** How does equality work for records compared to classes?
- **Q15.** When would you prefer a record struct over a record class?

#### Ch 5 — Generics and Variance (3)

- **Q16.** What are generic constraints and what kinds are available?
- **Q17.** Explain covariance and contravariance with `in` and `out` — give an example with `IEnumerable<T>` and `Action<T>`.
- **Q18.** How does the JIT specialize generic code for value types vs. reference types? What is the performance impact?

#### Ch 6 — Collections (5)

- **Q19.** What is the difference between `IEnumerable<T>` and `ICollection<T>`?
- **Q20.** What are concurrent collections in .NET? Name a few and their use cases.
- **Q21.** What is a `FrozenSet<T>` / `FrozenDictionary<TKey, TValue>` and when does it outperform a regular dictionary?
- **Q22.** Explain how `Dictionary<TKey, TValue>` is implemented internally and what affects its lookup performance.
- **Q23.** How does `ConcurrentDictionary` handle concurrent updates internally? Explain its locking strategy.

#### Ch 7 — Delegates, Events, Lambdas (4)

- **Q24.** What is the difference between a delegate and an event?
- **Q25.** What is a closure and what are the captured-variable rules?
- **Q26.** What is an expression tree and how does it differ from a delegate?
- **Q27.** What is a multicast delegate and what happens if one handler throws?

#### Ch 8 — LINQ (5)

- **Q28.** What is the difference between `IEnumerable<T>` and `IQueryable<T>` in LINQ?
- **Q29.** What is deferred execution in LINQ? Give an example where it matters.
- **Q30.** What is `IAsyncEnumerable<T>` and how do you consume it with `await foreach`?
- **Q31.** How does the LINQ provider for EF Core translate expression trees to SQL?
- **Q32.** Why is `Count() == 0` worse than `Any()` on an `IEnumerable<T>` — and are there cases where it's fine?

#### Ch 9 — Pattern Matching (1)

- **Q33.** What is a list pattern (C# 11) and what does it enable?

#### Ch 10 — Nullable Reference Types (1)

- **Q34.** What is the runtime behavior of nullable reference types — is the annotation enforced at runtime?

#### Ch 11 — C# Error Handling (3)

- **Q35.** What is the difference between `throw ex` and `throw` inside a catch block?
- **Q36.** What is the cost of throwing exceptions in .NET, and why should you avoid using them for control flow?
- **Q37.** How does the CLR unwind the stack when an exception is thrown? What does the JIT do at try/catch boundaries?

#### Ch 12 — Async/Await and Tasks (6)

- **Q38.** What is the difference between `Task` and `ValueTask` — and when should you use each?
- **Q39.** What is the purpose of `ConfigureAwait(false)`, and when should you use it?
- **Q40.** Explain the state machine the compiler generates for an async method. What does it allocate?
- **Q41.** What is `SynchronizationContext` and how does it affect `await` resumption?
- **Q42.** What is the difference between `async void` and `async Task`, and why is `async void` dangerous?
- **Q43.** Why does a deadlock occur when you call `.Result` or `.Wait()` on a `Task` in a context with a `SynchronizationContext`?

#### Ch 13 — Threading and Synchronization (4)

- **Q44.** What is `lock` and what does it compile to?
- **Q45.** What is the new `Lock` object in C# 13 and how does it improve over locking on an arbitrary object?
- **Q46.** What is `Channel<T>` in .NET, and what scenarios does it solve compared to `BlockingCollection<T>`?
- **Q47.** What happens when ThreadPool threads are starved (sync-over-async / blocking IO)? How do you diagnose it?

#### Ch 14 — Memory Management and GC (5)

- **Q48.** Explain GC generations 0, 1, 2 and how objects are promoted.
- **Q49.** What is the Large Object Heap (LOH) and why does it matter for performance?
- **Q50.** What is the difference between workstation GC and server GC?
- **Q51.** What is the dispose pattern, and why does it include `Dispose(bool disposing)`?
- **Q52.** How do you diagnose a memory leak in a .NET application? What tools would you use?

#### Ch 15 — Reflection and Dynamic (2)

- **Q53.** What is the performance cost of reflection — how can you cache reflection results?
- **Q54.** How do source generators compare to reflection for solving the same problems?

#### Ch 16 — Span, Memory, Pipelines (3)

- **Q55.** What is `Span<T>` and what problem does it solve?
- **Q56.** Why can `Span<T>` not be used as a field on a regular class — what is the workaround?
- **Q57.** What is `ArrayPool<T>` and when should you use it?

#### Ch 17 — Serialization (2)

- **Q58.** What is the source-generator mode of `System.Text.Json`, and when should you use it?
- **Q59.** Why was `BinaryFormatter` deprecated, and what should you use instead?

#### Ch 18 — C# Version Features (2)

- **Q60.** What is the `field` keyword (C# 14) and what problem does it solve in property setters?
- **Q61.** What is `CallerArgumentExpression` and how is it useful for guard clauses?

#### Ch 19 — .NET Runtime, CLR, JIT, AOT (3)

- **Q62.** What is tiered compilation in .NET, and how does it improve startup vs. steady-state performance?
- **Q63.** What is Native AOT and what are the trade-offs of using it?
- **Q64.** What is PGO (profile-guided optimization) and dynamic PGO in .NET?

#### Ch 20 — Performance and Benchmarking (2)

- **Q65.** Why should you not use `Stopwatch` and a `for` loop as a substitute for BenchmarkDotNet?
- **Q66.** What does `MemoryDiagnoser` measure, and how do you interpret `Gen0` / `Gen1` / `Gen2` counts?

#### Ch 21 — BCL and IO (2)

- **Q67.** What is the difference between `Stream`, `MemoryStream`, and `FileStream`?
- **Q68.** What is `RandomAccess` (introduced in .NET 6), and what scenario does it improve?

#### Ch 22 — NuGet (1)

- **Q69.** What is Central Package Management and `Directory.Packages.props`?

#### Ch 23 — MSBuild and csproj (2)

- **Q70.** What is `Directory.Build.props` / `Directory.Build.targets`, and what is it for?
- **Q71.** What is multi-targeting, and when would you use it?

#### Ch 24 — .NET CLI (2)

- **Q72.** What is the difference between `dotnet build` and `dotnet publish`?
- **Q73.** What is `global.json`, and what problem does it solve in multi-version environments?

#### Wrap-up — Async / Threading bonus depth (2)

- **Q74.** What is `TaskCompletionSource<T>`, and what is a common use case for it?
- **Q75.** What is the difference between `Task.WhenAll` vs. `Task.WhenAny`?

---

### Bucket 2 — ASP.NET Core and EF Core

#### Ch 25 — Types of Web Projects in ASP.NET Core (2)

- **Q76.** What are the main ASP.NET Core web project types?
- **Q77.** When would you choose Minimal APIs over a controller-based API project?

#### Ch 26 — Application Host (3)

- **Q78.** What is `WebApplicationBuilder`, and how does it simplify host and app configuration?
- **Q79.** What is `IHostedService`, and what is a typical use case?
- **Q80.** What mechanisms does `IHost.StopAsync` use to signal graceful shutdown?

#### Ch 27 — Controllers (5)

- **Q81.** What is model binding, and how does it work in ASP.NET Core controllers?
- **Q82.** Explain the difference between `[FromBody]`, `[FromQuery]`, `[FromRoute]`, and `[FromForm]`.
- **Q83.** What is the purpose of `IActionResult`, and why use it over a concrete return type?
- **Q84.** Explain the lifecycle of a controller in ASP.NET Core — when is it created and disposed?
- **Q85.** How can you handle exceptions globally for all controllers?

#### Ch 28 — Minimal APIs (5)

- **Q86.** How does a Minimal API differ from a traditional controller-based API?
- **Q87.** How do you secure Minimal API endpoints using authentication and authorization?
- **Q88.** How do you implement versioning with Minimal APIs?
- **Q89.** What filters are supported by Minimal APIs?
- **Q90.** What are the trade-offs of using Minimal APIs in a large enterprise application?

#### Ch 29 — Middlewares (4)

- **Q91.** What is the order of middleware execution and why does it matter?
- **Q92.** Name all the ways to create middleware in ASP.NET Core.
- **Q93.** What is the difference between convention-based and factory-based middleware?
- **Q94.** How do you handle exceptions globally using middleware?

#### Ch 30 — Filters (4)

- **Q95.** Name the main types of filters available in ASP.NET Core.
- **Q96.** How can you control the order in which filters are executed?
- **Q97.** What is the difference between resource filters and action filters?
- **Q98.** What are filter scopes (global / controller / action), and how is precedence resolved?

#### Ch 31 — REST Fundamentals (8)

- **Q99.** What is the Richardson Maturity Model, and what are its levels?
- **Q100.** List and briefly explain the six architectural constraints of REST.
- **Q101.** What is the difference between PUT and PATCH?
- **Q102.** Explain idempotency. Which HTTP methods are idempotent?
- **Q103.** Explain the difference between 401 Unauthorized and 403 Forbidden.
- **Q104.** What is HATEOAS, and how does it relate to REST Level 3?
- **Q105.** What are common strategies for pagination in REST APIs?
- **Q106.** What is data shaping in REST APIs and why is it useful?

#### Ch 32 — API Versioning (3)

- **Q107.** Explain URL-based vs. query-string vs. header-based vs. content-negotiation versioning.
- **Q108.** How do you mark an API version as deprecated?
- **Q109.** How do you ensure backward compatibility when introducing a new API version?

#### Ch 33 — Validation (5)

- **Q110.** What is FluentValidation, and why might you use it over `DataAnnotations`?
- **Q111.** How does FluentValidation handle complex object graphs or child collections?
- **Q112.** How do you perform asynchronous validation in FluentValidation?
- **Q113.** How can you inject services (e.g., database access) into a FluentValidation validator?
- **Q114.** How do you return FluentValidation errors as Problem Details in APIs?

#### Ch 34 — Mapping (4)

- **Q115.** What is AutoMapper, and what are common pitfalls in large solutions?
- **Q116.** What is Mapperly, and how does it use source generators?
- **Q117.** What are the trade-offs of Mapperly versus runtime mappers like AutoMapper?
- **Q118.** When might manual mapping be preferable to a mapping library?

#### Ch 35 — Configuration and Options Pattern (4)

- **Q119.** What is the options pattern, and why is it preferred over direct configuration access?
- **Q120.** Describe the difference between `IOptions<T>`, `IOptionsSnapshot<T>`, and `IOptionsMonitor<T>`.
- **Q121.** How do you validate configuration bound to a class using `DataAnnotations`?
- **Q122.** How do you secure sensitive configuration values such as API keys or connection strings?

#### Ch 36 — Error Handling (4)

- **Q123.** What is the `UseExceptionHandler` middleware, and how do you configure it?
- **Q124.** What's new in .NET 8 for global error handling (`IExceptionHandler`)?
- **Q125.** How can you return Problem Details (RFC 9457) in ASP.NET Core APIs?
- **Q126.** How would you map custom exceptions to specific HTTP status codes globally?

#### Ch 37 — Logging (5)

- **Q127.** What is structured logging, and why should you use it?
- **Q128.** What are scopes in ASP.NET Core logging, and how do you use them?
- **Q129.** How do you enable logging for EF Core database commands?
- **Q130.** How do you implement log aggregation and monitoring for production environments?
- **Q131.** How would you control log size and log-file rotation in Serilog?

#### Ch 38 — Health Checks (2)

- **Q132.** What's the difference between a liveness probe and a readiness probe?
- **Q133.** How do you implement a custom health check?

#### Ch 39 — Dependency Injection (DI) (5)

- **Q134.** What are the three most common DI lifetimes in ASP.NET Core?
- **Q135.** What are the potential pitfalls when injecting scoped services into singleton services?
- **Q136.** How do you resolve a scoped service within a background task or singleton class?
- **Q137.** How do you handle circular dependencies in DI?
- **Q138.** How would you implement conditional dependency resolution (e.g., based on configuration)?

#### Ch 43 — Entity Framework Core (7)

- **Q139.** What is the difference between `DbContext` and `DbSet`?
- **Q140.** Explain the difference between eager loading, lazy loading, and explicit loading.
- **Q141.** When and why should you use `.AsNoTracking()` in your queries?
- **Q142.** What is query splitting (`AsSplitQuery`), and what performance problem does it solve?
- **Q143.** Explain context pooling and how it helps high-throughput applications.
- **Q144.** How do you implement and resolve optimistic concurrency using `RowVersion` or concurrency tokens?
- **Q145.** How do you handle batch operations (update/delete) in EF Core without loading entities?

---

### Bucket 3 — Caching, Scheduling, Messaging, and Security

#### Ch 40 — Authentication and Authorization (7)

- **Q146.** What is the difference between authentication and authorization?
- **Q147.** What's the difference between cookie authentication and JWT bearer authentication?
- **Q148.** What are refresh tokens? Explain the authentication flow with JWT + refresh tokens.
- **Q149.** How do you implement policy-based / claim-based authorization?
- **Q150.** What is a Requirement in the context of authorization policies?
- **Q151.** How do you create a custom authorization handler?
- **Q152.** Describe a scenario where claims transformation is necessary and how to implement it.

#### Ch 41 — ASP.NET Core Identity (5)

- **Q153.** How do you configure password requirements (length, complexity, etc.) in Identity?
- **Q154.** How can you implement two-factor authentication (2FA) using Identity?
- **Q155.** How do you lock out a user after multiple failed login attempts?
- **Q156.** How would you integrate Identity with API authentication using JWT tokens?
- **Q157.** How do you create and manage custom user stores for NoSQL databases?

#### Ch 42 — ASP.NET Core Security (7)

- **Q158.** What is CORS, and what are the risks of allowing wide access with it?
- **Q159.** How do preflight OPTIONS requests work with CORS?
- **Q160.** How do you validate a JWT's signature and claims?
- **Q161.** What are the security risks associated with refresh tokens?
- **Q162.** How do you invalidate refresh tokens (e.g., on logout or password change)?
- **Q163.** What is OAuth 2.0, and how is it used for securing APIs?
- **Q164.** What is OpenID Connect, and how does it differ from OAuth 2.0?

#### Ch 44 — Caching (7)

- **Q165.** What is `IDistributedCache`, and how does it differ from memory cache?
- **Q166.** How do you implement cache expiration and eviction policies for Redis?
- **Q167.** What is `OutputCache` in ASP.NET Core, and how do you configure it for endpoints?
- **Q168.** How can you vary `OutputCache` by request parameters or user identity?
- **Q169.** What is `HybridCache`, and how does it combine in-memory and distributed caching?
- **Q170.** How do you use `HybridCache` with an L1/L2 strategy in ASP.NET Core?
- **Q171.** What is FusionCache, and what problem from `HybridCache` does it solve?

#### Ch 49 — Task Scheduling (7)

- **Q172.** What is a background service in ASP.NET Core? When is it started and stopped?
- **Q173.** What's the difference between a background service and an `IHostedService`?
- **Q174.** What happens if an unhandled exception occurs in a background service?
- **Q175.** How do you schedule recurring tasks using Quartz.NET with cron expressions?
- **Q176.** How do you inject dependencies into Quartz jobs?
- **Q177.** What strategies can you use to avoid running the same scheduled job multiple times across instances?
- **Q178.** How would you architect a solution for distributed scheduling across multiple servers?

#### Ch 50 — Event Messaging (7)

- **Q179.** What is MediatR, and what pattern does it implement?
- **Q180.** How do you send and handle notifications using MediatR?
- **Q181.** What are potential drawbacks of overusing MediatR in a project?
- **Q182.** What is MassTransit, and what role does it play in event-driven architecture?
- **Q183.** How do you configure MassTransit with RabbitMQ or another message broker?
- **Q184.** How do you define and consume messages (events / commands) using MassTransit?
- **Q185.** What are advanced features of MassTransit such as sagas or message-retry policies?

---

### Bucket 4 — System Design and Architecture

#### Ch 51 — APIs, SDKs and Resilience (10)

- **Q186.** What happens if you create a new `HttpClient` for every API call?
- **Q187.** What is `HttpClientFactory`, and why was it introduced in ASP.NET Core?
- **Q188.** What is a typed client, and how is it different from a named client?
- **Q189.** What is Refit, and how do you define an API interface using it?
- **Q190.** What is a `DelegatingHandler`, and what are the common use cases?
- **Q191.** What is Polly, and how is it used with `HttpClientFactory`?
- **Q192.** Give an example of adding a retry policy using Polly to an `HttpClientFactory`.
- **Q193.** How do you implement the circuit-breaker strategy with Polly?
- **Q194.** How do you implement a fallback strategy with Polly?
- **Q195.** How do you handle authentication and token refresh for outgoing HTTP requests?

#### Ch 52 — OpenTelemetry & Observability (8)

- **Q196.** What are the three pillars of observability in OpenTelemetry?
- **Q197.** What is the OpenTelemetry Collector, and what role does it play?
- **Q198.** Explain what a span and a trace are in the context of distributed tracing.
- **Q199.** How do you handle distributed context propagation (baggage) between microservices?
- **Q200.** Explain sampling in OTel, and why you would use different sampling strategies.
- **Q201.** How do you create custom metrics (counters, histograms) in .NET?
- **Q202.** What are trace links in OpenTelemetry, and when are they useful?
- **Q203.** How do you configure OpenTelemetry to handle high-cardinality data in metrics?

#### Ch 54 — Build & Deploy / Distributed Systems (12)

- **Q204.** What is the difference between framework-dependent and self-contained deployment?
- **Q205.** How do you publish a .NET app for a specific runtime (e.g., `win-x64`, `linux-x64`)?
- **Q206.** How do you configure environment-specific `appsettings` files in the publish output?
- **Q207.** How do you write a Dockerfile for an ASP.NET Core app?
- **Q208.** What is a multi-stage Docker build, and why should you use it?
- **Q209.** How do you optimize Docker image size for .NET apps?
- **Q210.** How do you pass environment variables and configuration to a Docker container?
- **Q211.** How do you configure a Docker Compose file for an ASP.NET Core app with PostgreSQL and Redis?
- **Q212.** How do you use health checks in Docker Compose for .NET services?
- **Q213.** What is .NET Aspire, and how does it simplify local development?
- **Q214.** How do you deploy an Aspire application to Docker Compose?
- **Q215.** How do you configure OpenTelemetry observability with Aspire?
