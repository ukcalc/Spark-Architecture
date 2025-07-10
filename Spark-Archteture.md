# Apache Spark Architecture Diagram

```mermaid
graph TD
    subgraph Driver Node
        D[Driver Program] -->|1. Submits| E[SparkContext]
        E -->|2. Creates| T[DAG Scheduler]
        T -->|3. Splits into| S[Stages]
        S -->|4. Creates| B[Tasks]
    end

    subgraph Cluster Manager
        E -->|5. Requests| CM[Cluster Manager]
        CM -->|6. Allocates| W[Workers]
    end

    subgraph Worker Nodes
        W -->|7. Launches| EX[Executors]
        EX -->|8. Runs| B
        EX -->|9. Caches| RDD[RDDs]
    end

    style D fill:#f9f,stroke:#333
    style E fill:#f9f,stroke:#333
    style CM fill:#bbf,stroke:#333
    style W fill:#9f9,stroke:#333
    style EX fill:#9f9,stroke:#333