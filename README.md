# Multistart Search for the Cyclic Cutwidth Minimization Problem <a href="https://doi.org/10.1016/j.cor.2020.105116"><img src="https://upload.wikimedia.org/wikipedia/commons/1/11/DOI_logo.svg" alt="DOI" width="20"/></a>

<!-- Load Material Symbols Outlined for icons -->
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:opsz,wght,FILL,GRAD@20..48,100..700,0..1,-50..200&icon_names=mail" />

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Code](https://img.shields.io/badge/Code-Java%208-orange.svg)]()
[![DOI](https://img.shields.io/badge/DOI-10.1016%2Fj.cor.2020.105116-blue)](https://doi.org/10.1016/j.cor.2020.105116)
[![Zenodo](https://zenodo.org/badge/1125763466.svg)](https://doi.org/10.5281/zenodo.18114802)



## Abstract

The Cyclic Cutwidth Minimization Problem (CCMP) is a Graph Layout Problem that consists of finding an embedding of the vertices of a candidate graph in a host graph, in order to minimize the maximum cut of a host edge. In this case, the host graph is restricted to be a cycle. In this paper, we identify a new lower bound for the problem, and also a property which allows search procedures to drastically reduce the neighborhood size during the search. Additionally, we propose the use of an alternative objective function for min–max optimization problems, never used before in the context of the CCMP. These strategies have been combined within a multistart search procedure for this problem. The obtained method is compared with the state of the art for the CCMP using sets of problem instances previously published. Statistical tests indicate the merit of our proposal.

## Authors

- Sergio Cavero <sup>1,*</sup> <a href="mailto:sergio.cavero@urjc.es" aria-label="Sergio Cavero Email"><img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Email_Shiny_Icon.svg" alt="email" width="20" style="vertical-align:middle;"/></a> <a href="https://orcid.org/0000-0002-5258-5915"><img src="https://upload.wikimedia.org/wikipedia/commons/0/06/ORCID_iD.svg" alt="ORCID" width="20" style="vertical-align:middle;"/></a>
- Eduardo G. Pardo <sup>1</sup> <a href="mailto:eduardo.pardo@urjc.es" aria-label="Eduardo G. Pardo Email"><img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Email_Shiny_Icon.svg" alt="email" width="20" style="vertical-align:middle;"/></a> <a href="https://orcid.org/0000-0002-6247-5269"><img src="https://upload.wikimedia.org/wikipedia/commons/0/06/ORCID_iD.svg" alt="ORCID" width="20" style="vertical-align:middle;"/></a>
- Manuel Laguna <sup>2</sup> <a href="mailto:laguna@colorado.edu" aria-label="Manuel Laguna Email"><img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Email_Shiny_Icon.svg" alt="email" width="20" style="vertical-align:middle;"/></a> <a href="https://orcid.org/0000-0002-8759-5523"><img src="https://upload.wikimedia.org/wikipedia/commons/0/06/ORCID_iD.svg" alt="ORCID" width="20" style="vertical-align:middle;"/></a>
- Abraham Duarte <sup>1</sup> <a href="mailto:abraham.duarte@urjc.es" aria-label="Abraham Duarte Email"><img src="https://upload.wikimedia.org/wikipedia/commons/b/b1/Email_Shiny_Icon.svg" alt="email" width="20" style="vertical-align:middle;"/></a> <a href="https://orcid.org/0000-0002-4532-3124"><img src="https://upload.wikimedia.org/wikipedia/commons/0/06/ORCID_iD.svg" alt="ORCID" width="20" style="vertical-align:middle;"/></a>

### Affiliations

1. Departamento de Informática y Estadística, Universidad Rey Juan Carlos — C. Tulipán, s/n, Móstoles, 28933, Madrid, Spain
2. Leeds School of Business, University of Colorado Boulder — Boulder, CO, USA

<sup>*</sup>Corresponding author.

---

## Table of Contents

- [Repository Structure](#repository-structure)
- [Abstract](#abstract)
- [Authors](#authors)
- [Datasets](#datasets)
- [Code Execution](#code-execution)
- [Requirements](#requirements)
- [Funding](#funding)
- [Citation](#citation)
- [Acknowledgments](#acknowledgments)
- [Contact](#contact)

---

## Repository Structure

```
.
├── instances/          # Problem instances
│   ├── small/         # Small random graphs (16-24 vertices)
│   ├── harwell-boeing/ # Harwell-Boeing graphs (39-685 vertices)
│   └── ... # all instances set
├── code # Executable JAR file
├── LICENSE            # License file
└── README.md          # This file
```

---

## Datasets

The instances are organized in ten different categories inside the `instances` folder, following the benchmark sets from the literature. The complete test set consists of 179 instances grouped into structured graphs with known properties and random graphs.

### Instance Format

Each instance is encoded as a plain text file representing an undirected graph:
- The first line contains: `Nombre del problema: <instance_name>`
- The second line contains three integers: `n n m` where:
  - `n` = number of vertices
  - `m` = number of edges
- Each subsequent line contains two integers `u v` representing an edge between vertex `u` and vertex `v`.
- Vertices are indexed from 1 to n.

**Example (ibm32.mtx.rnd):**
```
Nombre del problema: ibm32.mtx.rnd
32 32 90
18 26
18 16
18 22
...
```

### Dataset Categories

#### 1. Small Instances (`Smallinstances/`)
- **Instances**: 84 random graphs
- **Vertices**: 16-24
- **Edges**: 18-49
- **Description**: Small random graphs used for preliminary testing and validation

#### 2. Harwell-Boeing (`HarwellBoeing/`)
- **Instances**: 38 graphs
- **Vertices**: 39-685
- **Edges**: 46-3720
- **Description**: Real-world graphs from the Harwell-Boeing Sparse Matrix Collection, arising from scientific and engineering problems

#### 3. Complete Split Graphs (`CompleteSplit/`)
- **Instances**: 21 graphs
- **Description**: Structured graphs with a complete subgraph and an independent set
- **Part of**: Regular graphs with known structure

#### 4. Toroidal Mesh (`ToroidalMesh/`)
- **Instances**: 17 graphs
- **Description**: Grid-like structures with wraparound connections forming a torus topology
- **Part of**: Regular graphs with known structure

#### 5. Join of Hypercubes (`JoinHypercubes/`)
- **Instances**: 9 graphs
- **Description**: Graphs formed by joining hypercube structures
- **Part of**: Regular graphs with known structure

#### 6. Cone Graphs (`Cones/`)
- **Instances**: 10 graphs
- **Description**: Graphs formed by connecting all vertices of a base graph to an apex vertex
- **Part of**: Regular graphs with known structure

#### 7. Meshes (`Meshes/`)
- **Instances**: 66 graphs
- **Description**: Two-dimensional grid structures (not included in main experiments as optima are known)

#### 8. Grids (`Grids/`)
- **Instances**: 36 graphs
- **Description**: Rectangular grid graphs (not included in main experiments as optima are known)

#### 9. Cylindrical Mesh (`CylindricalMesh/`)
- **Instances**: 27 graphs
- **Description**: Grid structures with one dimension forming a cycle (not included in main experiments as optima are known)

#### 10. Hypercubes (`Hypercubes/`)
- **Instances**: 9 graphs
- **Description**: n-dimensional hypercube graphs Q₃ through Q₆ (not included in main experiments as optima are known)

#### 11. Complete Bipartite (`CompleteBipartite/`)
- **Instances**: 31 graphs
- **Description**: Complete bipartite graphs K_{m,n} (not included in main experiments as optima are known)

### Experimental Dataset Summary

The main experiments reported in the paper use the following instances:

| Dataset Category | Instances | Vertices Range | Edges Range | Type |
|------------------|-----------|----------------|-------------|------|
| Small | 84 | 16-24 | 18-49 | Random |
| Harwell-Boeing | 38 | 39-685 | 46-3720 | Random/Real-world |
| Complete Split | 21 | 12-500 | varies | Structured |
| Toroidal Mesh | 17 | 16-1000 | varies | Structured |
| Join of Hypercubes | 9 | 16-512 | varies | Structured |
| Cones | 10 | 12-100 | varies | Structured |
| **Total** | **179** | **12-1000** | **18-6225** | **Mixed** |


## Code Execution

The algorithm implementation consists of four executable JAR files: one for the main multistart tabu search algorithm and three for reproducing the preliminary experiments described in Section 4.2 of the paper.

### Directory Structure

```
code/
├── MultistartTS.jar                    # Main algorithm
├── GreedyConstructiveIterations.jar    # Experiment: Table 1
├── GreedyVSRandomConstructive.jar      # Experiment: Table 2
├── LocalSearchStrategies.jar           # Experiment: Table 3
├── readme.txt                          # Execution instructions
└── resources/                          # Sample instances
```

---

### Main Algorithm Execution

**Command:**
```bash
java -jar MultistartTS.jar <folder>
```

**Example:**
```bash
java -jar MultistartTS.jar resources/smallinstances/
```

**Output:** 
- `M-TS-CCMP.xlsx` - Excel file containing:
  - Best cyclic cutwidth value found
  - Computational time
  - Number of iterations performed
  - Solution quality metrics

**Description:** Executes the complete Multistart Tabu Search algorithm with the tuned parameters (TabuTenure = 0.2n, Non-Improving = 0.1n, r_min = 10, r_max = 30) on all instances in the specified folder.

---

### Preliminary Experiments

The following JAR files reproduce the experiments presented in Section 4.2 of the paper.

#### 1. Greedy Constructive Iterations (Table 1)

**Command:**
```bash
java -jar GreedyConstructiveIterations.jar <folder>
```

**Example:**
```bash
java -jar GreedyConstructiveIterations.jar resources/smallinstances/
```

**Output Files:**
- `GreedyConstructiveAfter1iterations.xlsx`
- `GreedyConstructiveAfter5iterations.xlsx`
- `GreedyConstructiveAfter10iterations.xlsx`
- `GreedyConstructiveAfter20iterations.xlsx`
- `GreedyConstructiveAfter30iterations.xlsx`
- `GreedyConstructiveAfter40iterations.xlsx`
- `GreedyConstructiveAfter50iterations.xlsx`

**Description:** Tests the performance of the greedy constructive procedure (Algorithm 1) with different numbers of iterations to determine optimal restart parameters. Results correspond to Table 1 in the paper.

---

#### 2. Greedy vs Random Constructive (Table 2)

**Command:**
```bash
java -jar GreedyVSRandomConstructive.jar <folder>
```

**Example:**
```bash
java -jar GreedyVSRandomConstructive.jar resources/smallinstances/
```

**Output Files:**
- `ConstructiveGreedy1Second.xlsx` - Results using greedy construction
- `ConstructiveRandom1Second.xlsx` - Results using random construction

**Description:** Compares the greedy constructive procedure against a totally random approach with a 1-second time limit. Results correspond to Table 2 in the paper.

---

#### 3. Local Search Strategies (Table 3)

**Command:**
```bash
java -jar LocalSearchStrategies.jar <folder>
```

**Example:**
```bash
java -jar LocalSearchStrategies.jar resources/smallinstances/
```

**Output Files:**
- `LS.xlsx` - Local Search baseline results
- `LS+E.xlsx` - Local Search with Efficient move calculation
- `LS+E+ROI.xlsx` - Local Search with Efficient calculation and Regions Of Interest

**Description:** Evaluates the contribution of the advanced strategies introduced in Section 3:
- **LS**: Basic local search (Section 2.2)
- **LS+E**: Adds efficient move calculation (Section 3.2)
- **LS+E+ROI**: Adds region of interest neighborhood reduction (Section 3.3)

Results correspond to Table 3 in the paper.

---

### Algorithm Configuration

The multistart tabu search algorithm uses the following default parameters (determined in Section 4.2):

| Parameter | Value | Description |
|-----------|-------|-------------|
| **Tabu Tenure** | 0.2 × n | Size of tabu list (where n = number of vertices) |
| **Non-improving iterations** | 0.1 × n | Stopping criterion (min: 6, max: 15) |
| **Minimum restarts** (r_min) | 10 | Minimum number of multistart iterations |
| **Maximum restarts** (r_max) | 30 | Maximum number of multistart iterations |
| **Time limit** (t_max) | Instance-dependent | Maximum execution time |

These parameters were determined through the preliminary experiments described in Section 4.2 of the paper.

---

### Output Format

All output files are generated in Excel format (`.xlsx`) and include:

- **Instance name**: Name of the graph instance
- **Best solution**: Best cyclic cutwidth value found
- **Average**: Average objective function value across runs
- **Deviation (%)**: Percentage deviation from best-known solution
- **CPU Time (s)**: Computational time in seconds
- **#Best**: Number of times the best solution was found
- **Additional metrics**: Depending on the experiment (e.g., Avg. #Cons., Avg. #Sol.)

---

### Batch Execution Example

To run the complete experimental evaluation:

```bash
# Main algorithm on all instance categories
java -jar MultistartTS.jar resources/HarwellBoeing/
java -jar MultistartTS.jar resources/smallinstances/
java -jar MultistartTS.jar resources/CompleteSplit/
java -jar MultistartTS.jar resources/ToroidalMesh/
java -jar MultistartTS.jar resources/JoinHypercubes/
java -jar MultistartTS.jar resources/Cones/

# Run preliminary experiments
java -jar GreedyConstructiveIterations.jar resources/smallinstances/
java -jar GreedyVSRandomConstructive.jar resources/smallinstances/
java -jar LocalSearchStrategies.jar resources/smallinstances/
```

---

## Requirements

- **Java Runtime Environment (JRE) 8 or higher**
- Minimum 2GB RAM (4GB recommended for large instances)
- No additional dependencies required (all libraries included in JAR files)
- Excel-compatible software to view output files (Microsoft Excel, LibreOffice Calc, etc.)

### System Specifications Used in Paper

All experiments reported in the paper were conducted on:
- **Processor**: Intel Core i7-4702MQ CPU @ 2.20 GHz
- **Memory**: 16 GB RAM
- **Operating System**: Not specified (Java cross-platform)
- **Java Version**: Java 8


## Funding

This research was supported by:

- **Ministerio de Ciencia, Innovación y Universidades** - Grant Ref. PGC2018-095322-B-C22
- **Ministerio de Ciencia, Innovación y Universidades** - Grant Ref. FPU19/04098
- **Comunidad de Madrid and European Regional Development Fund** - Grant Ref. P2018/TCS-4566

The funders had no role in study design, data collection and analysis, decision to publish, or preparation of the manuscript.

## Citation

If you use this work in your research, please cite our paper:

### DOI

<https://doi.org/10.1016/j.cor.2020.105116>

### Bibtex

```bibtex
@article{Cavero2021,
  title={Multistart search for the Cyclic Cutwidth Minimization Problem},
  author={Cavero, Sergio and Pardo, Eduardo G. and Laguna, Manuel and Duarte, Abraham},
  journal={Computers \& Operations Research},
  volume={126},
  pages={105116},
  year={2021},
  publisher={Elsevier},
  doi={10.1016/j.cor.2020.105116}
}
```

### APA Format

Cavero, S., Pardo, E. G., Laguna, M., & Duarte, A. (2021). Multistart search for the Cyclic Cutwidth Minimization Problem. *Computers & Operations Research*, *126*, 105116. https://doi.org/10.1016/j.cor.2020.105116

### IEEE Format

S. Cavero, E. G. Pardo, M. Laguna, and A. Duarte, "Multistart search for the Cyclic Cutwidth Minimization Problem," *Computers & Operations Research*, vol. 126, p. 105116, 2021, doi: 10.1016/j.cor.2020.105116.

## Acknowledgments

We would like to thank:
- P. Jain, K. Srivastava, and G. Saran for kindly providing the source code of their Memetic Algorithm for comparative testing
- The reviewers for their valuable feedback and suggestions that improved the quality of this work
- The creators of the Harwell-Boeing Sparse Matrix Collection for providing real-world benchmark instances

## Contact

For questions, issues, or collaborations, please contact:

- **Sergio Cavero** (Corresponding Author): [sergio.cavero@urjc.es](mailto:sergio.cavero@urjc.es)
- **Eduardo G. Pardo**: [eduardo.pardo@urjc.es](mailto:eduardo.pardo@urjc.es)
- **Research Group Website**: Universidad Rey Juan Carlos, Departamento de Informática y Estadística

---

**Keywords:** Cyclic cutwidth, Graph layout problem, Circular embedding, Tabu Search, Multistart search, Metaheuristics, Combinatorial optimization

**Published in:** Computers & Operations Research, Volume 126, February 2021
