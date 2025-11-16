# Comprehensive Software Developer Prompts Collection

A battle-tested collection of prompts for troubleshooting, development, and understanding codebases.

---

## Table of Contents
1. [Context Setting & Role Definition](#context-setting--role-definition)
2. [Debugging & Troubleshooting](#debugging--troubleshooting)
3. [Understanding Codebases](#understanding-codebases)
4. [Code Review & Refactoring](#code-review--refactoring)
5. [New Feature Development](#new-feature-development)
6. [Testing & Quality Assurance](#testing--quality-assurance)
7. [Architecture & System Design](#architecture--system-design)
8. [Performance Optimization](#performance-optimization)
9. [Security Review](#security-review)
10. [Documentation](#documentation)
11. [Advanced Strategies](#advanced-strategies)

---

## Context Setting & Role Definition

### Basic Context Template
```
Act as a senior [role] with [X] years of experience in [technologies].

**My Project Context:**
- Technology Stack: [list all technologies]
- Architecture: [microservices/monolith/serverless]
- Database: [PostgreSQL/MongoDB/etc.]
- Development Environment: [Docker/Kubernetes/etc.]
- Team Size: [number]
- Project Type: [web app/mobile/API/etc.]

**Current Objective:** [describe what you're trying to achieve]
```

### Comprehensive Role-Based Context
```
You are an experienced software architect and full-stack developer. 

**Project Details:**
- Application: [name and purpose]
- Tech Stack: [frontend], [backend], [database], [cloud provider]
- Architecture Pattern: [REST/GraphQL/event-driven/etc.]
- Scale: [users/requests per second]
- Deployment: [CI/CD tools, containerization]

**My Background:** [junior/mid-level/senior developer]

**What I Need:** Before providing solutions, ask me clarifying questions about:
- The exact behavior I'm seeing vs expected behavior
- What I've already tried
- Any error messages or logs
- Timeline constraints
```

### Multi-Perspective Analysis Setup
```
Analyze this from three perspectives:

1. **Software Architect** - Focus on system design, architecture patterns, scalability
2. **Software Developer** - Examine code structure, implementation, maintainability  
3. **DevOps Engineer** - Consider deployment, monitoring, infrastructure

For each perspective, provide:
- Key observations
- Potential issues
- Recommendations
```

---

## Debugging & Troubleshooting

### Production Issue Investigation
```
I'm troubleshooting a production issue. Help me systematically debug:

**Issue Description:** [detailed description]
**Error Message:** [exact error with stack trace]
**Frequency:** [always/intermittent/under specific conditions]
**Environment:** [production/staging/development]
**Recent Changes:** [deployments, config changes, traffic spikes]

**Investigation Steps:**
1. What's your initial hypothesis?
2. What should I check first in logs/metrics?
3. What are the top 3 most likely root causes?
4. How would you verify each hypothesis?
5. What immediate mitigation steps should I take?
6. What long-term fixes would prevent recurrence?

Include relevant commands, queries, or tools to use.
```

### Error Deep Dive
```
I'm getting this error and need comprehensive analysis:

**Error Message:** [complete error with traceback]
**Language/Framework:** [specify versions]
**Code Context:** [relevant code snippet]
**What I've Tried:** [list all attempts]

Please provide:
1. **Root Cause Analysis** - Why is this happening?
2. **Step-by-step Fix** - How to resolve it
3. **Prevention** - How to avoid this in the future
4. **Best Practices** - What should I know about this error type?
```

### Performance Debugging
```
Help me debug a performance issue:

**Problem:** [slow API/memory leak/high CPU/database bottleneck]
**Metrics:** 
- Response time: [current vs expected]
- Memory usage: [current usage]
- CPU usage: [percentage]
- Database query time: [duration]

**Environment:**
- Scale: [number of users/requests]
- Infrastructure: [server specs]

**Investigation Needed:**
1. Profile the performance bottleneck
2. Identify the root cause
3. Suggest optimizations with trade-offs
4. Provide monitoring strategies
```

### Intermittent Bug Analysis
```
I have an intermittent bug that's hard to reproduce:

**Symptom:** [what happens]
**Frequency:** [how often]
**Patterns:** [any observed patterns - time, load, specific users]
**Stack:** [technology details]
**Code:** [relevant sections]

**Help me:**
1. Design a strategy to reproduce it consistently
2. Identify race conditions or timing issues
3. Add appropriate logging/instrumentation
4. Create test cases to catch this
```

### Database Issue Troubleshooting
```
Investigate this database issue:

**Database:** [PostgreSQL/MySQL/MongoDB]
**Problem:** [slow queries/locks/connection pool exhaustion]
**Query:** [problematic query]
**Schema:** [relevant tables and relationships]
**Current Performance:** [query execution time, explain plan]

**Analyze:**
1. Identify performance bottlenecks
2. Suggest index optimizations
3. Recommend query rewrites
4. Propose schema improvements
5. Provide monitoring queries
```

---

## Understanding Codebases

### Complete Repository Analysis
```
Analyze this codebase from multiple perspectives:

[Paste repository structure or provide access]

**Analysis Framework:**

**1. Software Architect View:**
- System design and architecture patterns
- Service boundaries and dependencies
- Scalability considerations
- Technology choices and rationale

**2. Developer View:**
- Code organization and structure
- Coding patterns and conventions
- Technical debt areas
- Maintainability concerns

**3. Product View:**
- Features and functionality
- User flows and business logic
- Integration points
- Future extensibility

**Deliverable:**
Create a comprehensive README.md with:
- Mermaid diagrams for architecture and workflows
- Clear structure and navigation
- Actionable insights for development
- Areas requiring immediate attention
```

### Legacy Code Understanding
```
Help me understand this legacy codebase:

**Context:**
- Age: [years old]
- Language/Framework: [with versions]
- Documentation: [none/minimal/outdated]
- Original team: [available/gone]

**Files:** [paste key files or structure]

**I need:**
1. **High-level Overview** - What does this system do?
2. **Architecture Map** - How are components connected?
3. **Key Dependencies** - What relies on what?
4. **Critical Paths** - Main user flows and business logic
5. **Technical Debt** - What needs modernization?
6. **Entry Points** - Where should I start exploring?
7. **Risk Areas** - What's fragile or complex?

Explain it as if teaching to someone unfamiliar with this domain.
```

### Function/Module Deep Dive
```
Explain this code comprehensively:

[Paste code]

**Break down:**
1. **Purpose** - What problem does this solve?
2. **Logic Flow** - Step-by-step execution
3. **Algorithm** - What approach is used and why?
4. **Dependencies** - What it relies on
5. **Side Effects** - What it modifies
6. **Edge Cases** - How it handles unusual inputs
7. **Performance** - Time/space complexity
8. **Best Practices** - What it does well
9. **Improvements** - What could be better
10. **Testing Strategy** - How to test this

Use examples to illustrate complex parts.
```

### API Understanding
```
Help me understand this API:

**Endpoint:** [URL or code]
**Documentation:** [link or paste]
**Related Code:** [controller, service, model code]

**Explain:**
1. What does this endpoint do?
2. Request format with examples
3. Response structure with examples
4. Authentication/authorization
5. Error handling scenarios
6. Performance considerations
7. Common use cases
8. Integration examples in [language]
```

### Data Flow Tracing
```
Trace the complete data flow for [feature/operation]:

**Starting Point:** [user action/API call/event]
**Ending Point:** [result/side effect]

**Map out:**
1. Entry point and initial processing
2. Each layer/service it passes through
3. Data transformations at each step
4. Database operations
5. External API calls
6. Background jobs triggered
7. Final response/side effects

Include:
- File names and function names
- Data structure at each stage
- Error handling at each point
- Performance bottlenecks
```

---

## Code Review & Refactoring

### Comprehensive Code Review
```
Perform a thorough code review:

[Paste code]

**Review Criteria:**

**1. Functionality**
- Does it work correctly?
- Are there logical errors?
- Are edge cases handled?

**2. Readability**
- Is the code self-explanatory?
- Are names descriptive?
- Is the structure logical?

**3. Performance**
- Are there inefficiencies?
- Time/space complexity analysis
- Potential optimizations

**4. Security**
- Input validation
- SQL injection risks
- XSS vulnerabilities
- Authentication/authorization issues

**5. Best Practices**
- Design patterns applied
- SOLID principles
- Framework conventions
- Error handling

**6. Maintainability**
- Code duplication
- Function length and complexity
- Testability
- Documentation needs

Provide specific line-by-line feedback with examples.
```

### Clean Code Refactoring
```
Refactor this code following clean code principles:

[Paste code]

**Objectives:**
1. Use descriptive, meaningful names
2. Break large functions into smaller, single-purpose ones
3. Maintain logical order for readability
4. Ensure each function has single responsibility
5. Remove unnecessary comments (make code self-documenting)
6. Limit variable scope appropriately
7. Remove code duplication
8. Apply appropriate design patterns

**Provide:**
- Refactored code with explanations
- Before/after comparison
- Rationale for each change
- Performance impact (if any)
```

### SOLID Principles Application
```
Analyze and refactor this code to apply SOLID principles:

[Paste code]

**For Each Principle:**

**Single Responsibility:**
- Identify violations
- Show how to separate concerns

**Open/Closed:**
- Show extensibility improvements
- Add abstraction where needed

**Liskov Substitution:**
- Ensure proper inheritance/interface usage

**Interface Segregation:**
- Split large interfaces appropriately

**Dependency Inversion:**
- Introduce abstractions for dependencies

**Requirements:**
- Make only necessary changes
- Don't over-engineer
- Explain trade-offs
- Show before/after structure
```

### Design Pattern Application
```
Refactor this code to use the [Pattern Name] design pattern:

[Paste code]

**Current Issues:** [what problems exist]
**Pattern Benefits:** [why this pattern helps]

**Show:**
1. Current structure analysis
2. Pattern implementation step-by-step
3. Complete refactored code
4. UML/diagram of new structure
5. Benefits gained
6. Trade-offs made
7. When NOT to use this pattern
```

### Performance Refactoring
```
Optimize this code for [performance/memory/readability]:

[Paste code]

**Current Metrics:**
- Execution time: [duration]
- Memory usage: [amount]
- CPU usage: [percentage]

**Optimization Goals:**
- Target: [reduce time by X%/reduce memory by Y%]

**Provide:**
1. Performance analysis (time/space complexity)
2. Identified bottlenecks with explanations
3. Step-by-step optimization strategy
4. Refactored code with optimizations
5. Performance comparison (before/after)
6. Trade-offs made
7. Alternative approaches considered
```

### Eliminating Code Duplication
```
I have code duplication across my project. Help me refactor:

**Duplicated Pattern:** [describe what's repeated]
**Locations:** [list files and line numbers]
**Context:** [why duplication exists]

**Refactoring Strategy:**
1. Identify the common abstraction
2. Design a reusable component/function
3. Show the extracted code
4. Show updated call sites
5. Handle edge cases that differ
6. Maintain backward compatibility
7. Suggest naming conventions

[Paste duplicate code snippets]
```

---

## New Feature Development

### Feature Implementation Planning
```
I need to implement this feature: [feature description]

**Requirements:**
- User story: [as a [user], I want [feature] so that [benefit]]
- Acceptance criteria: [list criteria]
- Technical constraints: [performance/compatibility/etc.]

**Current System:**
- Architecture: [description]
- Relevant components: [list]
- Database schema: [relevant tables]

**Planning Needed:**
1. **Design Approach** - High-level design and architecture
2. **Component Breakdown** - What needs to be built
3. **Data Model** - Database changes needed
4. **API Design** - Endpoints and contracts
5. **Integration Points** - What existing code is affected
6. **Testing Strategy** - How to test this
7. **Migration Plan** - Deployment considerations
8. **Time Estimate** - Complexity and effort

Don't write code yet - create a comprehensive plan first.
```

### API Endpoint Design
```
Design a RESTful API endpoint for: [purpose]

**Requirements:**
- Resource: [what it manages]
- Operations: [CRUD or specific actions]
- Authentication: [type required]
- Authorization: [access control rules]
- Rate limiting: [requirements]

**Design Needed:**
1. HTTP method and path
2. Request structure with examples
3. Response structure with examples (success and errors)
4. Status codes for different scenarios
5. Query parameters and filters
6. Pagination strategy
7. Error response format
8. Validation rules
9. Performance considerations
10. Versioning strategy

Follow REST best practices and [framework] conventions.
```

### Database Schema Design
```
Design a database schema for: [feature/application]

**Requirements:**
- Data to store: [entities and their attributes]
- Relationships: [how entities relate]
- Query patterns: [common operations]
- Scale: [expected data volume]
- Database: [PostgreSQL/MySQL/MongoDB]

**Design Criteria:**
1. Proper normalization (or denormalization where needed)
2. Indexing strategy for performance
3. Constraint definitions (FK, unique, check)
4. Data types with appropriate sizes
5. Migration scripts (up/down)
6. Sample queries for common operations
7. Explain design trade-offs

**Provide:**
- Entity-Relationship diagram
- CREATE TABLE statements
- Index creation statements
- Sample data
- Common query examples
```

### Microservice Design
```
Design a microservice for: [capability]

**System Context:**
- Overall architecture: [existing services]
- Communication: [REST/gRPC/messaging]
- Data storage: [constraints]
- Scale requirements: [load expectations]

**Design Aspects:**

**1. Service Boundaries**
- Single responsibility
- Domain boundaries
- Data ownership

**2. API Contract**
- Endpoints/operations
- Request/response formats
- Versioning strategy

**3. Data Management**
- Database per service
- Data consistency approach (eventual/strong)
- Data synchronization needs

**4. Communication**
- Synchronous vs asynchronous
- Event schemas (if applicable)
- Service discovery

**5. Resilience**
- Failure scenarios
- Circuit breaker patterns
- Retry strategies

**6. Observability**
- Logging strategy
- Metrics to track
- Distributed tracing

**7. Deployment**
- Containerization approach
- Configuration management
- Secrets management
```

### Full-Stack Feature Flow
```
Implement end-to-end feature: [feature name]

**Tech Stack:**
- Frontend: [React/Vue/Angular]
- Backend: [Node.js/Python/Java]
- Database: [type]
- State Management: [Redux/Zustand/etc.]

**Feature Requirements:**
[User stories and acceptance criteria]

**Implementation Flow:**

**Phase 1: Backend**
1. Database schema changes
2. API endpoints with validation
3. Business logic implementation
4. Error handling
5. Unit tests

**Phase 2: Frontend**
1. Component structure
2. State management setup
3. API integration
4. Form handling and validation
5. Error handling and loading states
6. Responsive design considerations

**Phase 3: Integration**
1. End-to-end flow testing
2. Error scenario handling
3. Performance optimization
4. Documentation

Build this incrementally with working examples at each phase.
```

---

## Testing & Quality Assurance

### Comprehensive Test Suite
```
Create a complete test suite for:

[Paste code]

**Test Coverage Needed:**

**1. Unit Tests**
- Test each function independently
- Mock external dependencies
- Cover edge cases and boundaries
- Test error conditions

**2. Integration Tests**
- Test component interactions
- Database operations
- External API calls
- Authentication/authorization

**3. End-to-End Tests**
- Critical user journeys
- Happy paths
- Error scenarios

**Test Framework:** [Jest/Pytest/JUnit]

**For Each Test:**
- Clear test names describing what's tested
- Arrange-Act-Assert structure
- Isolated and independent tests
- Good test data setup
- Assertion explanations

**Include:**
- Test file organization
- Setup and teardown code
- Mock/fixture patterns
- Coverage targets
```

### Test-Driven Development
```
Use TDD to implement: [feature description]

**Requirements:** [specifications]

**TDD Workflow:**

**Step 1: Write Failing Tests**
- Define expected behavior through tests
- Cover happy path
- Cover edge cases
- Cover error scenarios

**Step 2: Implementation Plan**
- Outline the minimal code to pass tests

**Step 3: Refactoring Strategy**
- Code quality improvements
- Performance optimizations

**Deliverables:**
1. Complete test suite (written first)
2. Implementation that passes all tests
3. Refactored clean code
4. Documentation

Follow strict Red-Green-Refactor cycle.
```

### Edge Case Identification
```
Identify all edge cases and create tests:

[Paste code/feature description]

**Analysis Needed:**
1. **Input Boundaries** - Min/max values, empty inputs, null/undefined
2. **State Transitions** - Unexpected state changes
3. **Concurrency** - Race conditions, simultaneous operations
4. **Resource Limits** - Memory, file handles, connections
5. **External Dependencies** - API failures, timeouts, network issues
6. **Data Integrity** - Invalid formats, character encoding, injection
7. **Business Logic** - Rule violations, contradictions

**For Each Edge Case:**
- Description of the scenario
- Expected behavior
- Test implementation
- Handling strategy if not currently addressed
```

### Integration Test Design
```
Design integration tests for: [system/feature]

**System Architecture:**
[Describe components, databases, external services]

**Integration Points to Test:**
1. [Component A] ↔ [Component B]
2. [Service] ↔ [Database]
3. [System] ↔ [External API]

**For Each Integration:**
- Test successful interaction
- Test failure scenarios
- Test retry/timeout behavior
- Test data consistency
- Test transaction boundaries
- Test authentication/authorization

**Test Environment:**
- Setup requirements
- Docker compose or test containers
- Mock vs real external services
- Test data management
```

---

## Architecture & System Design

### High-Level System Design
```
Design a system for: [application description]

**Requirements:**
- Users: [expected scale]
- Operations: [key features and workflows]
- Non-functional: [performance, availability, consistency needs]
- Constraints: [budget, technology, team expertise]

**Design Aspects:**

**1. Architecture Pattern**
- Monolith vs microservices decision
- Rationale for choice

**2. High-Level Components**
- Client applications
- API layer/Gateway
- Backend services
- Databases
- Caching layers
- Message queues
- External integrations

**3. Data Flow**
- Request/response patterns
- Event flows
- Data synchronization

**4. Scalability Strategy**
- Horizontal vs vertical scaling
- Load balancing
- Database scaling
- Caching strategy

**5. Reliability**
- Redundancy
- Failover mechanisms
- Backup and recovery

**6. Security**
- Authentication/authorization
- Data encryption
- Network security

**Deliverables:**
- Architecture diagram
- Component descriptions
- Technology choices with rationale
- Trade-offs made
```

### Microservices Architecture
```
Design a microservices architecture for: [application]

**Business Capabilities:** [list domains/capabilities]
**Scale Requirements:** [load expectations]

**Design Framework:**

**1. Service Decomposition**
- Identify bounded contexts (DDD)
- Define service boundaries
- Single responsibility per service
- Data ownership strategy

**2. Communication Patterns**
- Synchronous (REST/gRPC)
- Asynchronous (Events/Messages)
- API Gateway pattern
- Service mesh considerations

**3. Data Management**
- Database per service
- Data consistency (SAGA pattern)
- Event sourcing considerations
- CQRS where applicable

**4. Cross-Cutting Concerns**
- Authentication/authorization (OAuth2/JWT)
- Service discovery
- Configuration management
- API versioning

**5. Resilience Patterns**
- Circuit breaker
- Bulkhead
- Retry with exponential backoff
- Timeout strategies

**6. Observability**
- Centralized logging
- Distributed tracing
- Metrics and monitoring
- Health checks

**7. Deployment**
- Containerization (Docker)
- Orchestration (Kubernetes)
- CI/CD pipelines
- Blue-green/canary deployments

**Provide:**
- Architecture diagram
- Service catalog
- API contracts
- Deployment architecture
```

### Scalability Design
```
Design for scalability: [system/component]

**Current State:**
- Architecture: [description]
- Load: [current metrics]
- Bottlenecks: [identified issues]

**Target Scale:**
- Users: [X to Y]
- Requests: [current to target RPS]
- Data volume: [current to target]

**Scalability Strategy:**

**1. Application Layer**
- Stateless services
- Horizontal scaling
- Load balancing strategy
- Session management

**2. Database Layer**
- Read replicas
- Sharding strategy
- Connection pooling
- Query optimization

**3. Caching**
- Cache-aside pattern
- Cache invalidation
- CDN for static content
- Database query caching

**4. Asynchronous Processing**
- Message queues
- Background jobs
- Event-driven architecture

**5. Infrastructure**
- Auto-scaling policies
- Resource allocation
- Network optimization

**Provide:**
- Scaling architecture diagram
- Implementation phases
- Cost analysis
- Monitoring strategy
```

### Migration Strategy
```
Design migration plan from [current] to [target]:

**Current System:**
- Architecture: [description]
- Tech stack: [technologies]
- Data volume: [size]
- Daily traffic: [metrics]
- Pain points: [issues]

**Target System:**
- Desired architecture: [new design]
- Technology choices: [stack]
- Goals: [what we want to achieve]

**Migration Strategy:**

**1. Assessment**
- Inventory of components
- Dependency mapping
- Risk analysis
- Success criteria

**2. Approach**
- Big bang vs incremental
- Strangler fig pattern
- Parallel run strategy
- Rollback plan

**3. Phases**
- Phase breakdown
- Dependencies between phases
- Testing at each phase
- Data migration strategy

**4. Risk Mitigation**
- Feature flags
- Monitoring and alerting
- Performance testing
- Gradual traffic shift

**5. Rollout Plan**
- Timeline
- Team allocation
- Communication plan
- Training needs

**Deliverables:**
- Detailed migration roadmap
- Technical design documents
- Testing strategy
- Rollback procedures
```

---

## Performance Optimization

### Performance Analysis
```
Analyze and optimize performance:

**Component:** [specific component/endpoint/query]

**Current Performance:**
- Response time: [Xms]
- Throughput: [Y requests/second]
- Resource usage: [CPU/Memory/Disk]
- Database query time: [Zms]

**Code:**
[Paste relevant code]

**Analysis Required:**

**1. Profiling**
- Identify bottlenecks
- Measure each operation
- Find N+1 queries
- Detect memory leaks

**2. Algorithm Analysis**
- Time complexity: O(?)
- Space complexity: O(?)
- Can we do better?

**3. Optimization Strategies**
- Algorithm improvements
- Database query optimization
- Caching opportunities
- Lazy loading
- Parallel processing
- Resource pooling

**4. Implementation**
- Optimized code
- Performance comparison
- Trade-offs made
- Monitoring metrics

**Provide:**
- Detailed analysis
- Before/after benchmarks
- Optimized implementation
- Measurement strategy
```

### Database Query Optimization
```
Optimize this database query:

**Database:** [PostgreSQL/MySQL/MongoDB]
**Query:** [SQL/NoSQL query]
**Current Performance:** [execution time]
**Frequency:** [how often run]
**Data Volume:** [table sizes]

**Schema:**
[Table definitions with indexes]

**Optimization Needed:**

**1. Query Analysis**
- Execution plan analysis
- Index usage
- Join strategies
- Subquery vs join

**2. Index Optimization**
- Missing indexes
- Unused indexes
- Composite index opportunities
- Index selectivity

**3. Query Rewriting**
- Simplified logic
- Better join order
- Elimination of subqueries
- Using CTEs effectively

**4. Schema Considerations**
- Denormalization opportunities
- Partitioning strategies
- Archival of old data

**Provide:**
- Optimized query
- Index creation statements
- Execution plan comparison
- Performance improvement metrics
```

### Frontend Performance
```
Optimize frontend performance:

**Application:** [React/Vue/Angular app]
**Issues:** [slow loading/janky scrolling/memory issues]

**Current Metrics:**
- Load time: [Xs]
- Time to Interactive: [Ys]
- Bundle size: [Zmb]
- Lighthouse score: [score]

**Code:** [relevant components]

**Optimization Areas:**

**1. Bundle Size**
- Code splitting strategy
- Tree shaking opportunities
- Lazy loading components
- Dynamic imports

**2. Rendering Performance**
- Identify unnecessary re-renders
- Memoization opportunities
- Virtual scrolling
- Debouncing/throttling

**3. Network**
- Image optimization
- Asset compression
- HTTP/2 optimization
- CDN strategy
- Service worker/caching

**4. Critical Path**
- Above-fold optimization
- Async/defer scripts
- Preloading critical resources
- Font loading strategy

**Provide:**
- Optimized code
- Webpack/Vite config changes
- Performance budget
- Measurement plan
```

### API Performance Tuning
```
Optimize API performance:

**Endpoint:** [endpoint details]
**Current:** [response time, throughput]
**Target:** [desired metrics]

**Analysis:**

**1. Request Processing**
- Authentication/authorization overhead
- Input validation efficiency
- Middleware bottlenecks

**2. Business Logic**
- Algorithm complexity
- External API calls
- File I/O operations
- Computation-heavy operations

**3. Data Access**
- N+1 query problems
- Unnecessary data fetching
- Missing indexes
- Connection pool settings

**4. Response Preparation**
- Serialization overhead
- Response size
- Compression

**5. Infrastructure**
- Load balancer configuration
- Server resources
- Network latency

**Optimization Strategy:**
- Identify bottleneck
- Implement caching
- Optimize queries
- Async processing
- Response optimization
- Monitoring setup

[Paste relevant code]
```

---

## Security Review

### Comprehensive Security Audit
```
Perform security review of:

[Paste code/system description]

**Security Checklist:**

**1. Authentication & Authorization**
- Password storage (hashing/salting)
- Session management
- Token security (JWT best practices)
- Multi-factor authentication
- Authorization checks at all levels
- Role-based access control

**2. Input Validation**
- SQL injection vulnerabilities
- XSS (Cross-Site Scripting)
- Command injection
- Path traversal
- XML external entity (XXE)
- Deserialization attacks

**3. Data Protection**
- Sensitive data encryption (at rest/in transit)
- PII handling
- Secure storage of secrets
- HTTPS enforcement
- Certificate validation

**4. API Security**
- Rate limiting
- CORS configuration
- API key management
- Request signing
- Versioning security

**5. Dependencies**
- Known vulnerabilities (npm audit/snyk)
- Outdated packages
- Supply chain security

**6. Error Handling**
- Information disclosure
- Stack trace exposure
- Proper logging (no sensitive data)

**7. Business Logic**
- Race conditions
- Integer overflow
- Price manipulation
- Privilege escalation

**For Each Issue Found:**
- Severity: [Critical/High/Medium/Low]
- Attack vector
- Impact
- Remediation steps
- Example exploit (if applicable)
```

### OWASP Top 10 Review
```
Review code against OWASP Top 10:

[Paste code]

**Framework:** [specify technology]

**Check For:**

**1. Broken Access Control**
- Unauthorized access to functions/data
- Missing function-level access control
- Forced browsing

**2. Cryptographic Failures**
- Weak crypto algorithms
- Hardcoded secrets
- Insecure key management

**3. Injection**
- SQL injection
- NoSQL injection
- OS command injection
- LDAP injection

**4. Insecure Design**
- Missing security controls in design
- Lack of threat modeling

**5. Security Misconfiguration**
- Default credentials
- Verbose error messages
- Unnecessary features enabled
- Insecure headers

**6. Vulnerable Components**
- Using outdated libraries
- Unpatched vulnerabilities

**7. Authentication Failures**
- Weak password policy
- Session fixation
- Missing logout functionality

**8. Software/Data Integrity**
- Unsigned updates
- Insecure CI/CD
- Untrusted data deserialization

**9. Logging Failures**
- Missing security events
- Insufficient log protection

**10. Server-Side Request Forgery (SSRF)**
- Unvalidated URLs
- Access to internal services

Provide specific code examples of vulnerabilities and fixes.
```

### Secure Code Rewrite
```
Rewrite this code with security best practices:

[Paste code]

**Security Requirements:**
- [e.g., handle user input securely, prevent SQL injection]
- [additional requirements]

**Secure Implementation:**
1. Identify all security issues in current code
2. Explain each vulnerability
3. Provide secure alternative
4. Add security comments
5. Include input validation
6. Implement proper error handling
7. Add security testing examples

**Follow standards:**
- OWASP guidelines
- Framework security best practices
- Industry standards (e.g., PCI-DSS if handling payments)
```

---

## Documentation

### API Documentation
```
Generate comprehensive API documentation:

**Endpoint:** [URL and method]
**Code:** [implementation code]

**Documentation Structure:**

**1. Overview**
- Purpose and functionality
- When to use this endpoint

**2. Authentication**
- Required auth type
- Token format
- Scopes/permissions needed

**3. Request**
- HTTP method
- URL structure with parameters
- Headers required
- Query parameters (name, type, required, description)
- Request body schema with examples
- Content-Type

**4. Response**
- Success response (200/201/204)
  - Schema
  - Example response
- Error responses (400/401/403/404/500)
  - Error codes
  - Error messages
  - Example responses

**5. Examples**
- cURL examples
- Client library examples ([JavaScript/Python/etc.])
- Postman collection format

**6. Rate Limiting**
- Limits and quotas
- Rate limit headers

**7. Notes**
- Versioning info
- Deprecation warnings
- Related endpoints
- Performance considerations

Format: [OpenAPI 3.0/Markdown/Swagger]
```

### Code Documentation
```
Create comprehensive documentation:

[Paste code]

**Documentation Needs:**

**1. Inline Comments**
- Complex logic explanation
- Algorithm description
- Non-obvious decisions
- Workarounds and why they exist
- TODOs and FIXMEs

**2. Function/Method Documentation**
- Purpose and functionality
- Parameters (name, type, description)
- Return value (type, description)
- Exceptions thrown
- Usage examples
- Side effects
- Performance notes

**3. Module/Class Documentation**
- Overview of responsibility
- Public API surface
- Usage examples
- Dependencies
- Design patterns used
- Thread safety notes

**4. Architecture Documentation**
- System overview
- Component interactions
- Data flow diagrams
- Deployment architecture
- Technology decisions

Format: [JSDoc/Docstring/JavaDoc/etc.]
```

### README Generation
```
Generate a professional README.md for:

**Repository:** [name and description]
**Technology:** [stack]
**Target Audience:** [developers/end-users/both]

**README Structure:**

**1. Header**
- Project name and tagline
- Badges (build status, coverage, version, license)
- Brief description (1-2 sentences)

**2. Features**
- Key features list
- What makes it unique

**3. Demo**
- Screenshots/GIFs
- Live demo link (if applicable)

**4. Prerequisites**
- Required software/tools
- System requirements
- Knowledge prerequisites

**5. Installation**
- Step-by-step installation
- Multiple installation methods
- Common issues and solutions

**6. Quick Start**
- Minimal example to get started
- Configuration basics
- First successful run

**7. Usage**
- Common use cases with examples
- API reference link
- Configuration options

**8. Architecture** (if complex)
- High-level overview
- Mermaid diagrams
- Design decisions

**9. Development**
- Setting up dev environment
- Running tests
- Contributing guidelines
- Code style

**10. Deployment**
- Production deployment steps
- Environment variables
- Scaling considerations

**11. Troubleshooting**
- Common issues and solutions
- FAQ
- Where to get help

**12. License**
- License type
- Copyright information

**13. Acknowledgments**
- Credits
- Inspiration
- Third-party resources

Make it engaging, clear, and professional with proper Markdown formatting.
```

### Technical Specification Document
```
Create a technical specification for: [feature/system]

**Requirements:** [functional and non-functional requirements]

**Specification Format:**

**1. Executive Summary**
- Problem statement
- Proposed solution overview
- Key benefits

**2. Goals and Non-Goals**
- What we're solving
- What's explicitly out of scope

**3. Background**
- Context and motivation
- Current state analysis
- Stakeholders

**4. Detailed Design**
- Architecture overview with diagrams
- Component breakdown
- API contracts
- Data models
- Sequence diagrams for key flows
- Security considerations
- Performance requirements

**5. Implementation Plan**
- Phases and milestones
- Dependencies
- Risk assessment
- Estimated timeline

**6. Testing Strategy**
- Unit testing approach
- Integration testing
- Performance testing
- Security testing

**7. Deployment Plan**
- Rollout strategy
- Monitoring and alerts
- Rollback procedure

**8. Alternatives Considered**
- Other approaches evaluated
- Why this approach was chosen
- Trade-offs

**9. Open Questions**
- Unresolved issues
- Items needing clarification

**10. References**
- Related documents
- External resources
- Similar systems
```

---

## Advanced Strategies

### Multi-Step Problem Solving
```
Help me solve this complex problem using a systematic approach:

**Problem:** [detailed description]
**Context:** [relevant background]
**Constraints:** [limitations]

**Step-by-Step Process:**

**Step 1: Problem Decomposition**
- Break the problem into smaller sub-problems
- Identify dependencies between sub-problems
- Prioritize by impact and effort

**Step 2: Research & Analysis**
- Similar problems and solutions
- Existing libraries or tools
- Best practices and patterns

**Step 3: Solution Design**
- High-level approach
- Algorithm or architecture
- Data structures needed
- Trade-off analysis

**Step 4: Implementation Strategy**
- Build incrementally
- What to build first
- Testing at each stage
- Validation checkpoints

**Step 5: Optimization**
- Performance considerations
- Scalability concerns
- Maintainability improvements

**Step 6: Validation**
- How to verify it works
- Edge cases to test
- Performance benchmarks

Don't jump to code - work through each step with me.
```

### Comparative Analysis
```
Compare and recommend the best approach:

**Problem:** [what I'm trying to solve]
**Context:** [constraints and requirements]

**Approaches to Compare:**
1. [Approach A]
2. [Approach B]
3. [Approach C]
[Add more as needed]

**Comparison Framework:**

**For Each Approach:**

**1. Implementation Complexity**
- Development effort
- Learning curve
- Lines of code estimate

**2. Performance**
- Time complexity
- Space complexity
- Benchmarks/estimates

**3. Scalability**
- Horizontal scaling
- Vertical scaling
- Bottlenecks

**4. Maintainability**
- Code clarity
- Testability
- Debugging ease

**5. Flexibility**
- Extensibility
- Handling changes
- Future-proofing

**6. Dependencies**
- Third-party libraries
- Infrastructure requirements
- Team expertise needed

**7. Costs**
- Development time
- Infrastructure costs
- Operational overhead

**8. Risks**
- Technical risks
- Known limitations
- Failure modes

**Final Recommendation:**
- Best approach for my use case
- Rationale
- Implementation roadmap
- Fallback options
```

### Rubber Duck Debugging
```
Act as my rubber duck. Let me explain my problem, then help me find the solution:

**My Explanation:**
[Let me explain what I'm trying to do and what's going wrong]

**Your Role:**
1. Ask clarifying questions about:
   - Exact behavior vs expected behavior
   - When it fails vs when it works
   - What I've tried so far
   - Assumptions I'm making

2. Help me reason through:
   - Step-by-step execution
   - Variable states at each point
   - Logic flow
   - Edge cases

3. Point out:
   - Logical inconsistencies
   - Unstated assumptions
   - Alternative perspectives
   - Simpler approaches

4. Guide me to discover the solution rather than giving it directly

Ask questions one at a time to help me think through this systematically.
```

### Learning Through Code Review
```
Help me learn by reviewing my code with educational focus:

[Paste code]

**Learning Objectives:**
- [e.g., understand best practices, learn design patterns, improve architecture skills]

**Review Format:**

**1. What's Done Well**
- Highlight good practices
- Explain why they're good
- Encourage these patterns

**2. Learning Opportunities**
- Areas for improvement
- Explain the principle/pattern
- Show why it matters
- Provide examples

**3. Deeper Concepts**
- Design patterns present or missing
- Architectural principles
- Language-specific idioms
- Industry best practices

**4. Resources**
- Articles/books to read
- Similar codebases to study
- Exercises to practice

**5. Progressive Improvements**
- Start with highest impact changes
- Build complexity gradually
- Explain the journey

Make this educational - teach me WHY, not just WHAT to change.
```

### Pair Programming Session
```
Let's pair program on: [task description]

**My Role:** [driver/navigator]
**Your Role:** [navigator/driver]

**Session Format:**

**If I'm Driving (writing code):**
- You provide high-level direction
- Suggest approaches and patterns
- Ask questions about my decisions
- Warn about potential issues
- Keep me focused on current task

**If You're Driving (generating code):**
- I'll provide direction
- Ask you to explain your decisions
- Suggest alternatives
- Request tests or documentation
- Guide architecture decisions

**Session Rules:**
1. Think out loud - explain reasoning
2. Switch roles when stuck or at natural breakpoints
3. Write tests alongside implementation
4. Refactor as we go
5. Take breaks at logical milestones

**Current Task:** [start with first small task]

Let's begin! [Start the conversation]
```

### Progressive Difficulty Learning
```
Teach me [concept/technique] through progressive examples:

**Learning Goal:** [what I want to learn]
**Current Level:** [beginner/intermediate/advanced]

**Teaching Approach:**

**Level 1: Fundamentals**
- Simplest possible example
- Core concept only
- Extensive comments explaining each part
- Walk through execution step-by-step

**Level 2: Practical Application**
- Realistic but simple use case
- Introduce one additional complexity
- Explain why this approach
- Show common mistakes to avoid

**Level 3: Real-World Scenario**
- Production-like complexity
- Multiple interacting concerns
- Error handling
- Performance considerations
- Best practices

**Level 4: Advanced Patterns**
- Edge cases
- Optimization techniques
- Alternative approaches
- When to use vs not use

**Level 5: Mastery Challenge**
- Complex problem to solve independently
- Multiple valid solutions
- Review and feedback

For each level:
- Check my understanding before moving on
- Provide exercises
- Explain the "why" behind patterns
```

### Architecture Decision Record (ADR)
```
Create an Architecture Decision Record for:

**Decision:** [what we're deciding]
**Date:** [current date]

**ADR Template:**

**1. Status**
- [Proposed/Accepted/Deprecated/Superseded]

**2. Context**
- What's the issue we're trying to solve?
- What factors are driving this decision?
- What constraints do we face?
- What's the current state?

**3. Decision**
- What's our decision?
- What approach are we taking?
- What are the key components?

**4. Rationale**
- Why this decision?
- What problem does it solve?
- What alternatives did we consider?
- Why were alternatives rejected?

**5. Consequences**

**Positive:**
- Benefits gained
- Problems solved
- Improvements made

**Negative:**
- Trade-offs accepted
- New risks introduced
- Limitations created

**Neutral:**
- Changes to team workflow
- Learning curve
- Migration requirements

**6. Implementation Notes**
- Key implementation details
- Migration path from current state
- Timeline considerations

**7. Related Decisions**
- Links to related ADRs
- Dependencies
- Superseded decisions

**8. References**
- Research materials
- Documentation
- Similar implementations

Create a clear, well-reasoned ADR that future developers will understand.
```

### Code Archaeology
```
Help me understand this mysterious code:

[Paste code]

**What I Know:**
- [any context or documentation available]

**What I Don't Know:**
- [questions I have]

**Archaeological Analysis:**

**1. Initial Observations**
- What does this code appear to do?
- What's the overall structure?
- Any immediate red flags?

**2. Historical Context**
- What problem was this solving?
- What was the state of technology then?
- Why might it be written this way?

**3. Decoding**
- Variable naming patterns
- Coding style clues
- Algorithm identification
- Framework/library versions

**4. Dependencies**
- What does it depend on?
- What depends on it?
- Side effects?

**5. Testing Strategy**
- How can I safely test this?
- What inputs to try?
- How to verify correct behavior?

**6. Modernization Path**
- Should this be rewritten?
- What would modern equivalent look like?
- Migration risks?

**7. Documentation**
- Create documentation explaining this
- Add comments for future maintainers

Help me uncover the mysteries of this code!
```

### Root Cause Analysis
```
Help me find the root cause of:

**Issue:** [problem description]
**Symptoms:** [what users/systems experience]
**When Started:** [timeframe]
**Frequency:** [always/intermittent/specific conditions]

**RCA Process:**

**1. Problem Statement**
- Clear, specific description
- Impact and severity
- Who's affected

**2. Timeline**
- When first noticed
- Recent changes (code, config, infrastructure, data)
- Correlated events

**3. Data Gathering**
- Logs analysis
- Metrics review
- Error rates
- User reports

**4. Five Whys**
- Why did this happen?
  - Because [reason 1]
- Why [reason 1]?
  - Because [reason 2]
- Why [reason 2]?
  - Because [reason 3]
- Why [reason 3]?
  - Because [reason 4]
- Why [reason 4]?
  - Because [root cause]

**5. Root Cause Identification**
- What's the fundamental cause?
- Why wasn't this caught earlier?
- What allowed this to happen?

**6. Contributing Factors**
- What else enabled this?
- What didn't work as expected?

**7. Solution**
- Immediate fix
- Long-term solution
- Prevention measures

**8. Action Items**
- What needs to change?
- Who's responsible?
- Timeline?

**9. Lessons Learned**
- What did we learn?
- How do we prevent similar issues?
- Process improvements needed?

Use facts and evidence, not assumptions.
```

### Technical Debt Assessment
```
Assess technical debt in: [codebase/component]

**Context:**
- Age of code: [timeframe]
- Team size: [number]
- Business pressure: [high/medium/low]

**Debt Analysis:**

**1. Code Quality Issues**
- Code smells identified
- Violation of SOLID principles
- Missing design patterns
- Poor naming conventions
- Excessive complexity (cyclomatic)

**2. Architectural Debt**
- Tight coupling
- Circular dependencies
- Missing abstractions
- Monolithic components that should be separated

**3. Testing Debt**
- Test coverage gaps
- Missing integration tests
- Flaky tests
- Slow test suites

**4. Documentation Debt**
- Missing documentation
- Outdated documentation
- Unclear APIs

**5. Infrastructure Debt**
- Outdated dependencies
- Security vulnerabilities
- Deprecated technologies
- Configuration complexity

**6. Performance Debt**
- Known bottlenecks
- N+1 queries
- Missing indexes
- Inefficient algorithms

**For Each Debt Item:**

**Severity:** [Critical/High/Medium/Low]

**Impact:**
- Development velocity
- Bug frequency
- Onboarding difficulty
- Production risks

**Effort to Fix:** [hours/days/weeks]

**Priority Score:** [Impact × Urgency / Effort]

**Payoff Strategy:**
- Quick wins (high impact, low effort)
- Critical items (high risk)
- Strategic refactoring (enables future work)
- Boy Scout rule (improve while working)

**Roadmap:**
- Immediate actions (this sprint)
- Short-term (this quarter)
- Long-term (this year)
- Acceptable debt to carry

Create a prioritized action plan with business justification.
```

---

## Specialized Domain Prompts

### DevOps & Infrastructure
```
Design CI/CD pipeline for: [project]

**Requirements:**
- Source control: [GitHub/GitLab/Bitbucket]
- Build tool: [tool]
- Testing requirements: [unit/integration/e2e]
- Deployment targets: [staging/production]
- Infrastructure: [Docker/Kubernetes/VM]

**Pipeline Stages:**

**1. Source**
- Trigger conditions
- Branch strategies
- Version tagging

**2. Build**
- Environment setup
- Dependency installation
- Compilation/bundling
- Artifact generation

**3. Test**
- Unit tests
- Integration tests
- Code coverage requirements
- Quality gates

**4. Security Scanning**
- Dependency vulnerabilities
- SAST (Static Analysis)
- DAST (Dynamic Analysis)
- Container scanning

**5. Deploy**
- Deployment strategies (blue-green/canary/rolling)
- Environment promotion
- Database migrations
- Configuration management

**6. Verify**
- Smoke tests
- Health checks
- Rollback triggers

**7. Monitor**
- Logging setup
- Metrics collection
- Alerting rules

**Provide:**
- Pipeline configuration file
- Scripts needed
- Best practices
- Security considerations
```

### Data Engineering
```
Design data pipeline for: [use case]

**Data Sources:**
- [List sources with volume and frequency]

**Processing Requirements:**
- Transformations needed
- Data quality rules
- Aggregations
- Expected latency

**Destination:**
- [Data warehouse/lake/database]

**Pipeline Design:**

**1. Ingestion**
- Batch vs streaming
- Data validation
- Schema evolution
- Error handling

**2. Processing**
- ETL vs ELT
- Transformations
- Data quality checks
- Deduplication

**3. Storage**
- Partitioning strategy
- Compression
- Retention policies
- Backup strategy

**4. Orchestration**
- Workflow tool (Airflow/Dagster)
- Scheduling
- Dependencies
- Retry logic

**5. Monitoring**
- Data quality metrics
- Pipeline health
- SLA monitoring
- Alerting

**Technology Stack:**
- Recommend tools for each component
- Rationale for choices
- Scalability considerations

**Provide:**
- Architecture diagram
- Sample DAG/workflow
- Data models
- Monitoring dashboard design
```

### Machine Learning Integration
```
Integrate ML model into application:

**Model Details:**
- Type: [classification/regression/etc.]
- Framework: [TensorFlow/PyTorch/Scikit-learn]
- Input format: [description]
- Output format: [description]
- Performance: [latency requirements]

**Integration Requirements:**

**1. Model Serving**
- Serving options (REST API/gRPC/Batch)
- Containerization
- Scaling strategy
- A/B testing capability

**2. Input Processing**
- Feature extraction
- Data validation
- Preprocessing pipeline
- Error handling

**3. Inference**
- Batching strategy
- Caching
- Fallback mechanisms
- Timeout handling

**4. Output Processing**
- Post-processing
- Confidence thresholding
- Response formatting

**5. Monitoring**
- Model performance metrics
- Data drift detection
- Latency tracking
- Error rates

**6. Model Updates**
- Versioning strategy
- Deployment process
- Rollback procedures
- Comparison testing

**Provide:**
- Integration architecture
- API contract
- Deployment configuration
- Monitoring setup
- Testing strategy
```

---

## Quick Reference Templates

### Bug Report Template
```
**Bug Title:** [Clear, specific description]

**Environment:**
- OS: [Windows/Mac/Linux]
- Browser/App Version: [version]
- Environment: [dev/staging/production]

**Steps to Reproduce:**
1. [First step]
2. [Second step]
3. [Third step]

**Expected Behavior:**
[What should happen]

**Actual Behavior:**
[What actually happens]

**Screenshots/Logs:**
[Attach relevant images or logs]

**Additional Context:**
- Frequency: [always/sometimes/rare]
- User impact: [high/medium/low]
- Workaround: [if known]

**Possible Cause:**
[Your hypothesis if any]
```

### Performance Optimization Template
```
**Component:** [What to optimize]
**Current Metrics:** [Baseline measurements]
**Target:** [Performance goals]

**Profiling Results:**
[Attach profiler output or describe bottlenecks]

**Optimization Plan:**
1. [First optimization with expected impact]
2. [Second optimization with expected impact]
3. [Third optimization with expected impact]

**Trade-offs:**
[What compromises are acceptable]

**Testing Strategy:**
[How to measure improvements]

**Success Criteria:**
[How we know it's fixed]
```

### Code Review Checklist
```
**Functionality**
- [ ] Code works as intended
- [ ] Edge cases handled
- [ ] Error handling complete

**Code Quality**
- [ ] Follows team conventions
- [ ] DRY principle applied
- [ ] SOLID principles followed
- [ ] Appropriate design patterns

**Testing**
- [ ] Unit tests included
- [ ] Integration tests where needed
- [ ] Test coverage adequate

**Security**
- [ ] Input validation
- [ ] No SQL injection risks
- [ ] No XSS vulnerabilities
- [ ] Secrets not hardcoded

**Performance**
- [ ] No obvious bottlenecks
- [ ] Database queries optimized
- [ ] Appropriate caching

**Documentation**
- [ ] Code comments where needed
- [ ] API documentation updated
- [ ] README updated if needed

**Git**
- [ ] Atomic commits
- [ ] Clear commit messages
- [ ] No merge conflicts
```

---

## Pro Tips for Using These Prompts

**1. Customize for Your Context**
- Replace placeholders with actual details
- Add project-specific requirements
- Include relevant constraints

**2. Be Specific**
- Provide exact versions of technologies
- Include actual error messages
- Share relevant code snippets

**3. Iterate**
- Start with high-level questions
- Drill down based on responses
- Ask follow-up questions

**4. Combine Prompts**
- Use multiple templates for complex issues
- Chain prompts for comprehensive solutions

**5. Maintain Context**
- Build on previous responses
- Reference earlier discussions
- Keep conversation focused

**6. Request Explanations**
- Don't just get solutions
- Ask "why" and "how"
- Request alternatives

**7. Validate Responses**
- Test suggested solutions
- Verify with documentation
- Cross-reference best practices

**8. Save Your Best Prompts**
- Build your personal library
- Refine based on results
- Share with team

---

## Conclusion

These prompts are starting points - adapt them to your specific needs, technology stack, and team practices. The key to effective prompting is:

1. **Clear context** - Set up the scenario properly
2. **Specific questions** - Ask for exactly what you need
3. **Structured format** - Request organized responses
4. **Iterative refinement** - Build on previous responses
5. **Validation** - Always verify and test suggestions

Happy coding! 🚀
