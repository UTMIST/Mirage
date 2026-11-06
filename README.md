# Mirage
### Minimally-modified Instances Rendered for AV Gauging and Evaluation

**Evaluating autonomous vehicle robustness through realistic, minimally modified counterfactual driving scenarios.**

Mirage is an open-source framework for generating physically plausible counterfactual driving scenarios from real-world autonomous vehicle datasets. By making controlled modifications to agent trajectories and reconstructing corresponding LiDAR scenes, we aim to evaluate how perception and prediction models respond as driving scenarios gradually deviate from their original conditions.

## Problem

Autonomous driving systems are increasingly capable of handling common traffic situations, but their reliability in rare and unexpected circumstances remains a significant challenge.

Real-world driving failures often arise from small deviations in otherwise familiar scenarios. A pedestrian may step slightly further into the road, a cyclist may suddenly change direction, or another vehicle may merge a second earlier than expected.

Existing adversarial approaches often focus on generating worst-case scenarios that cause collisions or planner failures. However, understanding how gracefully autonomous vehicle models degrade as scenarios progressively change is equally important.

Mirage addresses this gap by generating minimally modified, physically plausible counterfactual scenarios grounded in real-world driving data. This enables systematic evaluation of autonomous vehicle robustness across a continuous range of perturbation magnitudes.

## Approach

Mirage implements a four-stage pipeline:

1. **Scenario Extraction:** Extract and preprocess real-world driving scenarios from public autonomous driving datasets, including nuScenes, Argoverse 2, and Waymo Open Dataset.

2. **Counterfactual Scenario Generation:** Modify agent trajectories using physically plausible motion constraints and trajectory modelling techniques, including kinematic bicycle models and learned traffic priors.

3. **LiDAR Scene Reconstruction:** Reconstruct modified driving scenarios as 3D LiDAR point clouds using tools such as Open3D, ensuring that sensor-level representations reflect the modified agent positions.

4. **Model Evaluation and Benchmarking:** Evaluate open-source autonomous vehicle perception and prediction models across progressively increasing perturbation magnitudes. Compare model performance between original and counterfactual scenarios to quantify robustness.

**Core technologies:**
- Python, NumPy, SciPy
- PyTorch and PyTorch Geometric
- Open3D and OpenCV
- nuScenes devkit
- Docker

## Results

*Project currently in development.*

Our target deliverables include:

- 500 generated counterfactual driving scenarios, each paired with its original scenario.
- A trajectory perturbation module supporting controllable modification magnitudes.
- A LiDAR point-cloud scene editing and reconstruction pipeline.
- An evaluation harness for perception, detection, tracking, and trajectory prediction models.
- A benchmark analysis examining prediction error, criticality rates, distance, and time-to-collision (TTC).

Final performance metrics and experimental findings will be added as the project progresses.

## UTMIST Metadata

- **Team:** Mirage | Autonomous Driving & ML Research
- **Term:** Fall 2026 – Winter 2027
- **Type:** Research
- **Status:** Exploring / In Progress
- **Timeline:** 2 semesters (6–8 months)
- **Weekly Commitment:** 3–5 hours per developer

### Research Areas
- Counterfactual scenario generation
- Autonomous vehicle perception and prediction
- Trajectory and motion modelling
- 3D LiDAR point-cloud processing
- Robustness evaluation and benchmarking

---

## Getting Started

This project is built on the [UTMIST ML Seed](https://github.com/UTMIST/utmist-ml-seed).

### Installation

Clone the repository:

```bash
git clone https://github.com/UTMIST/Mirage.git
cd Mirage
```

Set up the development environment:

```bash
conda env create -f environment.yml
conda activate mirage
```

Alternatively, install dependencies using pip:

```bash
pip install -r requirements.txt
```

### Project Documentation

Full documentation and development guidelines are available in [`docs/`](docs/README.md):

- [Installation and Setup](docs/setup/installation.md)
- [Usage and Commands](docs/usage/commands.md)
- [Development Workflows](docs/README.md#documentation)
- [Contributing Guidelines](docs/contributing/guidelines.md)

### Datasets

Mirage is designed to work with publicly available autonomous driving datasets:

- [nuScenes](https://www.nuscenes.org/)
- [Argoverse 2](https://www.argoverse.org/av2.html)
- [Waymo Open Dataset](https://waymo.com/open/)

Dataset access, licensing, and usage restrictions must be followed independently.

## License

This repository currently uses the [MIT License](LICENSE).

See the license and individual dataset terms before using, modifying, or redistributing project materials.
