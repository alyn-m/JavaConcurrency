```markdown
# Java Thread Internal Working

```mermaid
flowchart TB

    A[Java Application Code] --> B[new Thread()]

    B --> C[Java Thread Object Created<br/>State = NEW]

    C --> D[start() called]

    D --> E[JVM: Thread.start0() <br/>(Native Method)]

    E --> F[OS Kernel Creates Native Thread]

    F --> G[Native OS Thread Allocated]
    G --> G1[Thread ID]
    G --> G2[Thread Stack Memory]
    G --> G3[Thread Local Storage]

    G --> H[JVM Maps<br/>Java Thread ↔ OS Thread<br/>(1:1 Model)]

    H --> I[Thread State = RUNNABLE]

    I --> J[OS Scheduler]

    J --> K[CPU Core Executes Thread]

    K --> L[JIT Compiled Machine Code]

    L --> M[Thread.run() Execution]

    M --> N[User Code / Runnable / Lambda]

    N --> O[Method Calls Pushed on Thread Stack]

    O --> P[JVM Thread Stack]
    P --> P1[Stack Frame 1]
    P --> P2[Stack Frame 2]
    P --> P3[Local Variables]
    P --> P4[Operand Stack]

    N --> Q[Thread Completes run()]

    Q --> R[OS Thread Exits]

    R --> S[JVM Marks Thread TERMINATED]

    S --> T[Stack Memory Released]
