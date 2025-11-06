---
layout: post
title: Master Thesis
subtitle: M.Sc. Informatics
# cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/Master-Thesis/database.png
share-img: /assets/img/Master-Thesis/database.png
tags: [Master Thesis, Research, Rust]
# author: Ricardo Kraft
---


In my master thesis written in Rust, I conducted research to optimize the already fast query engine [**rsonpath**][rsonpath-link] for JSON files. By introducing elements of **DOM (Document Object Model)** to it, I achieved faster query performance — at the cost of only a small amount of memory and preprocessing time (paid once at startup) for a newly designed data structure I call the **lookup table (LUT)**.

## RSONPath with a Touch of DOM

> **Download the current version of the thesis:**  
> [📄 View on Google Drive][thesis-link]

**Author:** Ricardo Kraft  
**Supervisor:** [Prof. Dr. Jana Giceva][jana-link]  
**Advisor:** [M. Sc. Mateusz Gienieczko][mateusz-link]  
**Institution:** Technical University of Munich, Chair for Database Systems

## 📘 Abstract

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

## 📊 Example

![Editor and Game Windows](/assets/img/Master-Thesis/bestbuy_large_record_(1GB)_query_20.png)

The image above compares query speeds (repeated 0–100 times) across four algorithms, for a 1 GB JSON file and the query: _$.products[2].shipping[*]_

- [serde][serde-link] (blue): Starts at 12.5 s since the DOM must be built once for the first query - consuming about 2–8× more space than the original JSON. Subsequent queries are fast due to the pre-built structure.
- [rsonpath][rsonpath-link] (red): No building step or extra space, making it lightweight but slower for repeated queries.
- [rsonpath-lut][rsonpath-lut-link] (orange & green): Adds minimal preprocessing (a few MB and milliseconds) to significantly accelerate repeated queries, staying competitive with SERDE until around 245 repetitions.

## 🧩 Repositories
Aside from many sources, there are four repositories associated with this thesis. Three mainly edited or created directly by me and the original [rsonpath][rsonpath-link] project.
The core repository, [rsonpath-lut][rsonpath-lut-link] implements the LUT and other optimizations along with all related benchmarks and analysis scripts.


| Repository                                                 | Description                                                             |
| ---------------------------------------------------------- | ----------------------------------------------------------------------- |
| [**rsonpath-lut**][rsonpath-lut-link]                      | My extended version of _rsonpath_ implementing the LUT optimization.    |
| [**rsonpath-original-measure**][rsonpath-original-measure] | An unmodified version of _rsonpath_ that we used as comparison.         |
| [**rsonpath-plotting**][rsonpath-plotting-link]            | Python-based visualization and analysis scripts for thesis experiments. |
| [**rsonpath**][rsonpath-link]                              | Original streaming JSON query engine.                                   |



[thesis-link]: https://drive.google.com/file/d/1OjDbdqzmnt_9qSnpg0yb2BanD_IoT-YO/view?usp=sharing
[jana-link]: https://www.professoren.tum.de/g/giceva-jana
[mateusz-link]: https://db.in.tum.de/~gienieczko/?lang=de
[rsonpath-link]: https://github.com/rsonquery/rsonpath
[rsonpath-lut-link]: https://github.com/KraftRicardo/rsonpath/tree/ricardo/main
[rsonpath-original-measure]: https://github.com/KraftRicardo/rsonpath/tree/ricardo/rsonpath-original-measure
[rsonpath-plotting-link]: https://github.com/KraftRicardo/rsonpath-plotting
[serde-link]: https://github.com/serde-rs/serde
[latex-template-link]: https://github.com/TUM-Dev/tum-thesis-latex?tab=readme-ov-file