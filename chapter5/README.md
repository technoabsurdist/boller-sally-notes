# Chapter 5

Integration on $\mathbb{R}^n$

The most basic functionality of integration over R is the determination of “area under a curve” which students learn in Calculus. The idea moves in a number of directions, such as volume in $\mathbb{R}^n$, arc length of a curve, flux through a surface, and other applications. 

Differentiation is designed to describe the behavior of a function at a point or in the neighborhood of a point, integration is intended to study the *cumulative properties of a function on a larger domain.* 

****************************************************************************************************The Riemann Integral in One Variable: Definitions****************************************************************************************************

**********************Partition.********************** A partition, denoted as **P,** is a finite collection of points selected from the interval $[a, b]$. 

Imagine you have a ruler (the interval), and you mark some points on this ruler, creating segments. The marks that you paint on the ruler are your partition points. 

Formally, 

**********Def.********** A **********partition********** P of the interval [a, b] is a finite set of points

$$
P = \{a_0, a_1, ..., a_k\}
$$

Such that, 

$$
a = a_0 < a_1 < ... < a_{k-1} < a_k = b
$$

************Mesh.************ This is going to be the length of the largest subinterval created by that partition. A small mesh indicates a fine partition with many closely-spaced points, while a large mesh means the opposite. Mathematically, it’s very simple. You just find the difference between consecutive points and take the maximum. 

<aside>
💡 Why is the *****mesh***** important? Because it’s a measure as to how “refined” our partition is. The more we refine our partition, the more accurate our representation of the area under the curve.

</aside>

$m_i$  ********and $M_i$.** For every subinterval created by our partition, we find two values. 

- $m_i$: The smallest value the function takes on that subinterval —infimum.
- $M_i$: The largest value the function takes on that subinterval

********************Lower Sum $L(f, P)$.** Provides an underestimate over the actual sum, because it calculates the area of a rectangle whose height is the smallest value of the function on that subinterval, and whose width is the size of that subinterval. 

$$
L(f,P) = \sum^k_{i=1} m_i (a_i - a_{i-1})
$$

**********************Upper Sum $U(f, P)$.** Similarly, we compute the area of the rectangle but taking the height to be the largest value of the function on that subinterval. 

$$
U(f,P) = \sum^k_{i=1} M_i (a_i - a_{i-1})
$$

![Screenshot 2023-10-04 at 12.16.16 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_12.16.16_PM.png)

*Solution.* 

We need to show,

 $m(b−a)≤L(f,P)≤U(f,P)≤M(b−a)$

⇒ For each subinterval $[a_i, a_{i+1}]$ of the partition P, given that $m_i$ is the infimum of $f$ on that subinterval, and $M_i$ is its supremum, we can conclude: 

$$
m≤m_i≤M_i≤M
$$

Using the definitions just provided for lower and upper sums, respectively. 

⇒ Multiply every term in the sum for the lower sum by $m$. 

$$
m(b - a) = m\sum^k_{i=1}(a_i - a_{i-1})
$$

Given that $m \leq m_i \forall i$, 

$$
m(b - a) \leq L(f, P)
$$

⇒ Same procedure and argument respectively for upper bound gives you: 

$$
U(f, P) \leq M(b-a)
$$

⇒ Now, for reach subinterval, since $m_i \leq M_i$ we get: 

$$
m_i(a_i - a_{i-1}) \leq M_i(a_i - a_{i-1}) \\ \therefore L(f, P) \leq U(f, P)
$$

**********Def.********** Let $P = \{a_j | j = 0, 1, 2, ..., k\}$ be a partition of [a, b]. A partition $P' = \{a^{'}_j | j = 0, 1, 2, ..., k\}$, where k’ ≥ k, is called a ***********refinement*********** of P if $P \subset P'$. 

Lower and Upper Integrals

**********Def.********** Let $f : [a, b] \rarr \mathbb{R}$ be a bounded function. 

1. **************Lower integral.************** Uses the smallest value of the function in each partition. For each partition P, you take the lowest value of the function within that partition, multiply it by the width and sum these values up. This process gives you a series of sums, called the **********lower sums**********. 
    
    ![Screenshot 2023-10-04 at 12.44.01 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_12.44.01_PM.png)
    
2. ****************Upper integral.**************** This uses the largest value of the function in each partition. You get a series of *upper sums*. 
    
    ![Screenshot 2023-10-04 at 12.44.23 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_12.44.23_PM.png)
    

<aside>
⛰️ Imagine a mountain, and you want to estimate its volume. The ***************lower integral*************** is like filling it with water from the bottom up. The ***********upper integral*********** is like draping a cloth from the top down. The true volume lies somewhere in between, and the trick is to squeeze the solution in between these two methods until reaching one value, which will necessarily be the total volume of the mountain.

</aside>

**********Def.********** ********************************Riemann Integrable.******************************** We say that **f** is *********Riemann integrable********* on [a, b] if lower integral is equal to upper integral, and we denote this common value by $\int^b_af$, which we call the *****************Riemann integral***************** of **f** on [a, b]. 

We often refer to a function that is Riemann integrable as simply ************integrable.************ 

---

********************The Fundamental Theorem of Calculus and Its Consequences********************

The next theorem is often regarded as the most important theorem in integral calculus in one variable. 

********Theorem (Fundamental Theorem of Calculus)********

High-level. We have a function $f$ which is Riemann integrable over [a, b]. Define $F(x)$ as the integral of $f$  from $a$  to $x$. Then, $F(x)$ is the area under the curve of $f$ from $a$ to $x$. 

This theorem is proving that for the function $F(x)$, which represents the accumulated area under the curve of **f** from a starting point to $x$, its derivate at any given point is $f(x)$. 

<aside>
♻️ I.e., if you differentiate this accumulated area function F(x), you get back the original function f(x). This means that the rate of change of the accumulated are at any point $x$ is precisely the value of the function f(x) at that point.

</aside>

Getting closer to a definition, we can define some pseudo-definition looking like:

***********************************If we have an f which is a Riemann integral on*********************************** [a, b]. Let’s define some arbitrary $x \in [a, b]$. 

Then, we can define $F(x) = \int^x_af$. Based on this newly defined F(x), we know that if **f** is continuous at a point $x \in (a, b)$, then $F$ is differentiable at x, and the differentiation of that F gives us the original function at that x (or $F'(x) = f(x)$). 

Now for the actually rigorous definition. 

**********Def.********** Let **f** be Riemann integrable on [a, b]. For $x \in [a, b]$, define $F(x) = \int^x_af.$  If $f$ is continuous at a point $x \in (a, b)$, then $F$ is differentiable at $x$, and $F'(x) = f(x)$. 

**************Proof.************** 

We have a function F(x) defined as the integral of $f$ from a fixed point $a$ to $x$. We want to prove that the derivative of $F(x)$ at any point $x$ is $f(x)$. 

Fix $\epsilon > 0.$  Consider the difference quotient

$$
\frac{F(x+h) - F(x)}{h} = \frac{1}{h}(\int^{x+h}_af - \int^x_af)
$$

Because **f** is continuous at **x**, as **h** becomes very small, the value of **f** over the entire interval [x, x+h] approaches f(x). Therefore, for sufficiently small $h$, the entire function in this interval is trapped between $f(x) - \epsilon$ and $f(x) + \epsilon$, where $\epsilon$ is a tiny positive value. 

⇒ Then, as h → 0, the difference quotient converges to f(x). This proves that ********************************************************************the derivative of F(x) at point x is f(x).******************************************************************** 

---

**************************************Principal Value Integrals************************************** —a way to make sense of integrals over unbounded intervals

So far, we have worked with bounded, real-valued functions defined on a closed, bounded interval on $\mathbb{R}$. For many reasons in mathematics, it is useful and *even necessary to extend the definition of integrals to both **unbounded** **functions** and **unbounded** **intervals**.*

**********Def (Principal Value Integral).********** Suppose that $f : [a, \infty] \rarr \mathbb{R}$ is a bounded function, and suppose further that for all b > a, the function $f$ is integrable on [a, b]. 

The principal value integral,  $\int^{\infty}_af$,  is defined by  $\lim_{b \rarr \infty}\int^b_af$  if this limit exists. 

<aside>
<img src="https://www.notion.so/icons/infinity_gray.svg" alt="https://www.notion.so/icons/infinity_gray.svg" width="40px" /> This is the main concept. Instead of trying to integrate the function over the entire interval $[a, \infty)$, which is obviously problematic since we’re dealing with infinity, we look at the limit of the integrals as the upper bound approaches infinity. If this limit exists, we say that the “Principal Value Integral” of **f** from a to $\infty$ exists. Thea idea of this theorem is to progressively consider larger and larger chunks of this curve and see if these areas converge to a specific value.

</aside>

🪣 A useful water analogy 

Imagine you’re filling a large container that seems to stretch indefinitely upwards with water. However, you notice that the more water you pour, the slower the water level rises. So, you start measuring how much the water level rises for each gallon you pour in. As you pour in more and more water, you realize the increase in water level is getting infinitesimally small, and you can estimate that the container can hold up to that level of water, even if you never truly fill it. 

---

********************The Riemann Integral in Several Variables********************

In developing the theory of integration, we build off the fundamental notion of the volume of a generalized rectangle. 

Single variable: when we did this for single variable, we considered rectangles in $\mathbb{R}$, namely intervals, whose volumes were their lengths. Such an interval formed the base for a rectangle in $\mathbb{R^2}$, whose height was determined by function values on this interval. The *******volume******* of this rectangle was base times height, and the integral of the function was approximated by volumes of such rectangles. 

<aside>
⚠️ Volume is not just an artifacts of 3D space. When we say “volume” in $\mathbb{R}$ (1D space), we’re talking about **length**. When we say “volume” in $\mathbb{R^2}$ (2D space), it means **area**. For each additional dimension, “volume” takes on a broader meaning.

</aside>

Definitions

****************************Definition 1 (Volume of a Generalized Rectangle in $\mathbb{R^n}$).** 

→ This definition is looking at $\mathbb{R^n}$, which is n-dimensional space. Within this space, we’re working with “generalized rectangles.” In a familiar 3-dimensional space, think of this as a box or rectangular prism.

→ A “generalized rectangle” in n-dimensional space is formed by taking the Cartesian product of **n** intervals. Each of these intervals is one-dimensional and bounded. 

**********************Intuition:********************** To compute the volume of this generalized rectangle in n-dimensional space, you need to consider each dimension’s extent (length, width, depth, and so on…). For each dimension *i*, the extent —or size— of the generalized rectangle in that dimension is $b_i - a_i$. 

To find the total volume $v(R)$, you multiply all these extents together. So, for a 3D example, this would be length times width times height. 

**Formally:** Let $R \subset \mathbb{R^n}$ be a generalized rectangle of the form $R = I_1 \times I_2 \times ... \times I_n$, where $I_i$ is a bounded interval (*each representing an interval in one of the n dimensions, where $I_i$ is the interval between $a_i$ and $b_i$, and $a_i$ is the lower bound*) with endpoints $a_i$ and $b_i$ with $a_i \leq b_i$, for each $i = 1, 2, ..., n$. Then the *******volume******* of R in $\mathbb{R^n}$ is

![Screenshot 2023-10-04 at 2.59.31 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_2.59.31_PM.png)

****************************Definition 2.**************************** 

************************Intuition:************************ A partition refers to dividing or breaking up the generalized rectangle R into smaller, *non-overlapping* sub-rectangles. The notation that is going to be presented with the union symbol represents the idea that if you “combine” all of the partitions you get the original rectangle ***R***. 

********************Formally:******************** A **********partition $P$* of a closed generalized rectangle $R \subset \mathbb{R^n}$ is a finite collection $P_1, ..., P_k$ of pairwise disjoint open generalized rectangles contained in R. 

The *****mesh***** of the partition **P** is 

$$
|P| = max_{1\leq i \leq k} \text{diam}(P_i)
$$

Explanation. The term *****diam***** stands for **********diameter.********** The “diameter” of a subset in a metric space refers to the greatest distance between any two points within that subset. This diameter is calculated simply from euclidean distance on a metric space. 

************************Exercise 5.5.4.************************ Let $R \subset \mathbb{R^n}$ be a generalized rectangle. Show that if $v(R) = 0$, then there do not exist partitions of R. 

→ We know that $v(R)$ is defined as $\prod^n_{i=1}(b_i - a_i)$. 

→ Endpoints $b_i$ and $a_i$ come from our intervals $I = I_1 \times ... \times I_n$. 

→ So in order to satisfy $v(R) = 0$, we need to either have (1) no intervals in $I$, or (2) have $b_i =a_i \forall i \in I$. 

(1) If we have no intervals, we have $v(R) = 0$, then trivially, there’s no partitions. 

(2) If $b_i =a_i \forall i \in I$, then we know we’re dealing with a single point in space with no dimensions. Because there’s no depth, width, or any congruent form of dimension if there’s no distance between the endpoints in the intervals. Therefore, it is obvious that $v(R) = 0$ and that no partitions can be formed with no dimensions to go through. 

$\square$

******************************Exercise 5.5.5.****************************** Let $R \subset \mathbb{R^n}$ be a generalized rectangle with $v(R) > 0$. Let $P_i$  and $P_j$ be two sub-rectangles from a partition $\text{of } R$. Show that, 

![Screenshot 2023-10-04 at 4.05.11 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_4.05.11_PM.png)

Intuition. The statement $v(P_i \cap P_j) = 0$  mathematically asserts that the volume of the intersection of two sub-rectangles is zero. 

Solution. By definition of a *********partition*********, all sub-rectangles are pairwise disjoint, which means that no two sets in the collection have any elements in common. Therefore, $P_i$  and $P_j$, being the servant partitions they are, do not intersect at all, so their intersection has no points in it, implying that its volume is 0! 

$\square$

****Exercise 5.5.6.**** Let $R \subset \mathbb{R^n}$ be a generalized rectangle with $v(R) > 0$, and let $R_1, R_2, ..., R_N$ be a finite collection of sub-rectangles of *R*, each with nonzero volume. Show that there exists a partition $P \text{ of } R$ that satisfies the following property: For every $i$ and every sub-rectangle $S$ in $P$, either $S$ is a sub-rectangle of $R_i$ or $S \cap R_i = \emptyset$. 

<aside>
🍫 Intuition for this (more complicated) problem. Imagine having a large chocolate bar on a table. You have marked regions on this bar to represent flavors: maybe the top left is dark chocolate ($R_1$), the bottom right is mil chocolate ($R_2$), and so on. Now, when you break the chocolate bar into pieces, you must ensure each piece is entirely of one flavor or is an empty space. So to actually solve this problem, since we know from our previous solution (5.5.5) that no two pieces from a partition can overlap, all we need to prove is that ****************************************************************************for every piece S in our partition P, either S lies entirely within a chunk $R_i$, or $S$ doesn’t intersect with any chunk at all.*

</aside>

Solution.

→ We’re going to approach this with an algorithm-like solution. 

→ First, let’s consider the partition induced just by the sub-rectangles $R_1, R_2, ..., R_n$. This gives us a coarse partition where the boundaries of our chunks $R_i$ define some partitions. 

→ Now, for each sub-rectangle $S$ in the initial partition: 

⇒ If S is entirely contained in one $R_i$, keep as is. 

⇒ Else if S intersects more than one $R_i$, further break it down until completely inside. 

→ After every iteration for each sub-rectangle, the refined partition P will have the property that we want. 

$\square$

🗒️ Note. *Let $R$ be a generalized rectangle in $\mathbb{R}^n$. Let $f : R \rarr \mathbb{R}$ be a bounded function. We define the integral of $f$ over the generalized rectangle $R$ by the same method we used in the one-variable case…* 

Intuition**********************.********************** This definition sets the stage for understanding how to integrate functions over n-dimensional boxes. Because we’re familiar with Riemann integrals in one dimension, this is essentially extending that concept to higher dimensions. When we expand to multiple dimensions, such as two (2D) or more, we're now dealing with volumes (in 3D) or even more complex "hyper-volumes" in higher dimensions. The concept described here is an extension of the 1D scenario to n dimensions.

********************************************Definition 5.5.7 (Upper and Lower Sums).******************************************** 

Intuition. We can think of a *************generalized rectangle in $\mathbb{R}^n$ as an n-dimensional box. $f$ in this case is bounded, which means it won’t shoot off to infinity.* Now we say P is a partition of R, but what does this mean? Think of it like a chocolate bar divided into P pieces. Each piece of chocolate is a sub-rectangle. With all this in mind, our **********Upper Sum********** is going to be the maximum value of the function over each sub-rectangle (chocolate bar piece) $P_i$, which we’ll set as $M_i$ and multiply by the “size” (or volume) of that sub-rectangle. Summing this up gives us an overestimation of the total volume. We do the same but with the minimum for getting the ***********Lower Sum.*********** 

![Screenshot 2023-10-04 at 6.47.45 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_6.47.45_PM.png)

****************************Exercise 5.5.8.**************************** Let $f$  be a bounded function on $R$ with $m \leq f(x) \leq M \text{ } \forall x\in R$.  Given a partition of $R$, show that $m *v(R) \leq L(f,P) \leq U(f,P) \leq M*v(R)$. 

Intuition. This exercise is teaching us that the true integral lies somewhere between our conservative and optimistic estimates, this being our lower and upper sums, respectively. 

Formal. We need to show that for any arbitrary partition $P$ of $R$: 

1. The total volume of the lower estimate is at least $m \times$$\text{volume of }R$. 
2. The total volume of the upper estimate is at most $M \times \text{volume of }R$. 

→ Lower Sum. For every sub-rectangle in partition P, $m_i$ represents the smallest value of $f$. Since $f(x)$ is always at least $m$, we know that $m_i \geq m$ for every sub-rectangle. Therefore, mathematically, we know that: 

$$
\sum^k_{i=1}m_i \times v(P_i) \geq m \times v(R). 
$$

→ Upper Sum. The same argument applies for $M$ and the upper sum. Mathematically, 

$$
\sum^k_{i=1}M_i \times v(P_i) \leq M \times v(R). 
$$

→ Therefore, we know that for any partition **P** of *R*, the lower sum L(f, P) is always at least $m \times v(R)$ and the upper sum U(f, P) is always at most $M \times v(R)$. 

**********Def.********** Let $P$ be a partition of $R$, and let $P'$ be a refinement of $P$. It is trivially true then that, 

$$
L(f, P) \leq L(f, P') \leq U(f, P') \leq U(f, P). 
$$

**********************************Definition 5.5.14 (Lower and Upper Integrals).********************************** Let $R \subset \mathbb{R^n}$ be closed generalized rectangle, and let $f : R \rarr \mathbb{R}$ be a bounded function. 

1. We define the ************lower integral of $f$ on $R$  to be*
    
    ![Screenshot 2023-10-04 at 8.28.51 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_8.28.51_PM.png)
    
2. And we define the ***************upper integral*************** of $f$ on $R$  to be
    
    ![Screenshot 2023-10-04 at 8.29.29 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_8.29.29_PM.png)
    

Intuition. This definition introduces the concept of the “upper” and “lower” integrals for a bounded function on a certain type of space called a “generalized rectangle”. The main idea is to approximate the area under a curve from above and below using rectangles. For each piece of the partition you consider the maximum/minimum value of the function and multiply it by the volume of that piece. The lower sums can’t be smaller than multiplying the minimum value of $f$  by the volume of $R$ and the upper sums can’t be longer than multiplying the maximum value of $f$ by the volume of $R$. 

****************************Exercise 5.5.15.**************************** For any bounded function $f : R \rarr \mathbb{R}$, we have 

![Screenshot 2023-10-04 at 8.35.41 PM.png](Chapter%205%20b84cd272c9274575a7c2c387f6c8a5e1/Screenshot_2023-10-04_at_8.35.41_PM.png)

Intuition. We break our domain $R$ into tiny pieces (partitions). For each partition, we look at the function values it contains and take the smallest one. Then we add all these smallest values, which gives us a sum that is an under-estimation of the true volume. The ***************lower integral*************** is the value we get as we refine our partitions to make them smaller and smaller until they capture the true essence. Similarly, we do the same to get the ***************Upper Integral*************** but instead we take the biggest function values we can find and still refine our partitions. 

Solution. Because we know that $L(f, P) \leq U(f, P)$  for every partition $P$ of $R$, we know that the largest possible lower sum will always be less than or equal to the smallest possible upper sum  $\square$. 

******************************************************************************Definition 5.5.17 (Regular Partitions).****************************************************************************** Let $R = [a_1, b_1] \times [a_2, b_2] \times ... \times [a_n, b_n]$ be a closed generalized rectangle. For each $i, 1 \leq i \leq n$ we take a partition $P_i = \{a_i = a_{i,0}, a_{i,1}, ..., a_{i, k_i} = b_i\}$ which is ordered. With this, we define a ******************regular partition****************** P of R by $P = P_1 \times ... \times P_n$, consisting of the $k_1 * k_2 * ...*k_n$ sub-rectangles of the form $(a_1,_{j_1}, a_1,_{j_2+1}) \times (a_2,_{j_2}, a_2,_{j_2+1}) \times ... \times (a_n,_{j_n}, a_n,_{j_n+1})$  with $0 \leq j_i \leq k_i$ for $1 \leq i \leq n.$ 

Intuition. A regular partition is a special kind of partition where every subinterval for a given dimension is of equal length. While both normal partitions and regular partitions break the space into pieces, a regular partition ensures that all these pieces are uniform and of the same size across all dimensions. In simpler terms, think of this definition as describing how to neatly slice up a multi-dimensional space. For each “dimension” of this space, imagine we have a ruler which divides that dimension into segments. Now, combine these divisions across all dimensions, and you get a grid like pattern of smaller blocks or “sub-spaces” within the larger space. 

********************************Exercise 5.5.18. Todo.******************************** 

**************************************Definition 5.5.19 (Riemann Integral).************************************** Let $f$ be a bounded function on a closed generalized rectangle $R \subset \mathbb{R^n}$. We say that $f$ is integrable on $R$ if $\int_{R_{-}}f = \int^{-}_Rf$, and we denote this common value 

by $\int_Rf$, which we call the ***Riemann Integral** $f$ on R.* 

Properties

For educational purposes and simplicity purposes, it should be noted that the following 3 theorems are perfect analogues of the corresponding results in one variable functions. The proofs carry from before. 

**********************Theorem 1 ($f$ Integrable on $R$).** Let $f$ be a bounded function on a closed generalized rectangle $R \subset \mathbb{R}^n$. Then $f$ is integrable on $R$ $\iff$given $\epsilon > 0$, there exists a partition $P$ of $R$ s.t. $U(f, P) - L(f, P) < \epsilon$. 

**Intuition**. Imagine you have an apple orchard. And you want to determine how many apples are in the entire fields without counting each apple individually. So you divide the field into subplots (sub-rectangles) and count the apples in each plot. Then sum them up. Now, the upper sum is like over-estimating the apples by counting the maximum number of apples in each plot, while the lower sum is like underestimating by counting the minumum. As you refine your plots, the lower and upper should become closer and closer. If they can become arbitrarily close (differing by less than $\epsilon$), then you can be confident in the total number of apples in the entire orchard, or in this case, the integrability of $f$. 

This theorem is simply saying that the upper sum is within an $\epsilon$ range above the lower sum. The inequality states that the difference between the upper and lower sums is less than some value $\epsilon$. It’s basically ensuring that the upper and lower bound are sufficiently “close” to each other. 

**************Proof.************** 

**********************Theorem 2 ($f$ continuous $\implies$ Integrable on $R$).** Let $R \subset \mathbb{R}^n$ be a closed generalized rectangle. Suppose $f : R \rarr \mathbb{R}$ is continuous. Then $f$ is Riemann integrable on $R$. 

**Intuition**. We have a “box” in n-dimensions. It’s closed, which means the boundaries are included. Our function $f$ tells us that we can take any point inside our box $R$ and map it to a real number. We also know that the function is continuous, which means that there are no abrupt jumps or breaks in the values it assigns. The theorem essentially says: if you have a continuous function $f$ that’s defined over a closed “box” $R$ in n-dimensional space, then this function $f$ is Riemann integrable over $R$. 

**********************Theorem 3.********************** Let $(f_k)_{k \in \mathbb{N}}$ be a sequence of Riemann integrable functions defined on a close generalized rectangle $R \subset \mathbb{R}^n$. Suppose that $(f_k)_{k \in \mathbb{N}}$ converges uniformly to a function $f$ on $R$. Then $f$ is Riemann integrable on $R$, and

$$
\int_Rf = lim_{k\rarr\infty}\int_Rf_k
$$

**********************Intuition.********************** Now we’re dealing with a sequence of functions, but we’re still dealing with a generalized-rectangle —”box-like” region in n-dimensional space. In this scenario, all the functions $f_k$ are getting closer and closer to some function $f$ as $k$ grows, and they’re doing so at the same “speed” everywhere in the domain $R$. From this, two main conclusions can be drawn: (1) The function $f$ they’re approaching is also Riemann integrable on $R$. (2) The integral of $f$ on $R$ (its “total value” over $R$) is equal to the limit of the integrals of the $f_k$ functions as $k$ goes to infinity. 

<aside>
📜 Essentially, the theorem assures us that if the sequence of functions is “heading” towards a particular function in a uniform way, then the areas under under these function curves are also “heading” towards the area under the curve of that particular function. *It’s a way to assign the notion of convergence to areas under a curve.*

</aside>

⇒ Propositions

******************************Proposition 1.****************************** Let $R \subset \mathbb{R^n}$ be a closed generalized rectangle, and let $f : R \rarr \mathbb{R}$ be a bounded function. 

1. $f$ is integrable on $R$ if and only if, given $\epsilon$ > 0, there exists a $\delta > 0$ s.t. if $P$ is a partition of $R$ with $|P| < \delta$, then $U(f, P) - L(f, P) < \epsilon$. 
    
    **Intuition**. This is providing a precise definition of what it means for a function to be integrable. If we can get the upper and lower sums to be as close to each other as we want by choosing a sufficiently fine partition, then $f$ is integrable. 
    
2. Suppose $f$ is integrable on $R$, and we have a sequence of partitions $(P_k)_{k\in N}$ of $R$ s.t. $lim_{k\rarr \infty}|P_k| = 0$. Then, 

$$
\int_Rf = lim_{k \rarr \infty}L(f, P_k) = lim_{k \rarr \infty}U(f, P_k)
$$

       **********************Intuition.********************** If a function is integrable, the limit of the lower sums and the limit of the     upper sums will converge to the same value: the integral of $f$ over $R$. 

******************************Proposition 2.******************************  Let $R \subset \mathbb{R^n}$ be a closed generalized rectangle, let $f, g : R \rarr \mathbb{R}$ be integrable functions, and let $\alpha \in \mathbb{R}$. Then

1. $\int_R(f + g) = \int_Rf + \int_Rg$
2. $\int_R \alpha f = \alpha \int_R f$
3. if $f(x) \leq g(x) \text{ for all }x \in R, \text{ then } \int_Rf \leq \int_Rg; \text { and } |f| \text { is integrable, and } |\int_Rf| \leq \int_R |f|$