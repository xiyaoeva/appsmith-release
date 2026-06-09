# Run Query (Action Execution)

## 1) Where the feature is located

```mermaid
graph LR
  A[Run Button\nuseHandleRunClick.ts] --> B[runAction\npluginActionActions.ts]
  B --> C[runActionSaga\nPluginActionSaga.ts]
  C --> D[executePluginActionSaga\nPluginActionSaga.ts]
  D --> E[ActionAPI.executeAction\nActionAPI.tsx]
  E --> F[POST /v1/actions/execute\nActionControllerCE.java]
  F --> G[ActionExecutionSolutionCEImpl.java]
```

## 2) How the feature works

```mermaid
sequenceDiagram
  participant U as User
  participant FE as Frontend
  participant BE as Backend
  participant PX as Plugin Executor

  U->>FE: Click Run Query
  FE->>FE: runActionSaga + evaluateActionParams
  FE->>BE: POST /v1/actions/execute (multipart)
  BE->>BE: parse + permission check + load action/datasource
  BE->>PX: executeParameterizedWithMetricsAndFlags
  PX-->>BE: ActionExecutionResult
  BE-->>FE: response
  FE->>FE: updateActionData + show result/error
```


## Appendix: AI Assistance Details (For This Assignment)

1. Consulted the AI ​​to identify the actual entry point and primary execution path for `Run Query (Action Execution)` within the project codebase, followed by manual verification.
2. Consulted the AI ​​to map out the execution path from the frontend to the backend, followed by manual verification.

