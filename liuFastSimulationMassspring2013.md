# Fast simulation of mass-spring systems

## Metadata

* Authors: [[Tiantian Liu]], [[Adam W. Bargteil]], [[James F. O'Brien]], [[Ladislav Kavan]]

* Date: [[11/2013]]

* Tags: #graphics, #simulation, #spring

## Zotero Links

* URL: [https://dl.acm.org/doi/10.1145/2508363.2508406](https://dl.acm.org/doi/10.1145/2508363.2508406)

* DOI: [10.1145/2508363.2508406](https://doi.org/10.1145/2508363.2508406)

* [Local library](zotero://select/items/1_8Q43Q8JA)

* PDF Attachments
	- [Liu 等 - 2013 - Fast simulation of mass-spring systems.pdf](zotero://open-pdf/library/items/Z4FQZTJ4)

[[Liu 等 - 2013 - Fast simulation of mass-spring systems.pdf#page=3]]

* Cite key: liuFastSimulationMassspring2013

## Abstract

We describe a scheme for time integration of mass-spring systems that makes use of a solver based on block coordinate descent. This scheme provides a fast solution for classical linear (Hookean) springs. We express the widely used implicit Euler method as an energy minimization problem and introduce spring directions as auxiliary unknown variables. The system is globally linear in the node positions, and the nonlinear terms involving the directions are strictly local. Because the global linear system does not depend on run-time state, the matrix can be pre-factored, allowing for very fast iterations. Our method converges to the same final result as would be obtained by solving the standard form of implicit Euler using Newton’s method. Although the asymptotic convergence of Newton’s method is faster than ours, the initial ratio of work to error reduction with our method is much faster than Newton’s. For real-time visual applications, where speed and stability are more important than precision, we obtain visually acceptable results at a total cost per timestep that is only a fraction of that required for a single Newton iteration. When higher accuracy is required, our algorithm can be used to compute a good starting point for subsequent Newton’s iteration.


***



Newton's method 的收敛性质很好，但是每一步都需要解一个**随时间变化**的线性系统，这很消耗计算资源。很多方法在运用 Newton's method 时不追求收敛，而是**只做**一步。这篇论文中提到的做implicit euler integration 的方法适用于**较大步长**，引入了 spring directions 作为 **auxiliary variables**，