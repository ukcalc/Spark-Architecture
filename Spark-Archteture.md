# Apache Spark Architecture Diagram

**Key Components:**

Driver Program - Runs SparkContext and schedules tasks

Cluster Manager - Manages resources (YARN/Mesos/Kubernetes/Standalone)

Worker Nodes - Run executors that execute tasks

Executors - Perform computations and store data

```mermaid
flowchart TD
    subgraph Driver
        A[SparkContext] --> B[DAG Scheduler]
        B --> C[Task Scheduler]
    end

    subgraph ClusterManager
        D[YARN/Mesos/Kubernetes/Standalone]
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

