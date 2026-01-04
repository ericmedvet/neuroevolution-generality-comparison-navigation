# neuroevolution-generality-comparison-navigation
Software artifacts related to a research on what factors impact on the generalization ability of neuroevolution in the case of 2D robot navigation.

## How to reproduce the experiments

### Requirements
- JDK 25

The binary of [JGEA](https://github.com/ericmedvet/jgea), the evolutionary framework these experiments are based on, is already available in this repo.

### Experiment: impact of the depth of the NN
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/nn-depth.txt \
  --expHeadLines \
    '$tFinal = 60' \
    '$nOfEvals = 30000' \
    '$seeds = [1:1:10]'
```

#### Plots

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/nn-depth.txt/best-train-quality.svg)|![Min Q progression](results/nn-depth.txt/best-train-min-q.svg)|![Max Q progression](results/nn-depth.txt/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/nn-depth.txt/best-test-avg-q.svg)|![Min Q progression](results/nn-depth.txt/best-test-min-q.svg)|![Max Q progression](results/nn-depth.txt/best-test-max-q.svg)|


#### Examples (seed 1)

`[]` (no inner layers)
![Train trajectories](results/nn-depth.txt/ga-[]-0.5-01/best-train-trajs.svg)
![Test trajectories](results/nn-depth.txt/ga-[]-0.5-01/best-test-trajs.svg)

`[8]`
![Train trajectories](results/nn-depth.txt/ga-[8]-0.5-01/best-train-trajs.svg)
![Test trajectories](results/nn-depth.txt/ga-[8]-0.5-01/best-test-trajs.svg)

`[8, 8]`
![Train trajectories](<results/nn-depth.txt/ga-[8, 8]-0.5-01/best-train-trajs.svg>)
![Test trajectories](<results/nn-depth.txt/ga-[8, 8]-0.5-01/best-test-trajs.svg>)

`[8, 8, 8]`
![Train trajectories](<results/nn-depth.txt/ga-[8, 8, 8]-0.5-01/best-train-trajs.svg>)
![Test trajectories](<results/nn-depth.txt/ga-[8, 8, 8]-0.5-01/best-test-trajs.svg>)

### Experiment: impact of the width of the NN
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/nn-depth.txt \
  --expHeadLines \
    '$tFinal = 60' \
    '$nOfEvals = 30000' \
    '$seeds = [1:1:10]'
```

#### Plots

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/nn-width.txt/best-train-quality.svg)|![Min Q progression](results/nn-width.txt/best-train-min-q.svg)|![Max Q progression](results/nn-width.txt/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/nn-width.txt/best-test-avg-q.svg)|![Min Q progression](results/nn-width.txt/best-test-min-q.svg)|![Max Q progression](results/nn-width.txt/best-test-max-q.svg)|

#### Examples (seed 1)

`[4]`
![Train trajectories](results/nn-width.txt/ga-[4]-0.5-01/best-train-trajs.svg)
![Test trajectories](results/nn-width.txt/ga-[4]-0.5-01/best-test-trajs.svg)

`[8]`
![Train trajectories](results/nn-width.txt/ga-[8]-0.5-01/best-train-trajs.svg)
![Test trajectories](results/nn-width.txt/ga-[8]-0.5-01/best-test-trajs.svg)

`[16]`
![Train trajectories](results/nn-width.txt/ga-[16]-0.5-01/best-train-trajs.svg)
![Test trajectories](results/nn-width.txt/ga-[16]-0.5-01/best-test-trajs.svg)

`[32]`
![Train trajectories](results/nn-width.txt/ga-[32]-0.5-01/best-train-trajs.svg)
![Test trajectories](results/nn-width.txt/ga-[32]-0.5-01/best-test-trajs.svg)

### Experiment: impact of memory size
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/ds-memory.txt \
  --expHeadLines \
    '$tFinal = 60' \
    '$nOfEvals = 30000' \
    '$seeds = [1:1:10]'
```

#### Plots

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/ds-memory.txt/best-train-quality.svg)|![Min Q progression](results/ds-memory.txt/best-train-min-q.svg)|![Max Q progression](results/ds-memory.txt/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/ds-memory.txt/best-test-avg-q.svg)|![Min Q progression](results/ds-memory.txt/best-test-min-q.svg)|![Max Q progression](results/ds-memory.txt/best-test-max-q.svg)|

#### Examples (seed 1)

0.1
![Train trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-0.1-01/best-train-trajs.svg>)
![Test trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-0.1-01/best-test-trajs.svg>)

0.5
![Train trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-0.5-01/best-train-trajs.svg>)
![Test trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-0.5-01/best-test-trajs.svg>)

1
![Train trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-1-01/best-train-trajs.svg>)
![Test trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-1-01/best-test-trajs.svg>)

2
![Train trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-2-01/best-train-trajs.svg>)
![Test trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-2-01/best-test-trajs.svg>)

5
![Train trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-5-01/best-train-trajs.svg>)
![Test trajectories](<results/ds-memory.txt/ga-[8, 8, 8]-5-01/best-test-trajs.svg>)

### Experiment: impact of mutation sigma
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/mut-sigma.txt \
  --expHeadLines \
    '$tFinal = 60' \
    '$nOfEvals = 40000' \
    '$seeds = [1:1:10]'
```

#### Plots

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/mut-sigma.txt/best-train-quality.svg)|![Min Q progression](results/mut-sigma.txt/best-train-min-q.svg)|![Max Q progression](results/mut-sigma.txt/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/mut-sigma.txt/best-test-avg-q.svg)|![Min Q progression](results/mut-sigma.txt/best-test-min-q.svg)|![Max Q progression](results/mut-sigma.txt/best-test-max-q.svg)|

#### Examples (seed 1)

0.05
![Train trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.05-01/best-train-trajs.svg>)
![Test trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.05-01/best-test-trajs.svg>)

0.10
![Train trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.10-01/best-train-trajs.svg>)
![Test trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.10-01/best-test-trajs.svg>)

0.20
![Train trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.20-01/best-train-trajs.svg>)
![Test trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.20-01/best-test-trajs.svg>)

0.35
![Train trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.35-01/best-train-trajs.svg>)
![Test trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.35-01/best-test-trajs.svg>)

0.50
![Train trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.50-01/best-train-trajs.svg>)
![Test trajectories](<results/mut-sigma.txt/ga-[8, 8, 8]-0.5 sm=0.50-01/best-test-trajs.svg>)

