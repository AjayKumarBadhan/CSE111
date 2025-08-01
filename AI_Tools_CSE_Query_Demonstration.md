# AI Tools for CSE - Practical Prompting Guide with Examples

## Table of Contents
1. [Perplexity - CSE Research & Current Tech](#perplexity---cse-research--current-tech)
2. [NotebookLM - Technical Documentation Analysis](#notebooklm---technical-documentation-analysis)
3. [Jennai - Technical Content Creation](#jennai---technical-content-creation)
4. [ChatGPT - Programming & Problem Solving](#chatgpt---programming--problem-solving)
5. [Gemini - Multimodal Technical Analysis](#gemini---multimodal-technical-analysis)
6. [Claude - System Design & Architecture](#claude---system-design--architecture)

---

## Perplexity - CSE Research & Current Tech

### Basic Level CSE Prompts

#### Example 1: Technology Updates
**Prompt:**
```
What are the latest updates in Python 3.12?
```

**Expected Output:**
- New language features and syntax improvements
- Performance enhancements with benchmarks
- Deprecated features and migration notes
- Official Python documentation links
- Developer community discussions

#### Example 2: Framework Comparison
**Prompt:**
```
Compare React vs Angular for web development in 2025
```

**Expected Output:**
- Current version capabilities
- Performance metrics from recent studies
- Community adoption statistics
- Job market trends
- Recent feature updates and roadmaps

#### Example 3: Security Vulnerabilities
**Prompt:**
```
What are the recent cybersecurity threats in cloud computing?
```

**Expected Output:**
- Latest CVE reports and security advisories
- Attack vectors and mitigation strategies
- Industry response and patches
- Security research publications
- Expert recommendations

### Medium Level CSE Prompts

#### Example 1: Technology Architecture Research
**Prompt:**
```
Analyze the current state of microservices architecture adoption in enterprise software development. Include performance benchmarks, scalability challenges, DevOps integration complexities, and emerging patterns like service mesh. Focus on 2024-2025 industry reports and case studies.
```

**Expected Output:**
- Enterprise adoption statistics with sources
- Performance comparison studies
- Scalability analysis from real implementations
- DevOps toolchain integration challenges
- Service mesh technology trends (Istio, Linkerd)
- Case studies from major tech companies
- Industry analyst reports and whitepapers

#### Example 2: Emerging Technology Impact Analysis
**Prompt:**
```
Evaluate the impact of quantum computing advances on current cryptographic standards and blockchain technology. What are the timeline predictions for quantum threat to RSA encryption, and what post-quantum cryptographic solutions are being developed by NIST and industry?
```

**Expected Output:**
- Quantum computing milestone timeline
- Cryptographic vulnerability assessments
- NIST post-quantum cryptography standards
- Blockchain quantum resistance analysis
- Industry migration strategies
- Research publications and expert opinions
- Timeline predictions with confidence intervals

#### Example 3: AI/ML Infrastructure Evolution
**Prompt:**
```
Research the evolution of MLOps platforms and tools in 2024-2025. Compare Kubeflow, MLflow, and emerging alternatives for managing machine learning workflows at scale. Include cost analysis, integration capabilities, and enterprise adoption patterns.
```

**Expected Output:**
- Platform feature comparison matrix
- Cost analysis and ROI studies
- Enterprise case studies and implementations
- Integration ecosystem analysis
- Performance benchmarks and scalability tests
- Community adoption trends and surveys
- Vendor roadmaps and future developments

---

## NotebookLM - Technical Documentation Analysis

### Basic Level CSE Prompts

#### Example 1: API Documentation Summary
**Prompt:** (After uploading REST API documentation)
```
Summarize the main endpoints and their functions in this API documentation.
```

**Expected Output:**
- List of all endpoints with HTTP methods
- Brief description of each endpoint's purpose
- Required parameters and data types
- Authentication requirements
- Response format examples

#### Example 2: Code Review Analysis
**Prompt:** (After uploading code review comments)
```
What are the main issues identified in this code review?
```

**Expected Output:**
- Categorized list of issues (bugs, performance, style)
- Severity levels of different problems
- Suggested improvements and fixes
- Code quality metrics mentioned
- Reviewer consensus on priority items

#### Example 3: Technical Specification Extraction
**Prompt:** (After uploading system requirements document)
```
Extract all the technical requirements and constraints from this document.
```

**Expected Output:**
- Functional requirements list
- Non-functional requirements (performance, security)
- System constraints and limitations
- Technology stack requirements
- Integration specifications

### Medium Level CSE Prompts

#### Example 1: Multi-Document Architecture Analysis
**Prompt:** (After uploading system design docs, API specs, and database schemas)
```
Analyze the consistency between these system architecture documents, API specifications, and database schemas. Identify any discrepancies, missing components, or potential integration issues. Create a comprehensive architecture review report.
```

**Expected Output:**
- Cross-document consistency analysis
- Data flow validation between components
- API-database mapping verification
- Missing component identification
- Integration bottleneck analysis
- Scalability concern assessment
- Recommended architectural improvements

#### Example 2: Research Paper Synthesis for Implementation
**Prompt:** (After uploading 5-7 machine learning research papers)
```
Synthesize these machine learning research papers to create an implementation roadmap for a real-time recommendation system. Compare the algorithms, identify the most practical approaches for production deployment, and outline the technical challenges and solutions for each method.
```

**Expected Output:**
- Algorithm comparison matrix with pros/cons
- Performance benchmarks synthesis
- Implementation complexity assessment
- Scalability and latency analysis
- Production deployment considerations
- Technical challenge identification
- Recommended technology stack
- Development timeline estimation

#### Example 3: Codebase Documentation Analysis
**Prompt:** (After uploading multiple code files and README documents)
```
Analyze this codebase documentation and source code to create a comprehensive developer onboarding guide. Include setup instructions, architecture overview, coding standards, testing procedures, and contribution guidelines. Identify gaps in current documentation.
```

**Expected Output:**
- Complete setup and installation guide
- Architecture diagram and component explanation
- Code organization and structure analysis
- Coding standards and style guide compilation
- Testing framework and procedures
- Contribution workflow documentation
- Documentation gap identification
- Suggested improvements and additions

---

## Jennai - Technical Content Creation

### Basic Level CSE Prompts

#### Example 1: Technical Blog Post
**Prompt:**
```
Write a blog post explaining RESTful APIs for junior developers.
```

**Expected Output:**
- Beginner-friendly explanation with analogies
- Key concepts breakdown (HTTP methods, endpoints)
- Simple code examples
- Best practices overview
- Engaging writing style with practical examples

#### Example 2: Code Documentation
**Prompt:**
```
Write documentation for a Python function that implements binary search.
```

**Expected Output:**
- Function description and purpose
- Parameter explanations with types
- Return value specification
- Usage examples
- Time and space complexity notes

#### Example 3: Technical Tutorial
**Prompt:**
```
Create a step-by-step guide for setting up a React development environment.
```

**Expected Output:**
- Prerequisites and system requirements
- Installation steps with commands
- Configuration instructions
- Verification steps
- Troubleshooting common issues

### Medium Level CSE Prompts

#### Example 1: Comprehensive Technical Guide
**Prompt:**
```
Create a comprehensive guide for implementing microservices architecture for a e-commerce platform. Include service decomposition strategies, inter-service communication patterns, data management approaches, monitoring and observability setup, and deployment strategies using Docker and Kubernetes. Target audience: senior developers and architects.
```

**Expected Output:**
- Service boundary identification methodology
- Communication pattern analysis (sync/async)
- Data consistency strategies (SAGA, 2PC)
- API gateway and service mesh implementation
- Monitoring and logging architecture
- CI/CD pipeline design for microservices
- Security considerations and implementations
- Performance optimization techniques
- Deployment and scaling strategies

#### Example 2: Technical Architecture Blog Series
**Prompt:**
```
Write a 4-part blog series on "Building Scalable Real-time Systems" covering: (1) System Design Principles, (2) Message Queue Technologies, (3) Caching Strategies, and (4) Monitoring and Performance Optimization. Each post should be 1500-2000 words with practical examples, code snippets, and industry case studies.
```

**Expected Output:**
- Series overview and learning objectives
- Part 1: CAP theorem, consistency patterns, load balancing
- Part 2: Kafka, RabbitMQ, Redis Streams comparison
- Part 3: Redis, Memcached, CDN strategies
- Part 4: Prometheus, Grafana, APM tools
- Code examples in multiple languages
- Real-world case studies and benchmarks
- Interactive exercises and assignments

#### Example 3: Developer Documentation Suite
**Prompt:**
```
Create a complete developer documentation suite for a GraphQL API serving a social media application. Include API reference, getting started guide, authentication setup, rate limiting explanation, schema evolution guide, and best practices for client implementations. Make it suitable for both internal developers and external API consumers.
```

**Expected Output:**
- Quick start guide with authentication flow
- Complete schema documentation with examples
- Query optimization and best practices
- Rate limiting and pagination strategies
- Error handling and status codes
- SDK examples in multiple languages
- Testing and debugging techniques
- Schema versioning and migration guides
- Performance monitoring and analytics

---

## ChatGPT - Programming & Problem Solving

### Basic Level CSE Prompts

#### Example 1: Algorithm Implementation
**Prompt:**
```
Write a Python function to implement quicksort algorithm.
```

**Expected Output:**
- Clean, well-commented quicksort implementation
- Proper handling of edge cases
- Time and space complexity explanation
- Example usage with test cases

#### Example 2: Database Query
**Prompt:**
```
Write a SQL query to find the top 5 customers by total order value.
```

**Expected Output:**
- Correct SQL query with JOINs and aggregation
- Proper ordering and limiting
- Comments explaining the logic
- Sample data structure assumptions

#### Example 3: Web Development Task
**Prompt:**
```
Create a simple HTML form with validation using JavaScript.
```

**Expected Output:**
- HTML form structure with appropriate inputs
- JavaScript validation functions
- Error message handling
- CSS styling for better UX

### Medium Level CSE Prompts

#### Example 1: System Design Implementation
**Prompt:**
```
Design and implement a distributed rate limiting system using Redis and Python. The system should support multiple rate limiting strategies (fixed window, sliding window, token bucket), handle distributed scenarios across multiple application instances, and provide monitoring capabilities. Include error handling, fallback mechanisms, and configuration management.
```

**Expected Output:**
- Complete Python class architecture
- Redis-based distributed storage implementation
- Multiple rate limiting algorithm implementations
- Configuration management system
- Monitoring and metrics collection
- Error handling and circuit breaker patterns
- Unit tests and integration tests
- Docker compose setup for testing
- Performance benchmarking code

#### Example 2: Full-Stack Application Architecture
**Prompt:**
```
Build a real-time collaborative code editor similar to VSCode Live Share. Design the system architecture, implement the backend WebSocket server using Node.js, create the frontend using React, handle operational transforms for concurrent editing, implement user authentication and room management, and add syntax highlighting. Include deployment configuration and scaling considerations.
```

**Expected Output:**
- System architecture diagram and explanation
- WebSocket server with room management
- Operational Transform algorithm implementation
- React frontend with CodeMirror integration
- JWT-based authentication system
- Real-time synchronization protocols
- Conflict resolution mechanisms
- Database schema and API design
- Docker containerization
- Kubernetes deployment manifests
- Load testing and performance optimization

#### Example 3: Machine Learning Pipeline
**Prompt:**
```
Create a complete MLOps pipeline for a image classification model using TensorFlow, MLflow, and Apache Airflow. Include data ingestion from multiple sources, automated feature engineering, model training with hyperparameter tuning, model validation and testing, deployment to production using Kubernetes, monitoring and alerting, and automated retraining triggers. Implement A/B testing capabilities for model comparison.
```

**Expected Output:**
- Airflow DAG for complete pipeline
- TensorFlow model architecture and training code
- MLflow experiment tracking and model registry
- Feature engineering pipeline with data validation
- Hyperparameter optimization using Optuna
- Model serving API with FastAPI
- Kubernetes deployment with auto-scaling
- Monitoring dashboard with Prometheus/Grafana
- A/B testing framework implementation
- Data drift detection and alerting
- Automated retraining mechanisms

---

## Gemini - Multimodal Technical Analysis

### Basic Level CSE Prompts

#### Example 1: Code Screenshot Analysis
**Prompt:** (With code screenshot upload)
```
Analyze this code screenshot and explain what the function does.
```

**Expected Output:**
- Code functionality explanation
- Input/output parameter analysis
- Algorithm or logic description
- Potential improvements or issues
- Language and framework identification

#### Example 2: System Architecture Diagram Review
**Prompt:** (With architecture diagram upload)
```
Explain the components and data flow in this system architecture diagram.
```

**Expected Output:**
- Component identification and roles
- Data flow path explanation
- Integration points analysis
- Potential bottlenecks identification
- Architecture pattern recognition

#### Example 3: Database Schema Analysis
**Prompt:** (With ER diagram upload)
```
Review this database schema and identify the relationships between tables.
```

**Expected Output:**
- Table structure analysis
- Relationship type identification
- Foreign key constraints explanation
- Normalization level assessment
- Potential query optimization opportunities

### Medium Level CSE Prompts

#### Example 1: Complex System Design Review
**Prompt:** (With multiple architecture diagrams and code snippets)
```
Analyze these microservices architecture diagrams along with the accompanying code samples. Evaluate the system design for scalability, fault tolerance, and performance. Identify potential single points of failure, suggest improvements for service communication patterns, and recommend monitoring strategies. Compare this design with industry best practices.
```

**Expected Output:**
- Comprehensive architecture assessment
- Scalability bottleneck identification
- Fault tolerance gap analysis
- Performance optimization recommendations
- Service communication pattern evaluation
- Monitoring and observability strategy
- Security vulnerability assessment
- Cost optimization suggestions
- Migration path recommendations

#### Example 2: Multi-Modal Code Quality Assessment
**Prompt:** (With code files, performance graphs, and test coverage reports)
```
Perform a comprehensive code quality assessment using these source code files, performance benchmarking graphs, and test coverage reports. Analyze code maintainability, identify performance bottlenecks from the graphs, assess test coverage adequacy, and provide prioritized recommendations for improving overall software quality.
```

**Expected Output:**
- Code quality metrics analysis
- Performance bottleneck root cause analysis
- Test coverage gap identification
- Code maintainability assessment
- Technical debt quantification
- Refactoring recommendations with priorities
- Performance optimization strategies
- Testing strategy improvements
- CI/CD pipeline enhancements

#### Example 3: Infrastructure and Application Integration Analysis
**Prompt:** (With Kubernetes YAML files, monitoring dashboards, and application logs)
```
Analyze the Kubernetes deployment configurations, monitoring dashboard screenshots, and application log samples to assess the overall health and optimization opportunities of this containerized application. Focus on resource utilization, scaling behavior, error patterns, and infrastructure cost optimization.
```

**Expected Output:**
- Kubernetes configuration optimization
- Resource utilization efficiency analysis
- Auto-scaling behavior assessment
- Error pattern identification and solutions
- Cost optimization recommendations
- Security configuration review
- Monitoring and alerting improvements
- Performance tuning suggestions
- Disaster recovery preparedness assessment

---

## Claude - System Design & Architecture

### Basic Level CSE Prompts

#### Example 1: Algorithm Explanation
**Prompt:**
```
Explain the difference between BFS and DFS algorithms with examples.
```

**Expected Output:**
- Clear conceptual explanation of both algorithms
- Step-by-step traversal examples
- Time and space complexity comparison
- Use case scenarios for each
- Implementation pseudocode

#### Example 2: Design Pattern Application
**Prompt:**
```
How would you apply the Observer pattern in a web application?
```

**Expected Output:**
- Observer pattern explanation
- Web application context examples
- Implementation approach
- Benefits and trade-offs
- Alternative patterns comparison

#### Example 3: Database Design Question
**Prompt:**
```
Design a database schema for a library management system.
```

**Expected Output:**
- Entity identification (Books, Users, Loans)
- Table structure with relationships
- Primary and foreign key definitions
- Normalization considerations
- Basic query examples

### Medium Level CSE Prompts

#### Example 1: Large-Scale System Architecture
**Prompt:**
```
Design a scalable architecture for a video streaming platform like Netflix that serves 200 million users globally. Address content delivery, user authentication, recommendation systems, video encoding and storage, real-time analytics, fault tolerance, and cost optimization. Consider geographic distribution, peak load handling, and content personalization at scale.
```

**Expected Output:**
- High-level architecture with component breakdown
- CDN strategy and geographic distribution
- Video processing and encoding pipeline
- Real-time and batch analytics architecture
- Recommendation system design and ML pipeline
- Database sharding and replication strategies
- Caching layers and content optimization
- Load balancing and auto-scaling mechanisms
- Fault tolerance and disaster recovery plans
- Cost optimization strategies and resource management
- Security and content protection measures

#### Example 2: Distributed System Design Challenge
**Prompt:**
```
Design a distributed chat application system like Discord that supports real-time messaging, voice/video calls, file sharing, and server organization with channels. Handle millions of concurrent users, ensure message ordering and delivery guarantees, implement presence awareness, and design for horizontal scalability. Address consistency challenges, network partitioning, and cross-platform synchronization.
```

**Expected Output:**
- Distributed system architecture design
- Real-time communication protocols (WebSockets, WebRTC)
- Message ordering and consistency guarantees
- Presence and status management system
- File storage and sharing architecture
- Voice/video call infrastructure design
- Database partitioning and sharding strategy
- Conflict resolution and synchronization mechanisms
- Network partition handling (CAP theorem application)
- Cross-platform client synchronization
- Performance optimization and caching strategies
- Security and privacy considerations

#### Example 3: Complex Data Processing System
**Prompt:**
```
Architect a real-time data processing system for a financial trading platform that processes millions of market data points per second, executes algorithmic trades, manages risk in real-time, ensures regulatory compliance, and provides low-latency analytics. Address data consistency, fault tolerance, audit trails, and integration with external market data providers and trading venues.
```

**Expected Output:**
- Stream processing architecture (Kafka, Flink/Storm)
- Low-latency data ingestion and processing pipeline
- Real-time risk management and circuit breaker systems
- Algorithmic trading execution engine design
- Market data normalization and distribution
- Regulatory compliance and audit trail systems
- Database design for high-frequency transactions
- Event sourcing and CQRS pattern implementation
- Disaster recovery and business continuity planning
- Performance monitoring and SLA management
- Security and data protection measures
- Integration patterns with external systems

---

## CSE-Specific Prompting Best Practices

### Technical Precision Guidelines

#### For Programming Tasks:
- Specify programming language and version
- Include performance requirements
- Mention testing and documentation needs
- Define error handling expectations

#### For System Design:
- Provide scale requirements (users, data, throughput)
- Specify availability and consistency needs
- Include budget and technology constraints
- Define security and compliance requirements

#### For Algorithm Questions:
- Mention time/space complexity requirements
- Specify input constraints and edge cases
- Include optimization goals
- Request complexity analysis

### CSE Domain Considerations

#### Software Engineering Context:
```
Design a [system/application] that handles [scale] with requirements for [performance/availability/consistency]. Consider [constraints] and integrate with [existing systems]. Provide [documentation/testing/deployment] strategies.
```

#### Data Structures & Algorithms Context:
```
Implement [algorithm/data structure] optimized for [specific use case] with [complexity requirements]. Handle [edge cases] and provide [analysis/testing/examples].
```

#### System Administration Context:
```
Configure [technology stack] for [environment] supporting [workload characteristics]. Include [monitoring/security/backup] strategies and [automation/scaling] considerations.
```

### Progressive Complexity in CSE

**Basic Level Focus:**
- Single concept or tool
- Straightforward implementation
- Standard algorithms and patterns
- Basic optimization

**Medium Level Focus:**
- Multiple integrated components
- Performance and scalability considerations
- Error handling and edge cases
- Real-world constraints and trade-offs
- Industry best practices and patterns

This guide provides CSE professionals with practical examples that mirror real-world software development, system design, and engineering challenges, demonstrating how different AI tools can accelerate various aspects of computer science and engineering work.
