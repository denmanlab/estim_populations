# estim_populations

### Neural population dynamics of direct electrical stimulation of neocortex  
*(Hickman et al., 2025 — submitted to Neuron on 10/29/2025)*  
**Preprint:** [https://www.biorxiv.org/content/10.1101/2025.10.28.685195v1](https://www.biorxiv.org/content/10.1101/2025.10.28.685195v1)

This repository contains all analysis code and figure-generation scripts used in the manuscript **"Neural population dynamics of direct electrical stimulation of neocortex."**  
Analyses were performed in Python using Jupyter notebooks. Each notebook reproduces one or more main and corresponding supplementary figures from the manuscript.

### Repository Structure

- **`figure1.ipynb`** — Orthogonal multi-Neuropixels recordings for spatial measurement of electrical stimulation in awake mice  
  - Describes the setup, stimulation parameters, and anatomical registration to CCF coordinates.

- **`figure2.ipynb`** — Evoked potential spatial extent increases sub-linearly with amplitude  
  - Analyses evaluating the spatial properties of the evoked potential and a null model using Gauss’ equations.

- **`figure3.ipynb`** — Anisotropic volumetric profile of the induced electrical field  
  - Code to assess the 3-D shape of the evoked potential with anatomical registration.

- **`figure4_figure5_figure6.ipynb`** — Analyses of direct neuronal responses to stimulation  
  - **Figure 4:** Evoked spiking is sparse and increases in density with amplitude  
  - **Figure 5:** Stimulation amplitude and polarity tune unit-specific recruitment  
  - **Figure 6:** Cell type influences activation distance and response probability with amplitude dependence.

- **`figure7.ipynb`** — Single-pulse electrical stimulation leads to extensive circuit responses  
  - Evaluates the network-level response to microstimulation.

- **`figure8.ipynb`** — Single pulses of electrical stimulation are weakly detected, similar to low-contrast visual stimuli  
  - Compares detection performance for visual and electrical stimuli.

- **`requirements.txt`** — Contains key Python package and version information used in the analyses.

- **`recordings/`** — Contains subfolders for each recording, named by mouse ID and date.  
  - Each folder includes recording-specific data.  
  - Raw data and metadata are stored in NWB files hosted on **DANDI (ID: DANDI:000774)**.  
  - To run analyses, download the NWBs and place them in the corresponding subfolders.

- **`jlh_ephys/`** — Custom wrappers and analysis tools used across notebooks.  
  - Includes helper functions for loading NWBs, handling recording metadata, and performing common analyses.

- **`intermediates/`** — Cached intermediate data (NumPy arrays, DataFrames, etc.) used to reduce runtime.  
  - Some intermediates are generated from raw binary files not included in the NWBs but are available upon request.


---

## Data Access

The electrophysiological datasets used here are publicly available on **[DANDI](https://dandiarchive.org/)** (ID: **DANDI:000774**).  
To reproduce analyses:

1. Download the corresponding **NWB** files from DANDI.  
2. Place them in their appropriate subfolder in the `recordings/` directory, named by `mouse_id` and recording date.

---

## Environment Setup

The repository is intended to be fully reproducible and will eventually include a Docker configuration.  
In the interim, key Python package version information is provided in `requirements.txt`.

## To run data

### Running the Code

1. **Download/clone this repository:**
2. **Install dependencies** (as described above).
3. **Download and organize NWBs** from DANDI as described in the *Data Access* section.
4. **Run the notebooks:**
   - Open any `Figure*.ipynb` notebook in Jupyter or VS Code.
   - Execute all cells to reproduce analyses and figures.  
   - Each notebook is self-contained and accesses data locally through the `recordings/` and `intermediates/` folders.

For questions about code and data, please contact: Jordan Hickman (jordan.hickman@cuanschutz.edu)


