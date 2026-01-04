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
    '$nOfEvals = 20000' \
    '$seeds = [1:1:30]'
```

#### Plots

On training arenas:
![Avg Q progression](results/nn-depth.txt/best-train-quality.svg)
![Min Q progression](results/nn-depth.txt/best-train-min-q.svg)
![Max Q progression](results/nn-depth.txt/best-train-max-q.svg)

On test arenas:
![Avg Q progression](results/nn-depth.txt/best-test-avg-q.svg)
![Min Q progression](results/nn-depth.txt/best-test-min-q.svg)
![Max Q progression](results/nn-depth.txt/best-test-max-q.svg)

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
    '$nOfEvals = 20000' \
    '$seeds = [1:1:30]'
```

