---
permalink: /
title: "Reachability Overview"
excerpt: "This is an overview on Hamilton-Jacobi Reachability"
sitemap: true
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

Why Hamilton-Jacobi reachability? Doesn't it suffer from the curse of dimensionality? Why shouldn't I just use a control barrier function? What even *is* Hamilton-Jacobi reachability?

This website is primarily intended to researchers acquire familiarity with HJ computation tools with minimal overhead. This website covers three computation methods: Grid-based methods (HelperOC+Level Set Toolbox, Optimized_dp), Model-based learning (DeepReach), and Model-free learning (ISAACS). Each method comes with its own set of strengths and drawbacks, and this website seeks to guide researchers to the appropriate toolbox to use, and how to use it.

In the [Advanced Topics](https://cmu-intentlab.github.io/ReachabilityComputation/_pages/advanced/) section, the connection between HJ reachability analysis and CBFs is investigated, along with other topics dealing with the application of reachability in human-robot interaction, adaptitve reachable sets and others.

We assume that the reader has some basic familiarity on the theory of HJ reachability, but below are a list of select papers that introduce reachability in the broader context of safety filters, and the necessary theory for HJ reachability.

### Safety Filters
- [The Safety Filter: A Unified View of Safety-Critical Control in Autonomous Systems](https://arxiv.org/abs/2309.05837)<br>
- [Data-Driven Safety Filters: Hamilton-Jacobi Reachability, Control Barrier Functions, and Predictive Methods for Uncertain Systems](https://ieeexplore.ieee.org/abstract/document/10266799)

### Hamilton-Jacobi Reachability Theory
- [Hamilton-Jacobi Reachability: A Brief Overview and Recent Advances](https://arxiv.org/pdf/1709.07523.pdf) <br>
- [A Time-Dependent Hamilton-Jacobi Formulation of Reachable Sets for Continuous Dynamic Games](https://www.cs.ubc.ca/~mitchell/Papers/publishedIEEEtac05.pdf)<br>
- [Reach-Avoid Problems with Time-Varying Dynamics, Targets, and Constraints](https://arxiv.org/abs/1410.6445)



<script type="text/javascript">
  var GOOG_FIXURL_LANG = 'en';
  var GOOG_FIXURL_SITE = '{{ site.url }}'
</script>
<script type="text/javascript"
  src="//linkhelp.clients.google.com/tbproxy/lh/wm/fixurl.js">
</script>
