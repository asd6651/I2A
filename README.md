# I2A
# I2A + DQN PCB Routing

```mermaid
flowchart TD
  A[Start] --> B[Load PCB Board]
  B --> C[Extract Netlist]
  C --> D[Initialize I2A Agent]
  D --> E[Build Net Order (Actor)]
  E --> F[Predict Routing Parameters]
  F --> G[Run Routing Attempt]
  G --> H{Routing Successful?}
  H -->|Yes| I[Calculate Reward]
  H -->|No| J[Rip-up & Retry]
  I --> K[Backpropagate Reward]
  J --> K
  K --> L[Update Model Training]
  L --> M{Converged?}
  M -->|Yes| N[Done]
  M -->|No| E
```

