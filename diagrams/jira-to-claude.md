# Jira to Claude Code Workflow

This diagram shows how to convert Jira issues (stories, tasks, and bugs) into markdown files that Claude Code can consume for development assistance.

```mermaid
flowchart TD
    A[Jira Issues] --> B[Stories]
    A --> C[Tasks]
    A --> D[Bugs]
    
    B --> E[Extract Story Details]
    C --> F[Extract Task Details]
    D --> G[Extract Bug Details]
    
    E --> H[Story Metadata<br/>• ID & Title<br/>• Acceptance Criteria<br/>• User Journey<br/>• Dependencies]
    F --> I[Task Metadata<br/>• ID & Title<br/>• Technical Requirements<br/>• Implementation Notes<br/>• Definition of Done]
    G --> J[Bug Metadata<br/>• ID & Title<br/>• Steps to Reproduce<br/>• Expected vs Actual<br/>• Environment Info]
    
    H --> K[Format as Markdown]
    I --> K
    J --> K
    
    K --> L[Claude Code<br/>Compatible Files]
    
    L --> M[story-JIRA-123.md]
    L --> N[task-JIRA-456.md]
    L --> O[bug-JIRA-789.md]
    
    M --> P[Claude Code Analysis]
    N --> P
    O --> P
    
    P --> Q[Code Generation]
    P --> R[Test Creation]
    P --> S[Documentation]
    P --> T[Implementation Guidance]
    
    Q --> U[Development Workflow]
    R --> U
    S --> U
    T --> U
    
    U --> V[Update Jira Status]
    U --> W[Create PR/Commit]
    U --> X[Run Tests]
    
    style A fill:#9992cc
    style B fill:#36b37e
    style C fill:#ff8b00
    style D fill:#de350b
    style L fill:#fff3e0
    style P fill:#e3f2fd
    style U fill:#e8f5e8
    
    classDef jiraIssue fill:#f0f8ff,stroke:#0052cc,stroke-width:2px
    classDef processing fill:#fff9c4,stroke:#ffa000,stroke-width:2px
    classDef output fill:#e8f5e8,stroke:#388e3c,stroke-width:2px
    
    class B,C,D jiraIssue
    class E,F,G,H,I,J,K processing
    class M,N,O,U,V,W,X output
```

## Conversion Process

### 1. Issue Extraction
- **Stories**: Focus on user value, acceptance criteria, and business context
- **Tasks**: Extract technical requirements and implementation details  
- **Bugs**: Capture reproduction steps, expected behavior, and environment

### 2. Markdown Template Structure

#### Story Template (`story-JIRA-123.md`)
```markdown
# Story: [JIRA-123] Title

## User Story
As a [user type], I want [goal] so that [benefit].

## Acceptance Criteria
- [ ] Criterion 1
- [ ] Criterion 2

## Dependencies
- Related issues
- Prerequisites

## Notes
Additional context from Jira
```

#### Task Template (`task-JIRA-456.md`)
```markdown
# Task: [JIRA-456] Title

## Objective
Technical goal and purpose

## Requirements
- Technical specifications
- Performance criteria
- Security considerations

## Definition of Done
- [ ] Code implemented
- [ ] Tests written
- [ ] Documentation updated
```

#### Bug Template (`bug-JIRA-789.md`)
```markdown
# Bug: [JIRA-789] Title

## Description
Issue summary

## Steps to Reproduce
1. Step one
2. Step two

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- OS, browser, version info
```

### 3. Claude Code Integration
These markdown files serve as context for Claude Code to:
- Understand requirements and constraints
- Generate appropriate code solutions
- Create relevant tests
- Provide implementation guidance
- Update issue status upon completion
