# Agent Development Kit (ADK) for Java - Developer Guide

## Project Overview

The Agent Development Kit (ADK) for Java is an open-source, code-first toolkit for building, evaluating, and deploying sophisticated AI agents with flexibility and control. It provides tight integration with Google Cloud services and allows developers to define agent behavior, orchestration, and tool use directly in Java.

**Key Characteristics:**
- Code-first development approach with fine-grained control
- Pre-built tools and custom function support
- Modular multi-agent system design
- Development UI for testing and debugging agents
- Agent-to-agent (A2A) communication via A2A protocol integration
- Apache 2.0 Licensed

## Key Directories

| Directory | Purpose |
|-----------|---------|
| `core/` | Core ADK library implementation |
| `dev/` | Development UI components |
| `a2a/` | Agent-to-Agent protocol integration |
| `contrib/` | Community contributions |
| `tutorials/` | Learning resources and examples |
| `maven_plugin/` | Maven plugin for ADK |

## Development Setup

### Prerequisites
- Java development environment
- Maven (included via `mvnw`/`mvnw.cmd`)

### Installation (Maven)

Add to your `pom.xml`:
```xml
<dependency>
  <groupId>com.google.adk</groupId>
  <artifactId>google-adk</artifactId>
  <version>0.3.0</version>
</dependency>

<!-- Optional: Development UI -->
<dependency>
    <groupId>com.google.adk</groupId>
    <artifactId>google-adk-dev</artifactId>
    <version>0.3.0</version>
</dependency>
```

### Project Structure
- `pom.xml` - Main Maven configuration
- `mvnw`/`mvnw.cmd` - Maven wrapper for cross-platform builds
- `CONTRIBUTING.md` - Contribution guidelines
- `CHANGELOG.md` - Version history

## Common Commands

### Maven Build Commands
```bash
# Build the project
./mvnw clean install

# Run tests
./mvnw test

# Build without running tests
./mvnw clean install -DskipTests

# Package the project
./mvnw package
```

### Project Resources
- **Documentation**: https://google.github.io/adk-docs
- **Samples**: https://github.com/google/adk-samples
- **Python ADK**: https://github.com/google/adk-python
- **A2A Protocol**: See `a2a/README.md` for setup instructions

## Quick Start Example

```java
import com.google.adk.agents.LlmAgent;
import com.google.adk.tools.GoogleSearchTool;

LlmAgent rootAgent = LlmAgent.builder()
    .name("search_assistant")
    .description("An assistant that can search the web.")
    .model("gemini-2.0-flash")
    .instruction("You are a helpful assistant. Answer user questions using Google Search when needed.")
    .tools(new GoogleSearchTool())
    .build();
```

---
*For more information, refer to README.md and official documentation*
