---
title: "FAQs"
excerpt: "Frequently Asked Questions"
sitemap: true
redirect_from: 
  - /FAQs/
  - /FAQs.html
---

<script
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML"
  type="text/javascript">
</script>

## How do I compute the Hamiltonian?

$$ H(x, D_x V(x, t)) = \max_{u \in \mathcal{U}} \min_{d \in \mathcal{D}} D_x V(x, t) ^\top f(x, u,d) $$


This is easiest illustrated as an example. We will discuss a two-player collision avoidance scenario where each agent has dynamics

$$ \dot{\mathbf{x}} = \begin{bmatrix} v \cos \theta \\ v \sin \theta \\ \omega \\ a \end{bmatrix} $$

Now, define the joint dynamics of the system such that player 1 (the ego player) is fixed at the origin facing the positive $x_{rel}$ axis

$$ \dot{\mathbf{x}} = \begin{bmatrix} x_{rel} \\ y_{rel} \\ \theta_{rel} \\ v_{1} \\ v_{2} \end{bmatrix} = \begin{bmatrix} -v_{1} + v_{2}\cos \theta_{rel} + \omega_{1} y_{rel} \\ v_{2}\sin \theta_{rel} - \omega_{1} x_{rel} \\ \omega_{2} - \omega_{1} \\ a_1 \\ a_2 \end{bmatrix}, $$

where $u = [\omega_1, a_1]$ is the ego control and $d = [\omega_2, a_2]$ is the disturbance control. Now, define the vector 

$$ p := \begin{bmatrix} p_1 \\ p_2 \\ p_3 \\ p_4 \\ p_5 \end{bmatrix} = \begin{bmatrix} \frac{\partial V}{\partial x_{rel}} \\ \frac{\partial V}{\partial y_{rel}} \\ \frac{\partial V}{\partial \theta_{rel}} \\ \frac{\partial V}{\partial v_{1}} \\ \frac{\partial V}{\partial v_{2}} \end{bmatrix} $$


Then the Hamiltonian is given by 

$$ \min_{u \in \mathcal{U}_1} \max_{d \in \mathcal{D}} p_1(-v_{1} + v_{2}\cos \theta_{rel} + \omega_{1} y_{rel}) + p_2(v_{2}\sin \theta_{rel} - \omega_{1} x_{rel}) + p_3(\omega_{2} - \omega_{1}) + p_4 a_1 + p_5 a_2 $$


By factoring out the control inputs for each player this can be simplified to:

$$ \min_{u \in \mathcal{U}} \max_{d \in \mathcal{D}}  \omega_{1}(p_1 y_{rel} - p_2 x_{rel} - p_3) \\ + \omega_{2} p_3 + a_1 p_4 + a_2 p_5 + constants. $$

If $u \in [u_{min}, u_{max}]$ where $u_{min} := [\omega_{min}, a_{min}]$ and $u_{max} :=  [\omega_{max}, a_{max}]$ (similarly for $d$) then the Hamiltonian can be computed using the following rules:

- If $p_1 y_{rel} - p_2 x_{rel} - p_3 < 0 $, then $\omega_1 = \omega_{1,max}$, else $\omega_1 = \omega_{1,min}$
- If $p_3 < 0 $, then $\omega_2 = \omega_{2,min}$, else $\omega_2 = \omega_{2,max}$
- If $p_4 < 0 $, then $a_1 = a_{1,max}$, else $a_1 = a_{1,min}$
- If $p_5 < 0 $, then $a_2 = a_{2,min}$, else $a_2 = a_{2,max}$


### Notes

This is an example of a system with *separable* dynamics, meaning that it can be written in the form 
$$ \dot{\mathbf{x}} = f_0(\mathbf{x}) + f_1(\mathbf{x}, u) + f_2(\mathbf{x}, d)$$. In these cases, the optimal control input is equivalent to state-feedback.

In the case that the dynamics are *not* separable, one must consider non-anticipative strategies for the disturbance player. For more details, see section II of [this paper](https://www.cs.ubc.ca/~mitchell/Papers/publishedIEEEtac05.pdf).

 <sup>TL;DR, This gives the disturbance player all of the information of state-feedback control, as well as instantaneous information on the control of the ego player at the current time (but not at any time in the future). This results in a small advantage for the disturbance player that makes the set of unsafe states slightly more conservative for the ego player. </sup>



### References
- [A Time-Dependent Hamilton-Jacobi Formulation of Reachable Sets for Continuous Dynamic Games](https://www.cs.ubc.ca/~mitchell/Papers/publishedIEEEtac05.pdf)
- [A Robust Controlled Backward Reach Tube with (Almost) Analytic Solution for Two Dubins Cars](https://easychair.org/publications/open/Dd8G)

Contributers: Kensuke Nakamura 


<script type="text/javascript">
  var GOOG_FIXURL_LANG = 'en';
  var GOOG_FIXURL_SITE = '{{ site.url }}'
</script>
<script type="text/javascript"
  src="//linkhelp.clients.google.com/tbproxy/lh/wm/fixurl.js">
</script>
