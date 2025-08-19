# Jira Issue Creation Workflow

This diagram shows the workflow of using System Design Plans (SDPs) and Proposals with Claude Code and Jira templates to create Jira issues.

```mermaid
flowchart TD
    A[System Design Plans<br/>SDPs] --> C[Claude Code]
    B[Proposals] --> C
    D[Jira Templates] --> C
    
    C --> E{Analyze & Process}
    E --> F[Extract Requirements]
    E --> G[Identify Components]
    E --> H[Map Dependencies]
    
    F --> I[Generate Jira Issues]
    G --> I
    H --> I
    
    I --> J[Epic Creation]
    I --> K[Story Creation]
    I --> L[Task Creation]
    I --> M[Bug/Technical Debt]
    
    J --> N[Jira Project]
    K --> N
    L --> N
    M --> N
    
    N --> O[Sprint Planning]
    N --> P[Backlog Management]
    
    style A fill:#e1f5fe
    style B fill:#e1f5fe
    style C fill:#fff3e0
    style D fill:#f3e5f5
    style N fill:#e8f5e8
    style E fill:#fff9c4
```

## Workflow Steps

1. **Input Sources**: System Design Plans (SDPs) and Proposals provide the technical requirements and business context
2. **Processing**: Claude Code analyzes the input documents along with predefined Jira templates
3. **Analysis Phase**: 
   - Extract functional and non-functional requirements
   - Identify system components and modules
   - Map dependencies and integration points
4. **Issue Generation**: Create appropriate Jira issues based on the analysis:
   - **Epics**: High-level features or initiatives
   - **Stories**: User-facing functionality
   - **Tasks**: Technical implementation work
   - **Bugs/Technical Debt**: Known issues or improvements
5. **Output**: Structured Jira issues ready for sprint planning and backlog management