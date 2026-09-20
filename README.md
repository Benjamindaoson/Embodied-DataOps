# Embodied-DataOps

**Physical AI Lab entry point for embodied data infrastructure and robot-learning workflows.**

Embodied-DataOps is an active build focused on the operational layer between robots, demonstrations, datasets, training, and evaluation. The repository remains an independent system and is indexed by the [Embodied AI Lab](https://github.com/Benjamindaoson/Embodied-AI-Lab).

> Current status: architecture and implementation are under active development. The capabilities below describe the target system unless a module is explicitly marked implemented and verified.

## Mission

Build a traceable workflow that turns robot and simulation interactions into validated, reusable evidence for VLA training and evaluation.

```text
Robot / Simulator
      ↓
Teleoperation and Data Collection
      ↓
Validation, Synchronization, and Lineage
      ↓
Dataset Versioning and Storage
      ↓
Training / Adaptation
      ↓
Simulation and Real-Robot Evaluation
      ↓
Failure Mining and Data Iteration
```

## System scope

### 1. Dataset pipeline

- episode and trajectory schemas;
- synchronized observations, actions, timestamps, and metadata;
- validation for missing, corrupted, or misaligned samples;
- dataset versioning, lineage, and reproducible splits.

### 2. Robot data collection

- standardized collection sessions;
- device and calibration metadata;
- task, embodiment, environment, and operator records;
- quality checks before an episode enters a training dataset.

### 3. Teleoperation

- leader–follower and remote operation workflows;
- latency and intervention logging;
- safe stop, recovery, and exception handling;
- operator workload as an explicit system metric.

### 4. Simulation

- task and initial-state contracts;
- controlled distribution shifts;
- replayable evaluation scenarios;
- explicit separation between simulation and real-robot evidence.

### 5. Evaluation

- task success and failure taxonomy;
- checkpoint and policy comparisons;
- data-quality and behavior regressions;
- traceable links from metrics to episodes and artifacts.

### 6. VLA training workflow

- dataset selection and frozen split manifests;
- training and adaptation configuration;
- checkpoint registry and evaluation linkage;
- promotion gates from simulation to real-robot testing.

## Intended lab architecture

The broader Physical AI program is designed around a campus hub and distributed robot nodes.

| Planned component | Intended role |
| --- | --- |
| reBot B601-DM ×1 | Central integrated manipulation platform |
| SO-ARM101 ×8 | Distributed demonstration and robot-learning nodes |
| Intel RealSense D405 ×1 | Close-range RGB-D sensing |
| DIGIT ×2 | Tactile sensing for contact-rich manipulation |

This is a planned configuration, not a procurement or deployment claim.

## Engineering principles

- **Evidence before claims** — planned, simulated, and real-robot results are labeled separately.
- **Data lineage by default** — every derived artifact should trace back to source episodes and configuration.
- **Reproducible evaluation** — dataset, checkpoint, task, seed, and environment versions are recorded.
- **Safety boundaries** — remote actions, approvals, stop conditions, and recovery are explicit.
- **Exception-only operations** — reduce continuous onsite supervision while preserving safe human intervention.

## Roadmap

- [ ] Freeze the episode, trajectory, and metadata contracts.
- [ ] Implement local dataset validation and manifest generation.
- [ ] Add object storage and dataset versioning.
- [ ] Integrate teleoperation session capture.
- [ ] Add simulation replay and evaluation harness.
- [ ] Connect VLA training/adaptation runs to dataset and checkpoint lineage.
- [ ] Validate the first real-robot end-to-end workflow.
- [ ] Publish measured results and limitations.

## Portfolio role

Embodied-DataOps remains an independent active repository. It should not be archived or absorbed into the Hub. The Hub provides navigation; this repository owns the implementation and operational contract.
