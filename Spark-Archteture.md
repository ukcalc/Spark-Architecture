# Apache Spark Architecture Diagram

```mermaid
flowchart TD
    subgraph Driver
        A[SparkContext] --> B[DAG Scheduler]
        B --> C[Task Scheduler]
    end

    subgraph ClusterManager
        D[YARN/Mesos/Standalone]
    end

    subgraph WorkerNodes
        E[Executor 1] --> F[Task 1]
        E --> G[Task 2]
        H[Executor 2] --> I[Task 3]
        H --> J[Task 4]
    end

    C -->|Submits Tasks| D
    D -->|Assigns Resources| E
    D -->|Assigns Resources| H
