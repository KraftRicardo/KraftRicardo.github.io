---
layout: post
title: Master Thesis
subtitle: RSONPath with a touch of DOM
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [Master Thesis, Research, Rust]
# author: Ricardo Kraft
---

[rsonpath-lut][rsonpath-lut-link] is a fork of the original [rsonpath][rsonpath-link] project, developed as part of my master's thesis. This version includes a new lookup table (LUT) implementation, along with all associated benchmarks and additional measurements.

## Master Thesis: _RSONPath with a Touch of DOM_

> **Download the current version of the thesis:**  
> [📄 View on Google Drive][thesis-link]

## Author & Supervision

**Author:** Ricardo Kraft  
**Supervisor:** [Prof. Dr. Jana Giceva][jana-link]  
**Advisor:** [M. Sc. Mateusz Gienieczko][mateusz-link]  
**Institution:** Technical University of Munich, Chair for Database Systems

## Abstract

Efficiently querying large JSON files is a significant challenge due to the trade-offs between preprocessing time,
memory usage, and query speed. In this thesis, we extend the streaming JSON query engine [rsonpath][rsonpath-link] with
a lookup table (LUT) to improve skipping performance. We explain the development and design considerations
behind the LUT, and evaluate its impact across different JSON datasets and query types, comparing it to the original
[rsonpath][rsonpath-link] and a tree-based approach using [serde][serde-link]. Our results show that [rsonpath-lut][rsonpath-lut-link]
achieves notable speedups for queries that skip large portions of the data, particularly when the number of query
repetitions is between 10 and 100. However, in cases without significant skipping opportunities, the LUT introduces
some additional overhead. We conclude that [rsonpath-lut][rsonpath-lut-link] offers a useful trade-off and propose criteria for
choosing between [rsonpath][rsonpath-link] modes based on query and data characteristics. We believe that this modification
could be incorporated as a feature into the [rsonpath][rsonpath-link] project, dedicated to improving the discussed query pattern.

## Associated Projects

| Repository                                                 | Description                                                                         |
| ---------------------------------------------------------- | ----------------------------------------------------------------------------------- |
| [**rsonpath**][rsonpath-link]                              | Original streaming JSON query engine by Mateusz Gienieczko.                         |
| [**rsonpath-lut**][rsonpath-lut-link]                      | My extended version of _rsonpath_ implementing the Lookup Table (LUT) optimization. |
| [**rsonpath-original-measure**][rsonpath-original-measure] | An unmodified version of _rsonpath_ that we used as comparison.                     |
| [**rsonpath-plotting**][rsonpath-plotting-link]            | Python-based visualization and analysis scripts for thesis experiments.             |


[thesis-link]: https://drive.google.com/file/d/1OjDbdqzmnt_9qSnpg0yb2BanD_IoT-YO/view?usp=sharing
[jana-link]: https://www.professoren.tum.de/g/giceva-jana
[mateusz-link]: https://db.in.tum.de/~gienieczko/?lang=de
[rsonpath-link]: https://github.com/rsonquery/rsonpath
[rsonpath-lut-link]: https://github.com/KraftRicardo/rsonpath/tree/ricardo/main
[rsonpath-original-measure]: https://github.com/KraftRicardo/rsonpath/tree/ricardo/rsonpath-original-measure
[rsonpath-plotting-link]: https://github.com/KraftRicardo/rsonpath-plotting
[serde-link]: https://github.com/serde-rs/serde
[latex-template-link]: https://github.com/TUM-Dev/tum-thesis-latex?tab=readme-ov-file