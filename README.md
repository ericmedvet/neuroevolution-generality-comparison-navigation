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

### Experiment: impact of EA
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/ea.txt \
  --expHeadLines \
    '$tFinal = 60' \
    '$nOfEvals = 40000' \
    '$seeds = [1:1:10]'
```

#### Plots

##### Short (40k evaluations)

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/ea.txt/short/best-train-quality.svg)|![Min Q progression](results/ea.txt/short/best-train-min-q.svg)|![Max Q progression](results/ea.txt/short/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/ea.txt/short/best-test-avg-q.svg)|![Min Q progression](results/ea.txt/short/best-test-min-q.svg)|![Max Q progression](results/ea.txt/short/best-test-max-q.svg)|

Final best avg Q on test:
![Avg Q progression](results/ea.txt/short/final-best-test-avg-q.svg)

Final min (in the population) avg Q on test:
![Avg Q progression](results/ea.txt/short/final-min-test-avg-q.svg)

##### Long (200k evaluations)

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/ea.txt/long/best-train-quality.svg)|![Min Q progression](results/ea.txt/long/best-train-min-q.svg)|![Max Q progression](results/ea.txt/long/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/ea.txt/long/best-test-avg-q.svg)|![Min Q progression](results/ea.txt/long/best-test-min-q.svg)|![Max Q progression](results/ea.txt/long/best-test-max-q.svg)|

Final best avg Q on test:
![Avg Q progression](results/ea.txt/long/final-best-test-avg-q.svg)

Final min (in the population) avg Q on test:
![Avg Q progression](results/ea.txt/long/final-min-test-avg-q.svg)

#### Examples (200k evaluations)

##### GA

![Train trajectories](<results/ea.txt/long/ga-[8, 8, 8]-0.5-01/best-train-trajs.svg>)
![Test trajectories](<results/ea.txt/long/ga-[8, 8, 8]-0.5-01/best-test-trajs.svg>)

##### ME with final position descriptors

Descriptors:
1. average (on arenas) of final x of the robot
2. average (on arenas) of final y of the robot

Best:
![Train trajectories](results/ea.txt/long/me.pos-01/best-train-trajs.svg)
![Test trajectories](results/ea.txt/long/me.pos-01/best-test-trajs.svg)

Archive:
![Archive](results/ea.txt/long/me.pos-01/me-archives.svg)

low-low archive individual on training:
![Train trajectories](results/ea.txt/long/me.pos-01/archive-ll-train-trajs.svg)

low-high archive individual on training:
![Train trajectories](results/ea.txt/long/me.pos-01/archive-lh-train-trajs.svg)

high-low archive individual on training:
![Train trajectories](results/ea.txt/long/me.pos-01/archive-hl-train-trajs.svg)

high-high archive individual on training:
![Train trajectories](results/ea.txt/long/me.pos-01/archive-hh-train-trajs.svg)

##### ME with trajectory descriptors

Descriptors:
1. average (on arenas) of trajectory regularity: rate between length of symbolic trajectory w/o repetitions and with repetitions (low = high regularity; high = low regularity)
2. average (on arenas) of gap on right: average during the similation of distance to the closest obstacle on the right

Best:
![Train trajectories](results/ea.txt/long/me.behav-01/best-train-trajs.svg)
![Test trajectories](results/ea.txt/long/me.behav-01/best-test-trajs.svg)

Archive:
![Archive](results/ea.txt/long/me.behav-01/me-archives.svg)

low-low archive individual on training:
![Train trajectories](results/ea.txt/long/me.behav-01/archive-ll-train-trajs.svg)

low-high archive individual on training:
![Train trajectories](results/ea.txt/long/me.behav-01/archive-lh-train-trajs.svg)

high-low archive individual on training:
![Train trajectories](results/ea.txt/long/me.behav-01/archive-hl-train-trajs.svg)

high-high archive individual on training:
![Train trajectories](results/ea.txt/long/me.behav-01/archive-hh-train-trajs.svg)

### Experiment: impact of training size
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/train-size.txt \
  --expHeadLines \
    '$qFun = ds.e.n.avgD()' \
    '$tFinal = 60' \
    '$nOfEvals = 200000' \
    '$seeds = [1:1:10]'
```

Number of arenas:
- `train`: 6
- `train.l`: 6+2
- `train.xl`: 6+2+2

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/train-size.txt/long-200k/best-train-quality.svg)|![Min Q progression](results/train-size.txt/long-200k/best-train-min-q.svg)|![Max Q progression](results/train-size.txt/long-200k/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/train-size.txt/long-200k/best-test-avg-q.svg)|![Min Q progression](results/train-size.txt/long-200k/best-test-min-q.svg)|![Max Q progression](results/train-size.txt/long-200k/best-test-max-q.svg)|

Final best avg Q on test:
![Avg Q progression](results/train-size.txt/long-200k/final-best-test-avg-q.svg)

Final min (in the population) avg Q on test:
![Avg Q progression](results/train-size.txt/long-200k/final-min-test-avg-q.svg)

#### Examples
For all the three cases, we show the trajectories on the `train.xl` arenas (and the test ones):

`train`
![Train trajectories](<results/train-size.txt/long-200k/ga-[8, 8, 8]-0.5-01/train/best-train-xl-trajs.svg>)
![Test trajectories](<results/train-size.txt/long-200k/ga-[8, 8, 8]-0.5-01/train/best-test-trajs.svg>)

`train.l`
![Train trajectories](<results/train-size.txt/long-200k/ga-[8, 8, 8]-0.5-01/train.l/best-train-xl-trajs.svg>)
![Test trajectories](<results/train-size.txt/long-200k/ga-[8, 8, 8]-0.5-01/train.l/best-test-trajs.svg>)

`train.xl`
![Train trajectories](<results/train-size.txt/long-200k/ga-[8, 8, 8]-0.5-01/train.xl/best-train-xl-trajs.svg>)
![Test trajectories](<results/train-size.txt/long-200k/ga-[8, 8, 8]-0.5-01/train.xl/best-test-trajs.svg>)

### Experiment: impact of brain type
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/brain-type.txt \
  --expHeadLines \
    '$qFun = ds.e.n.avgD()' \
    '$tFinal = 60' \
    '$nOfEvals = 40000' \
    '$seeds = [1:1:10]'
```

On training arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/brain-type.txt/best-train-quality.svg)|![Min Q progression](results/brain-type.txt/best-train-min-q.svg)|![Max Q progression](results/brain-type.txt/best-train-max-q.svg)|

On test arenas:
|Avg Q|Min Q|Max Q|
|-----|-----|-----|
|![Avg Q progression](results/brain-type.txt/best-test-avg-q.svg)|![Min Q progression](results/brain-type.txt/best-test-min-q.svg)|![Max Q progression](results/brain-type.txt/best-test-max-q.svg)|

Final best avg Q on test:
![Avg Q progression](results/brain-type.txt/final-best-test-avg-q.svg)

Final min (in the population) avg Q on test:
![Avg Q progression](results/brain-type.txt/final-min-test-avg-q.svg)

### Experiment: different train/test arenas
```shell
java \
  -jar jgea.jar \
  -nt 16 -nr 4 \
  -f exp-files/progressive.txt \
  --expHeadLines \
    '$tFinal = 60' \
    '$nOfEvals = 40000' \
    '$seeds = [1:1:10]'
```


