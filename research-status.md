---
layout: default
---

[back](./)

# Fisher Vector Research Status
Table of Contents:
===================
* [fisher_vector](#fisher_vector)
  * [Additional info](#additional-info)
  * [useful links](#useful-links)
* [TODO List](#todo)
  * [KNN Benchmarks](#knn-benchmark)
* [Hardware](#hardware)
* [Datasets](#datasets)
* [Results So Far](#results-so-far)
  * [Benchmarks](#benchmarks)
    * [erikbern/ann benchmarks](#erikbernann-benchmarks)
      * [NY Times-256-Angular](#2020_0313_nytimes-256-angular-on-jarvis-417-days)
      * [SIFT-128-Euclidean](#2020_0313_sift-128-euclidean-on-ganon-192-days)

# fisher_vector
My code collection for running custom fisher vector methods 
1. __cv_2__ (`c/c++`) based on [VLFeat lib](https://github.com/vlfeat/vlfeat/tree/master) cutting down Mahalanobis distance calculations by running a __knn search__
   * __cv_fer__ (`c/c++`) based on __cv_2__, this code is more recent version
2. __Trajectory set__(`python`) *Fer's* Code based on Dense Trajectories calculation originaly made for Bag Of Words and Fisher Vector comparison. This code includes NN classification.

## Additional info

Fer's __Trajectory set__ is based on [Trajectory Set](https://github.com/Gauffret/TrajectorySet) code, which is an enhanced version of [Improved Trajectories Video Description](http://lear.inrialpes.fr/~wang/improved_trajectories)

## useful links
- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/#emphasis-and-strong-emphasis)
- [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) 
# TODO
- [x] Generate Table Of Contents
- [x] Add `Trajectory Set` (*Fer*): [Github](https://github.com/Gauffret/TrajectorySet)
  - [ ] Debug and run for HMDB51 and UFC50
- [x] Add `cv_2` Code (Dropbox)
- [ ] Add `cv_fer` Code (Dropbox)
  - [ ] Unify `cv_2` and `cv_fer`
- [ ] Calculate results for datasets

### KNN Benchmark

- [x] Re-run benchmarks: [erikbern/ ann benchmarks](https://github.com/erikbern/ann-benchmarks) (`python`)
- [x] Upload KNN Benchmark results :)
- [] Re-run for my data.
- [] Upload result.

# Hardware

| code name | CPU                         | GPU                                       | RAM                                   |   |
|-----------|-----------------------------|-------------------------------------------|---------------------------------------|---|
| JARVIS    | Intel Core i7-5820K @3.3GHz | GeForce GTX 1080 Ti (3584 cores @1582Mhz) | 4x 4GB DIMM-DDR4 Synchronous 2400 MHz |   |
| GANON     | Intel Core i7-8700  @3.2Ghz | GeForce GTX 1070 (1920 cores @1506MHz)    | 2x 8GB DIMM DDR4 Synchronous 2733 MHz (0.4 ns) | |

# Datasets

<!-- Dataset Table -->
|Done| DB NAME  | DATA SIZE        | RESULT SIZE  |Paper| Paper Result(Method)|
|:--:| -------  | -----------:     | -----:       |:----:|-----:|
|[_]| [NUAA](http://parnec.nuaa.edu.cn/xtan/data/nuaaimposterdb.html)| `(Images, 3 formats)` 390-73-56 (MB)| --           |[X Tan, 2010](http://parnec.nuaa.edu.cn/jliu/papers/tan_eccv_10.pdf) |
|[_]|[HMDB51](http://serre-lab.clps.brown.edu/resource/hmdb-a-large-human-motion-database/#Downloads)| `(Videos)` 2.2GB |680 GB  |[Kuehne, 2011](http://cbcl.mit.edu/publications/ps/Kuehne_etal_iccv11.pdf) |<!-- HMDB -->
|[_]| UFC50    | `(Videos)` 3.5GB |      455 GB  |[-](scholar.google.com) |

# Results So Far

## Benchmarks
### [erikbern/ann benchmarks](https://github.com/erikbern/ann-benchmarks)

<!-- ANN Benchmarks Table -->
|DONE       | DB NAME              |DATA SZ  |RESULT SZ | HW    | RUN TIME  |BEST 3 ALG                       |
|:--:       | -------              |-----:   | ------:  |------:| ------:   |----:                            |
|[2020_0306]| nytimes-256-angular  |315.2 MB |135.6 MB  |JARVIS | 4.17 DAYS | hnsw(nmslib), hnswlib, NGT-onng |
|[2020_0305]| sift-128-euclidean   |525.1 MB |127.6 MB  |GANON  | 1.92 DAYS | hnsw(nmslib), hnswlib, pynndescent |
|[ -- ]     |  (_mine_) custom-256-euclidean |-- MB| -- MB | --  | -- DAYS   | --, --, --                      |

<!-- *benchmark results* -->
#### `2020_0313_nytimes-256-angular` on JARVIS (_4.17 days_)
![2020_0313_nytimes-256-angular](/results/img/ann_benchmarks/2020_0313_nytimes-256-angular.png "2020_0313_nytimes-256-angular")
#### `2020_0313_sift-128-euclidean` on GANON (_1.92 days_)
![2020_0313_sift-128-euclidean](/results/img/ann_benchmarks/2020_0313_sift-128-euclidean.png "2020_0313_sift-128-euclidean")

[back](./)
<!-- ## Available code:
- [x] Fer Trajectory set (python)
- [x] Fer Trajectory set (python) -->