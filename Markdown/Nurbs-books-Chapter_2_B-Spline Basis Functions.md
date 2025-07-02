# **CHAPTER  TWO** 

## *B-Spline Basis Functions* 

## **2.1	Introduction** 

Curves consisting of just one polynomial or rational segment are often inade- quate. Their shortcomings are:   
uo   
• a high degree is required in order to satisfy a large number of constraints; e.g., (n − 1)-degree is needed to pass a polynomial Bézier curve through   
•   
wwwwwww   
n data points. However, high degree curves are inefficient to process and are numerically unstable;   
• a high degree is required to accurately fit some complex shapes; single-segment curves (surfaces) are not well-suited to interactive shape design; although Bézier curves can be shaped by means of their control points (and weights), the control is not sufficiently local.   
The solution is to use curves (surfaces) which are piecewise polynomial, or piecewise rational. Figure 2.1 shows a curve, C(u), consisting of m (= 3\) nth- degree polynomial segments. C(u) is defined on u € \[0, 1\]. The parameter values \= 0 \< u1 \< U2 \< Uz 1 are called breakpoints. They map into the endpoints of the three polynomial segments. We denote the segments by Ci (u), 1 ≤ i ≤ m. The segments are constructed so that they join with some level of continuity (not necessarily the same at every breakpoint). Let C) denote the jth derivative of C1. C(u) is said to be C continuous at the breakpoint u; if C3) (u,) \= C1(ui)   
for all 0 \<j\< k.   
Any of the standard polynomial forms can be used to represent C; (u). Figure 2.2 shows the curve of Figure 2.1 with the three segments in cubic Bézier form. Pa denotes the ith control point of the jth segment.   
If the degree equals three and the breakpoints U {uo, ui, uz, u3} remain fixed, and if we allow the twelve control points, P, to vary arbitrarily, we obtain the vector space, V, consisting of all piecewise cubic polynomial curves   
48 B-Spline Basis Functions   
C1(u)   
ио 0   
U1   
C2(u)   
C3(u)   
ՂԱԶ   
Из 1   
Pl   
P   
P   
P \= P   
P2   
ио 0   
นา   
P3   
P2   
P3 P3   
บว   
Pi P3   
Introduction 49   
Uz 1   
Figure 2.1. A piecewise cubic polynomial curve with three segments.   
on U. V has dimension twelve, and a curve in V may be discontinuous at u1 or u2. Now suppose we specify (as in Figure 2.2) that P \= P2 and P3 P3. This gives rise to Vo, the vector space of all piecewise cubic polynomial curves on U which are at least Co continuous everywhere. V has dimension ten, and Do CV.   
u1. Assume   
Imposing C1 continuity is a bit more involved. Let us consider u \= that P3 P3. Let   
V \=   
น ио   
Ալ ио   
and W   
น   
Աշ   
U1   
นา   
be local parameters on the intervals \[uo, u1\] and \[u1,u2\], respectively. Then 0 ≤ v, w ≤ 1\. C1 continuity at u1 implies   
1   
1   
C{1) (v \= 1\) \= C(1) (u1) \= C(1) (u1) \=   
C(1) (w \= 0\)   
աշ   
นา   
U1   
ио   
and from Eq. (1.10) it follows that   
Thus   
3   
ALLA   
3   
(P3 \- P1)   
(P2 \- P2)   
Ալ   
Цо   
Պաշ U1   
P3   
(U2 − P)   
u1) P2+ (u1 \- uo) P   
P2   
աշ ио   
(2.1)   
Equation (2.1) says that P3 and P3 can be written in terms of P1, P2 and P2, P3, respectively. Hence, V1, the vector space of all C1 continuous piecewise cubic polynomial curves on U, has dimension eight, and V1 CVO CV.   
This makes it clear that storing and manipulating the individual polynomial segments of a piecewise polynomial curve is not the ideal method for handling   
Figure 2.2. The curve of Figure 2.1 shown with the polynomial segments represented in Bézier form.   
such curves. First, redundant data must be stored: twelve coefficients, where only eight are required for C1 continuous cubic curves, and only six for C2 continuous cubic curves. Second, for the Bézier form the continuity of C(u) depends on the positions of the control points, hence there is little flexibility in positioning control points while maintaining continuity. If a designer wants C1 continuity and is satisfied with the segments C1(u) and C3(u), but wants to modify the shape of C2(u), he is out of luck: none of C2(u)'s control points can be modified. Third, determining the continuity of a curve requires computation (such as Eq. \[2.1\]).   
We want a curve representation of the form   
C(u) \= Σfi(u) P;   
Σ   
i=0   
(2.2)   
where the P; are control points, and the {ƒ¿(u), i 0,...,n} are piecewise poly- nomial functions forming a basis for the vector space of all piecewise polynomial functions of the desired degree and continuity (for a fixed breakpoint sequence, U \= {ui}, 0 ≤ i ≤ m). Note that continuity is determined by the basis functions, hence the control points can be modified without altering the curve's continuity. Furthermore, the {fi} should have the ‘usual' nice analytic properties, e.g. those listed in Section 1.3. This ensures that the curves defined by Eq. (2.2) have nice geometric properties similar to Bézier curves, e.g., convex hull, variation dimin- ishing, transformation invariance. Another important property that we seek in our basis functions is that of local support; this implies that each f¿(u) is nonzero only on a limited number of subintervals, not the entire domain, \[uo, um\]. Since P is multiplied by f;(u), moving P; affects curve shape only on the subintervals where fi(u) is nonzero.   
Definition and Properties of B-spline Basis Functions 51   
50 B-Spline Basis Functions   
Finally, given appropriate piecewise polynomial basis functions, we can con- struct piecewise rational curves   
Cw(u) \= fi(u) Pw   
i=0   
and nonrational and rational tensor product surfaces   
n   
m   
S(u, v) \= ΣΣfi(u)gj(v) Pi,j   
i=0 j=0   
n   
m   
sw (u,v) \= ΣΣfi(u)9j(v) Puj   
i=0 j=0   
น   
Иі   
Ui+4   
น   
Ni,3   
Ui+3   
Ui   
(2.3)   
Ui+4 \- Ui+1   
Ni,2   
(2.4)   
For the remainder of this chapter we study the so-called B-spline basis func- tions. In Chapters 3 and 4 we combine these functions with three-dimensional and four-dimensional control points to obtain nonrational and rational curves and surfaces, respectively.   
2.2   
Definition and Properties of B-spline Basis Functions   
There are a number of ways to define the B-spline basis functions and to prove their important properties, e.g., by divided differences of truncated power func- tions \[Curr47; Scho46\], by blossoming \[Rams87\], and by a recurrence formula due to deBoor, Cox, and Mansfield \[Cox72; DeBo72, 78\]. We use the recurrence formula, since it is the most useful for computer implementation.   
Let U   
{uo, um} be a nondecreasing sequence of real numbers, i.e., u¿ ≤ m-1. The uż are called knots, and U is the knot vector. The ith B-spline basis function of p-degree (order p+1), denoted by Ni, p(u), is defined as   
U i \+1, i   
www   
0,....   
1 if u \<u\< Ui+1   
Ni,o(u) \=   
{}   
0   
otherwise   
Ці   
Ni,p(u) \=   
Ni,p-1(u) \+   
Ui+p   
Ui   
Ui+p+1 U   
Ui+p+1   
U i \+ 1   
Ni+1,p-1(u)   
(2.5)   
Wi   
Ui+1   
Ui+2   
Ni+1,2   
Uż+4   
Ui+3   
Figure 2.3. The recursive definition of B-spline basis functions.   
•   
•   
computation of a set of basis functions requires specification of a knot vector, U, and the degree, p;   
Equation (2.5) can yield the quotient % (see examples later); we define this quotient to be zero;   
the Ni,p(u) are piecewise polynomials, defined on the entire real line; generally only the interval \[uo, um\] is of interest;   
•   
the half-open interval, \[uż, ui+1), is called the ith knot span; it can have zero length, since knots need not be distinct;   
•   
No,0   
the computation of the pth-degree functions generates a truncated trian- gular table   
No,1   
N1,0   
No,2   
N1,1   
No,3   
N1,2   
N2,0   
N2,1   
N1,3   
N2,2   
:.   
N3,0   
N3,1   
N4,0   
:   
Note that   
Ni,o(u) is a step function, equal to zero everywhere except on the half-open interval u Є \[ui, Ui+1);   
for p \> 0, Ni,p(u) is a linear combination of two (p \--- 1)-degree basis functions (Figure 2.3);   
For brevity we often write Ni,p instead of Ni,p(u).   
A word about terminology. In Section 2.1 we used the term breakpoint and required u¿ \< u1+1 for all i. In the remainder of this book we use the term knot and assume u ui+1. The breakpoints correspond to the set of distinct knot values, and the knot spans of nonzero length define the individual polynomial segments. Hence, we use the word knot with two different meanings: a distinct   
Definition and Properties of B-spline Basis Functions 53   
52 B-Spline Basis Functions   
value (breakpoint) in the set U, and an element of the set U (there can exist additional knots in U having the same value). It should be clear from the context which meaning is intended.   
Examples   
Ex2.1   
∞\>n\>∞00.   
0,42 0,43 1,24   
Let U \= {uo \= 0, u1   
1,25 1} and p 2\. We now compute the B-spline basis functions of degrees 0, 1, and 2   
No,0 \= N1,0 0   
0   
0 ≤ u\<1   
otherwise   
N3,0 \= N4,0 0 \-∞\<u\<∞   
N2,0   
{   
Uu   
0   
น   
No,1 \=   
No,0 \+   
N1,0   
0   
0   
0   
1   
น   
www.   
1   
1 น   
\<   
\< ∞   
0 \<u \<1   
otherwise   
are shown in Figures 2.4, 2.5, and 2.6, respectively   
No,0   
N1,0   
0 for ∞\<u\<∞   
N2,0 \= {0 otherwise   
1 0 \<u \<1   
{\!   
1 \< u\<2   
1 2≤u \<3   
N3,0 \= {}   
1   
N4,0   
N5,0   
{ 3 su \<3   
1 3 \<u\<4   
{3 3 Su=4   
N6,0 \= 0 for   
∞\<u\<∞   
1 4\<u\<5   
N7,0 \= {0 otherwise   
N8,0   
www.   
N9,0 \= 0 for ∞   
N1,1N1,0 \+N20={1)   
น   
N2, N2,0 \+3,0 \= {"   
Na,1 3,0 \+40=0   
No,2   
N1.2   
www   
0   
U   
0   
0 ≤u \<1   
\=   
1   
otherwise   
U   
1   
1   
น   
N4,0   
1   
{   
(1   
\- u)2   
0 ≤ u\<1   
0   
otherwise   
1   
U   
0   
U   
\--   
No,1+ N1,1   
{2u(1-u)   
0   
1   
น   
0   
1   
0   
1   
น   
N1,1 \+   
N2,1   
0   
1   
otherwise   
น   
0   
1   
U   
u2   
N2,2   
N2,1 \+   
N3,1   
1   
0   
1   
1   
0   
0 \<u\<1   
otherwise   
Note that the N1,2, restricted to the interval u € \[0, 1\], are the quadratic Bernstein polynomials (Section 1.3 and Figure 1.13b). For this reason, the B-spline representation with a knot vector of the form   
U {0,   
0,1,   
p+1   
p+1   
is a generalization of the Bézier representation.   
Ex2.2   
Let U   
{uo   
www.   
1,24 2,25 3,46   
4,27   
0,21   
0, աշ 0,43 4, u8   
5, աց   
5, 210 5} and p 2\. The zeroth-, first-, and second- degree basis functions are computed here. The ones not identically zero   
น   
\-0   
0 น   
No,1   
No,o \+   
N1,0   
0   
\<∞   
0   
0   
0   
U   
\-0   
1   
น   
N1.1   
wwwwwww   
N1,0 \+   
0   
0   
1   
0   
N2,0 \= {1   
U   
0 \<u \< 1   
otherwise   
น   
0 \<u \<1   
N2,1   
U   
1   
0   
2   
U   
N2,0 \+   
N3,0   
2   
น   
1\<u\<2   
2   
1   
0   
otherwise   
น   
1   
1≤u \<2   
U   
1   
3   
U   
N3,1   
N3,0 \+   
N4,0   
2   
1   
3   
2   
3-u   
0   
2\<u \<3   
otherwise   
u-2 2≤u \<3   
U   
2   
4   
น   
N4,1   
N4,0 \+   
N5,0   
4 น   
3\<u\<4   
3   
4   
3   
น   
3   
4   
U   
N5,1   
N5,0 \+   
N6,0   
4   
3   
4   
4   
น 4   
5   
\-P   
U   
N6,1 \=   
N6.0 \+   
www   
5-4   
น   
wwww..   
4   
5   
น   
N7,1   
5   
|མ   
N7,0 \+   
4   
5   
5   
N7,0   
otherwise   
U 3 3≤u\<4   
10   
{   
5 U   
Ju   
N8,0 \= {\~-   
0   
otherwise   
4 ≤ u\<5   
otherwise   
4 4≤u\<5   
otherwise   
N8,1   
\#   
3 ho   
น   
5   
5 น   
· N8,0 \+   
N9,0   
0   
∞\>n\>∞   
5   
10   
5   
5-5   
54 B-Spline Basis Functions   
1   
N2,0   
0   
1   
3   
\+   
0   
1   
\~   
\#   
N4,0   
\+   
♡   
1   
\+   
5   
10   
TH   
5   
сл   
1   
1   
N3,0   
ลง   
2   
N2,2   
Definition and Properties of B-spline Basis Functions 55   
U   
0   
3   
น   
N2,1 \+   
N3,1   
2   
0   
3   
ཤང་   
\+   
车   
3   
4   
5   
น   
1   
4   
น   
N3,2   
N3,1 \+   
N4,1   
\=   
3   
1   
4   
N5,0   
\+   
\#   
\+H+   
N4,2   
1   
2   
3 4 5   
11⁄2u2 \-3/2+3u \- u2 1/2(3-u)2   
1/2(u-1)2   
\- 11/2 \+ 5u \- u2   
1/2(4-u)2   
1/2(u \- 2)2   
0 \<u \<1   
1\<u\<2   
2\<u\<3   
1≤u\<2   
2\<u \<3   
3 \<u\<4   
2≤u\<3   
\-16+10u3/2u2 3≤u\<4   
Hi   
\+   
0   
1   
HE   
N7,0   
H   
\+   
\#   
0   
1   
2   
3   
4   
5   
wwwww.xm   
U   
4   
www.   
2   
4   
น   
N4,1 \+   
N5,1   
2   
น   
3   
5   
U   
N5,2   
N5,1 \+   
N6,1   
www   
4   
3   
5   
(u \- 3)2 (5-u)2   
3\<u\<4   
4\<u\<5   
U   
4   
5   
И   
N6,2   
N6,1 \+   
N7,1   
2(u — 4)(5 — u)   
4≤u\<5   
5   
5   
4   
www.   
N7,2   
www.   
น   
5 4   
4   
5   
น   
N7,1 \+   
wwwwwww   
N8,1 \= (u-4)2   
4≤u\<5   
5   
www.   
Figure 2.4. The nonzero zeroth-degree basis functions, U {0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5}.   
All of the following Ni,2 are zero everywhere except on the specified intervals, that is   
น   
0   
1   
น   
No,2 \=   
No,1 \+   
N1   
wwwwwww...   
(1 − u)2   
0 ≤ u\< 1   
0   
1   
0   
น   
2   
U   
N1,2 \=   
N1,1 \+   
N2,1   
1   
2   
0   
2u \- 3/2u2 1/2(2-u)2   
0 ≤u \<1 1≤ u \< 2   
We now list a number of important properties of the B-spline basis functions. As we see in the next chapter, it is these properties which determine the many de- sirable geometric characteristics in B-spline curves and surfaces. Assume degree p and a knot vector U {uo,..., um}.   
P2.1   
Ni,p(u) \= 0 if u is outside the interval \[u1, Ui+p+1) (local support prop- erty). This is illustrated by the triangular scheme shown here. Notice   
N7,2   
N5,2   
1 No,2   
N3,2   
N4,2   
N2,2   
N6,2   
N7,1   
N1,2   
N4,1   
N3,1   
N6.1   
N2,1   
N1,1   
N5,1   
1   
0   
1   
2   
3   
0   
\#   
2   
3   
4   
5   
5   
Figure 2.5. The nonzero first-degree basis functions, U \= {0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5}.   
Figure 2.6. The nonzero second-degree basis functions, U \= {0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5}.   
56 B-Spline Basis Functions   
that N1,3 is a combination of N1,0, N2,0, N3,0, and N4,0. Thus, N1,3 is nonzero only for u € (u1, u5)   
Definition and Properties of B-spline Basis Functions 57   
with i and u arbitrary. By definition   
P2.2   
P2.3   
N1.0   
N2,0   
No.2   
No,3   
N1,1   
N1,2   
U   
wwwwww   
Ui   
Ni,p(u) \=   
Ni,p-1(u) \+   
Ui+p   
Ui   
Ui+p+1 U   
Ui+p+1 Ui+1   
· Ni+1,p-1(u) (2.6)   
By P2.1, Ni,p-1(u) \= 0 if u ¢ \[ui, Ui+p). But u € (ui, Ui+p) implies   
U   
www.   
Ui+p   
Ui   
Ui   
is nonnegative. By assumption, Ni,p-1(u) is nonnegative, and thus the first term of Eq. (2.6) is nonnegative. The same is true for the second term, and hence the Ni,p(u) are nonnegative;   
N1,3   
N2,1   
N2,2   
N3,0   
N2,3   
N3,1   
N3,2   
N4,0   
In any given knot span, \[u;, u;+1), at most p+1 of the N1,p are nonzero, namely the functions Nj-p,p,.........、   
Nj, p   
On \[uз, u4) the only nonzero zeroth-degree function is N3,0. Hence, the only cubic functions not zero on \[uз, u1) are No,3,..., N3,3. This property is illustrated here   
P2.4   
For an arbitrary knot span, \[u1, Ui+1), Σj=i-p Nj,p(u)   
1 for all   
u E \[ui, Ui+1) (partition of unity). To prove this, consider   
i   
i   
Σ Nj,p(u) \= Σ   
U   
Uj   
\-Njp-1(u)   
j=i-p   
j=i-p   
Uj+p   
\- Uj   
i   
\+ Σ   
Uj+p+1   
น   
Nj+1,p-1(u)   
Uj+p+1   
Uj+1   
j-i-p   
Changing the summation variable in the second sum from i-p to i-p+1, and considering that Ni-pp-1(u) \= Ni+1,p-1 (u) \= 0, we have   
No,3   
N1.1   
N1,2   
N2,0   
N1,3   
N2,1   
هر   
N2,2   
N3,0   
N3,1   
N3,2   
N4,0   
N3,3   
N4,1   
N2,3   
Ni,p(u) \> 0 for all i, p, and u (nonnegativity). This is proven by induc- tion on p. It is clearly true for p \= 0; assume it is true for p − 1, p ≥ 0,   
P2.5   
i   
Ź Nj, p(u) \=   
ΣΙ   
U \- Uj   
Uj+p   
\+   
Uj   
Uj+p น   
Uj+p \- Uj   
Njp\_1(u)   
j-i-p   
j=i-p+1   
Σ Nj,p-1(u)   
j=i-p+1   
Applying the same concept recursively yields   
i   
i   
i   
Σ Nj,p(u)   
\-   
Σ Nj,p-1(u)   
Σ Nj,p-2(u)   
j=i-p   
j=i-p+1   
j=i-p+2   
i   
ΣNj,o(u) \= 1   
j=i   
All derivatives of N1,p(u) exist in the interior of a knot span (where it is a polynomial, see Figure 2.7). At a knot Ni,p(u) is p-k times continuously differentiable, where k is the multiplicity of the knot. Hence, increasing   
58 B-Spline Basis Functions   
1   
즐(2-1)2   
N3,2   
0   
2   
3   
11   
\+ 5u- u2 2   
(4-3)2   
Figure 2.7. The decomposition of N3,2 into its polynomial pieces (parabolas).   
P2.6   
degree increases continuity, and increasing knot multiplicity decreases continuity;   
Except for the case p \= 0, Ni,p(u) attains exactly one maximum value. It is important to understand the effect of multiple knots. Consider the functions No,2, N1,2, N2,2, N5,2, and N6,2 of Figure 2.6. Recalling that U {0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5}, from Eq. (2.5) and P2.1, we see that these functions are computed on the following knot spans and are zero outside these spans   
No,2   
(0,0,0,1}   
N1,2 {0,0,1,2}   
2.3   
Derivatives of B-spline Basis Functions 59   
Derivatives of B-spline Basis Functions   
The derivative of a basis function is given by   
Ρ   
Ρ   
N\!   
i,p   
\-Nip-1(u)·   
Ni+1,p-1(u)   
Ui+p Ui   
Ui+p+1 \- Ui+1   
(2.7)   
(See Figure 2.8 for a graphical illustration.) We prove this by induction on p. For p \= 1, Ni,p-1 and Ni+1,p-1 are either 0 or 1, and thus N,, is either   
1   
1   
or   
Ui+1   
Ui   
Ui+2 Ui+1   
(see Figure 2.5). Now assume that Eq. (2.7) is true for p-1, p \> 1\. Using the product rule, (fg)' \= ƒ'g \+ ƒg', to differentiate the basis function   
น   
Ur   
Ni, p(u) :   
wwwwww   
Nip-1(u) \+   
Ui+p Ղաջ   
1   
yields   
N\!   
Ni,p-1   
,p   
Uitp ՂԱՂ   
1   
Ui+p+1 U   
Ui+p+1 − Ui+1   
น Ці   
\+   
Ui+p \- Ղաշ   
Ui+p+1 Ui+1   
www.   
Ni+1,p-1+   
N\!   
i,p-1   
Ni+1,p-1(u)   
(2.8)   
Ui+p+1 U   
Ui+p+1 Ui+1   
· N1+1,p−1   
N2,2   
{0,1,2,3}   
N5,2   
{3, 4, 4, 5}   
N6,2   
{4,4,5,5}   
Now the word 'multiplicity' is understood in two different ways:   
•   
the multiplicity of a knot in the knot vector;   
the multiplicity of a knot with respect to a specific basis function.   
For example, u —–—– O has multiplicity three in the previous knot vector U. But with respect to the functions No,2, N1,2, N2,2, and N5,2, u 0 is a knot of multiplicity 3, 2, 1, and 0, respectively. From P2.5, the continuity of these functions at u 0 is No.2 discontinuous; N1.2 C° continuous; N2.2 C1 continuous; and N5,2 totally unaffected (N5,2 and all its derivatives are zero at u \= 0, from both sides). N1,2 'sees' u O as a double knot, hence it is Co continuous. N2,2 'sees' all its knots with multiplicity 1, thus it is C1 continuous everywhere. Clearly, another effect of multiple knots (as seen by the functions) is to reduce the number of 'apparent' intervals on which a function is nonzero; e.g., N6,2 is nonzero only on u € (4,5), and it is only Co continuous at u \= \= 4 and u \= \= 5\.   
1   
Ni,3   
Ni2   
Ni+1,2   
Ui+3   
Ui+4   
Ui+1   
Ui+2   
Ui   
Figure 2.8. The recursive definition of B-spline derivatives.   
N3   
i,3   
60 B-Spline Basis Functions   
Substituting Eq. (2.7) into Eq. (2.8) for N,p-1 and N+1,p-1 yields   
Ni, P   
Ui+p   
1   
1   
Ni,p-1-   
Ni+1,p-1   
U i   
Ui+p+1   
Ui+1   
U   
U i   
p-1   
p-1   
\+   
Ni,p-2   
Ni+1,p-2   
wwwwwwww   
Ui+p աղ Ui+p-1 Иі   
Ui+p   
Ubi \+1   
www....   
\+   
Ui+p+1   
Ui+p+1 Ui+1   
น   
Р 1   
p-1   
Ni+1,p-2   
Ui+p Ui+1   
Ui+p+1 — Ui+2   
Ui+p   
1   
www.   
Ui   
1   
Ni,p-1   
Ni+1,p-1   
Ui+p+1 Ui+1   
p 1   
น   
Ui   
\+   
Ni,p-2   
p-1   
\+   
Ui+p   
p 1   
Ui+p Ui Ui+p-1   
Ui+1 Ui+p+1 Ui+1 Ui+p   
U i   
Ui+p+1   
น   
น Иг   
Ni+1,p-2   
Ui   
Derivatives of B-spline Basis Functions 61   
By the Cox-deBoor formula (Eq. \[2.5\]), the expressions in the parentheses can be replaced by Ni,p-1 and Ni+1,p-1, respectively. It follows that   
1   
Ui+p+1 Ui+1   
1   
· Ni+1,p−1   
Nip   
Ni,p-1   
Ui+p   
U i   
Р 1   
\+   
Ni,p-1   
Ui+p Ці   
p-1   
Ui+p+1 Ui+1   
Ni+1,p-1   
Ρ   
Ρ   
Ni+1,p-1   
Ni,p-1   
Ui+p   
ՂԱՐ   
Ui+p+1   
Ui+1   
Ni+2,p−2   
This completes the proof.   
(k)   
Now let N denote the kth derivative of N1,p(u). Repeated differentiation of Eq. (2.7) produces the general formula   
N(k−1)   
i,p-1   
N(k-1)   
i+1,p-1   
(2.9)   
N(\*)(u)   
p   
Ui+p \- Uż Ui+p+1 Ui+1   
Equation (2.10) is another generalization of Eq. (2.7). It computes the kth derivative of Ni,p(u) in terms of the functions Ni,p-k Ni+k,p-k   
(2.10)   
Ui+p+1 − Ui+1 Ui+p+1   
Ui+p+1 че   
Ni+2,p-2   
Ui+2   
k   
N(k)   
p\!   
i,p   
(p −k)\!   
Σak,j Ni+j,p-k   
j=0   
Noting that   
Ui+p+1 น   
Ui+p+1   
น   
Ui   
Ui+p+1 น   
U   
Wi   
with   
a0,0   
1   
\-1 \+   
\+1   
Ui+1   
Ui+p   
Ui   
Ui+p+1 Ui+1   
Uitp   
U i   
ak,0   
ak-1,0   
Ui+p-k+1 — Uį   
Ui+p+1   
Ui+1   
\+   
Ui+p+1   
U i \+ 1   
Ui+p+1 U   
Ui+p+1   
Ui+1   
Uitp   
աշ   
น   
աղ   
\+   
Ui+p   
U i   
Uitp   
Wi   
ak-1,jak-1,j-1   
j=1,...,k1   
ak,j   
Ui+p+jk+1   
Ui+j   
ak,k   
\-ak-1,k-1   
Ui+p+1 — Ui+k   
Ui+p   
Ui+p   
น   
U i   
น   
Ui+1   
Ui+p+1   
U i \+ 1   
we obtain   
N',p   
Ui+p   
1   
\+   
1   
Ni,p-1   
Ni+1,p-1   
Иг   
Ui+p+1   
Ui+1   
Remarks on Eq. (2.10):   
•   
k should not exceed p (all higher derivatives are zero);   
the denominators involving knot differences can become zero; the quotient is defined to be zero in this case (see Example Ex2.4 and Algorithm A2.3 in Section 2.5).   
We omit a proof of Eq. (2.10) but verify that it holds for k \= 1,2. By definition   
p 1   
น   
Иі   
·Ni,p-2 \+   
Ui+p   
\- ՂԱՀ   
Ui+p-1   
աշ   
Uitp น   
Ui+p Ui+1   
Ni+1,p-2   
1   
a1,0   
1   
Ui+p Иі   
a1,1   
Ui+p+1   
Ui+1   
Ρ   
1   
U   
Ui+p+1   
Ui+1   
\- Ui+1 Ni+1, p−2+ Ui+p Wi+1   
Ui+p+1 น   
Ui+p+1 Ui+2   
Ni+2,p—\~2   
and   
www   
N(1) \= 2(a1,0 Ni,p-1+01,1 Ni+1,p−1)   
Further Properties of the Basis Functions 63   
N(1)   
i,p-1   
p   
www.   
Ui Ui+p-1   
62 B-Spline Basis Functions   
Comparing this with Eq. (2.7) proves the case for k entiating Eq. (2.7) yields   
N(2)   
i,p   
Ui+p   
Ui+p   
p   
p   
www.   
Wi   
1; now let k:   
2\. Differ-   
p   
Ui+p+1 \- Ui+1   
N(1)   
i+1,p-1   
1   
p-1   
N6,3   
1   
No,3   
N3,3   
N4,3   
N5.3   
N1,3   
N2,3   
Ni,p-2-   
Ni+1,p-2   
Ui   
Ui+p   
Ui+1   
p   
Ui+p+1 Ui+1   
p-1   
Ui+p \- Ui+1   
p-1   
Ni+1,p-2   
Ni+2,p-2   
0   
2   
6   
8   
Ui+p+1 Ui+2   
(a)   
\= p(p \-   
a1,0   
Ui+p-1   
Ni,p-2   
U i   
1   
1   
Ui+p   
Ui+1   
Ui+p   
wwwww.......   
Ui   
\+   
Ui+p+1-24+1).   
Ni+1,p-2   
@1,1   
\+   
\-Ni+2,p-2   
N1,3   
1   
N1.3   
N2.3   
N'3.3   
N6,3   
wwwwww   
Ui+p+1 Ui+2   
\= p(p − 1\) | a2,0 Ni,p−2 \+   
Noting that k 2 and   
a1,1 — a1,0\_Ni+1,p−2 \+ a2,2 Ni+2,p-2)   
Ui+p Ui+1   
@2,1   
@1,1 a1,0   
Uitp ·Ui+1   
2   
N5,3   
it follows that   
2   
N(2) (u)   
a2,jNi+j,p−2(u)   
j=0   
For completeness, we give an additional formula for computing derivatives of the B-spline basis functions (see \[Butt76\])   
N(k)   
i,p   
p   
p   
U   
U i   
k   
Ui+p   
Ui   
N(k)   
i,p-1   
\+   
Ui+p+1   
Ui+p+1   
U   
N(K)   
Ui+1 k \= 0,   
i+1,p-1   
p-1   
(2.11)   
Equation (2.11) gives the kth derivative of N1,p(u) in terms of the kth derivative of Ni,p-1 and Ni+1,p-1-   
Figures 2.9b and 2.10b show the derivatives corresponding to the basis func- tions in Figures 2.9a and 2.10a. Figure 2.11 shows all the nonzero derivatives of N1,3. Note the effect of multiple knots in Figure 2.10b; N6,3 has a jump at the triple knot.   
No.3   
(b)   
Figure 2.9. (a) Cubic basis functions; (b) derivatives corresponding to the basis func- tions in Figure 2.9a.   
2.4   
U www.   
Further Properties of the Basis Functions   
Let {uj}, 0 ≤ j ≤ k, be a strictly increasing set of breakpoints. The set of all piecewise polynomial functions of degree p on {u} which are C continuous at \- u; forms a vector space, V (−1 ≤ r; ≤ p). If no continuity constraints are imposed (r; \= \-1 for all j), then the dimension of V (denoted dim(V)) is equal to k(p \+ 1). Each continuity constraint decreases the dimension by one, thus   
k   
dim(V) \= k(p \+ 1\) − Σ (r; \+ 1\)   
j-0   
(2.12)   
64 B-Spline Basis Functions   
N6,3(u)   
N5,3(u)   
1 No,3(u)   
N1,3(u)   
N2,3(u)   
N3,3(u) N4,3(u)   
0   
2   
4   
(a)   
Further Properties of the Basis Functions 65   
1   
N9,3(u)   
N   
N7,3(u)   
\- N8,3(u)   
6   
8   
N1,3   
N6,3   
N13   
N1.3   
1   
N's,3   
N'3.3   
N'2,3   
2   
CO   
No,3   
No.3   
:00   
Ng,3   
No,3   
(b)   
Figure 2.10. (a) Cubic basis functions showing single, double, and triple knots; (b) derivatives of the functions in Figure 2.10a.   
Ni,3(u)   
N3   
Ui+4   
Ui+3   
Ui+2   
Ui+1   
Ui   
N1,3   
Figure 2.11. Ni,3 and all its nonzero derivatives.   
Then clearly, there are m zeroth-degree functions, N¿,0, m · 1 first degree func- tions, N1,1, and in general, m \-p pth-degree functions, Ni,p, which have the desired continuity, r; \= p − s;. Hence the Ni,p are contained in V. Substituting Sj \= p-r; into Eq. (2.12) yields   
k   
dim(V) \= k(p \+ 1)(ps; \+ 1\)   
j=0   
k   
\= k(p \+ 1\) − (k \+ 1)p \+ Σ s; − (k \+ 1\)   
\= −   
k   
\-p-1+   
Sj   
j=0   
j=0   
By Property P2.5, we obtain the B-spline basis functions of p-degree with knots at the {u}, and with the desired continuity, by setting the appropriate knot multiplicities, sj, where Sj \= p-rj. Hence, we use a knot vector of the form   
Now set   
U \= {   
\>   
uo, u1,   
, u1,   
Uki   
9   
ик   
So   
$1   
m   
\- (2) \-:   
j=0   
1   
Sk   
m \- p   
Thus, the number of pth-degree B-spline basis functions on U is equal to dim(V). We now justify the term 'basis' functions by showing that the N1,p are linearly independent, i.e., they form a basis for the vector space, V. The proof is by. induction on p. Clearly, the zeroth-degree functions are linearly independent. Assume the (p-1)th-degree functions are linearly independent for p \> 0\. Set n \= m − p − 1, and assume that   
n   
Σœ¿Ni,p(u) \= 0 for all u   
i=0   
66 B-Spline Basis Functions   
Using Eq. (2.7) we obtain   
0   
n   
n   
i=0   
Ni,p-1   
i=0   
Computational Algorithms 67   
Ex2.2, Section 2.2 is nonuniform because of the double knot at u 4\. Figure 2.9a shows a set of uniform cubic basis functions, and Figures 2.10a and 2.12 show nonuniform cubic basis functions.   
Ο Σαί   
Uitp   
Ui   
Ui+p+1   
Ni+1,p-1   
Ui+1   
i0   
which implies that   
n   
n   
Ni,p-1   
0   
αi   
αν   
Ui+p   
U i   
i=0   
i=0   
Now noting that No,p-1 Nn+1,p-1 in the second term, we have   
n   
Ni+1,p-1   
LAIKAM   
Ui+p+1 Ui \+1   
0, and changing the summation variable   
ai ai-1   
0 for all i (by assumption), which in turn implies   
0 for all i. This completes the proof. We turn our attention now to knot vectors. Clearly, once the degree is fixed the knot vector completely determines the functions Ni,p(u). There are several types of knot vectors, and unfortunately terminology varies in the literature. In this book we consider only nonperiodic (or clamped or open) knot vectors, which have the form   
U   
{a,..., a, Up+1, Um-p-1, ,b,...,b}   
p+1   
p+1   
(2.13)   
that is, the first and last knots have multiplicity p+1. For nonperiodic knot vectors we have two additional properties of the basis functions:   
P2.7   
A knot vector of the form   
U   
{0,..., 0, 1, . . ., 1}   
p+1   
p+1   
•   
N(),p(u),..., N() (u) for k \= 0,......,p; for k \> p the derivatives are zero   
i,p   
(this algorithm is based on Eq. \[2.10\]);   
⚫ a single basis function, Nj,p(u), where 0 ≤ j ≤m-p-1;   
⚫ the derivatives of a single basis function, N(k)(u), where 0 ≤ j ≤m-p-1   
and k \= 0,......‚p (based on Eq. \[2.9\]).   
'î \- p, p 1 · · · \* 

P2.8   
yields the Bernstein polynomials of degree p (see Example Ex2.1 in Sec- tion 2.2);   
Let m \+ 1 be the number of knots. Then there are n \+ 1 basis functions, where n   
p 1; No,p(a) \= 1 and Nn,p(b) 1\. For example, No,p(a)   
wwwwww   
m   
0, since this   
1 follows from the fact that No,0,..., Np-1,0 implies that No,p(a) \= Np,o(a) \= 1\. From P2.4 it follows that Ni,p(a) \=   
0 for i 0, and Ni,p(b) \= 0 for in.   
For the remainder of this book, all knot vectors are understood to be nonperi- odic. We define a knot vector U {uo,..., um} to be uniform if all interior knots   
are equally spaced, i.e., if there exists a real number, d, such that d Ui+1 for all p \< i \<m-p-1; otherwise it is nonuniform. The knot vector of Example 

## **2.5 	Computational Algorithms** 

In this section we develop algorithms to compute values of the basis functions and their derivatives. Let U \= {u0, ... , um} be a knot vector of the form in Eq. (2.13), and assume we are interested in the basis functions of degree *p*. Furthermore, assume *u* is fixed, and u  \[ui, ui+1). We develop five algorithms that compute: 

* the knot span index, *i*;   
* Ni-p,p(u), ..., Ni,p(u) (based on Eq. \[2.5\]);   
* $$N\_{i-p,p}^{(k)}(u), \\ldots, N\_{i,p}^{(k)}(u)$$ for *k \= 0, …, p*; for k \> p the derivatives are zero (this algorithm is based on Eq. \[2.10\]);  
* a single basis function, Nj,p(u) , where 0 j  m \- p \-1;  
* the derivatives of a single basis function, $$N\_{i,p}^{(k)}(u)$$, where 0 j  m \- p \-1 and *k \= 0, …, p* (based on Eq. \[2.9\])

We present the two algorithms which compute p \+ 1 functions before the two which compute only one, because they are the most important and actually are somewhat simpler. 

From P2.2 and the assumption that u  \[ui, ui+1), it follows that we can focus our attention on the functions Ni-p,p, ..., Ni,p and their derivatives; all other functions are identically zero, and it is wasteful to actually compute them. Hence, the first step in evaluation is to determine the knot span in which *u* lies. Either a linear or a binary search of the knot vector can be used; we present here a binary search. Since we are using intervals of the form u  \[ui, ui+1), a subtle problem in the evaluation of the basis functions is the special case u \= um. It is best to handle this at the lowest level by setting the span index to n (=m-p-1). Hence, in this case u  \[um-p-i, um-p). ***FindSpan*** is an integer function which returns the span index. 

#### **Algorithm A2.1**

\`\`\`  
FindSpan(n, p, u, U)  
{   /\* Determine the knot span index \*/  
    /\* Input:  n, p, u, U          \*/  
    /\* Return: the knot span index \*/

    if (u \== U\[n+1\]) return n;  /\* Special case /  
      
    int low \= p;  
    int high \= n \+ 1; /\* Do binary search \*/  
    int mid \= (low \+ high) / 2;

    while (u \< U\[mid\] || u \>= U\[mid+1\])  
    {  
        if (u \< U\[mid\])  
            high \= mid;  
        else  
            low \= mid;  
        mid \= (low \+ high) / 2;  
    }  
      
    return mid;  
}  
\`\`\`

![][image1]  
Figure 2.12. Nonuniform cubic basis functions defined on U \= {0,0,0,0,1,5,6,8, 8, 8, 8}. 

Now we tackle the second algorithm. Assuming *u* is in the *i*th span, computation of the nonzero functions results in an inverted triangular scheme   
![][image2]

Example  
Ex2.3	Let p \= 2, U \= {0,0,0,1,2,3,4,4,5,5,5} and u \=52 (see Figure 2.6)  
	Then i \= 4, since u  \[u4, u5). Thus, we compute  
![][image3]

Substituting u \=52  into Eq. (2.5) (the reader should to this) yields  
$$ \\begin{align\*}  
N\_{4,0}\\left(\\frac{5}{2}\\right) &= 1 \\\\  
N\_{3,1}\\left(\\frac{5}{2}\\right) &= \\frac{1}{2}, \\quad N\_{4,1}\\left(\\frac{5}{2}\\right) \= \\frac{1}{2} \\\\  
N\_{2,2}\\left(\\frac{5}{2}\\right) &= \\frac{1}{8}, \\quad N\_{3,2}\\left(\\frac{5}{2}\\right) \= \\frac{6}{8}, \\quad N\_{4,2}\\left(\\frac{5}{2}\\right) \= \\frac{1}{8}  
\\end{align\*}

$$  
Notice that for fixed degree the functions sum to 1 (P2.4). 

It will be clear to the reader who carried out the substitutions in this example that there is a great deal of redundant computation inherent in Eq. (2.5). For example, writing out the second-degree functions in general terms, we have 

$$ \\begin{align}  
N\_{i-2,2}(u) &= \\frac{u \- u\_{i-2}}{u\_i \- u\_{i-2}} N\_{i-2,1}(u) \+ \\frac{u\_{i+1} \- u}{u\_{i+1} \- u\_{i-1}} N\_{i-1,1}(u) \\tag{2.14} \\\\  
N\_{i-1,2}(u) &= \\frac{u \- u\_{i-1}}{u\_{i+1} \- u\_{i-1}} N\_{i-1,1}(u) \+ \\frac{u\_{i+2} \- u}{u\_{i+2} \- u\_i} N\_{i,1}(u) \\tag{2.15} \\\\  
N\_{i,2}(u)   &= \\frac{u \- u\_i}{u\_{i+2} \- u\_i} N\_{i,1}(u) \+ \\frac{u\_{i+3} \- u}{u\_{i+3} \- u\_{i+1}} N\_{i+1,1}(u) \\tag{2.16}  
\\end{align}  
$$

Note that 

* the first term of Eq. (2.14) and the last term of Eq. (2.16) are not computed, since Ni-2,1(u) \= Ni+1,1(u) \= 0;   
* the expression   
  $$ \\frac{N\_{i-1,1}(u)}{u\_{i+1} \- u\_{i-1}}$$

  which appears in the second term of Eq. (2.14) appears in the first term of Eq. (2.15); a similar statement holds for the second term of Eq. (2.15) and the first term of Eq. (2.16). 

We introduce the notation   
$$\\text{left}\[j\] \= u \- u\_{i+1-j} \\qquad \\text{right}\[j\] \= u\_{i+j} \- u $$

Equations (2.14)-(2.16) are then   
$$ N\_{i-2,2}(u) \= \\frac{\\text{left}\[3\]}{\\text{right}\[0\] \+ \\text{left}\[3\]} N\_{i-2,1}(u) \+ \\frac{\\text{right}\[1\]}{\\text{right}\[1\] \+ \\text{left}\[2\]} N\_{i-1,1}(u) $$  
$$ N\_{i-1,2}(u) \= \\frac{\\text{left}\[2\]}{\\text{right}\[1\] \+ \\text{left}\[2\]} N\_{i-1,1}(u) \+ \\frac{\\text{right}\[2\]}{\\text{right}\[2\] \+ \\text{left}\[1\]} N\_{i,1}(u) $$  
$$ N\_{i,2}(u) \= \\frac{\\text{left}\[1\]}{\\text{right}\[2\] \+ \\text{left}\[1\]} N\_{i,1}(u) \+ \\frac{\\text{right}\[3\]}{\\text{right}\[3\] \+ \\text{left}\[0\]} N\_{i+1,1}(u) $$

Based on these observations, **Algorithm A2.2** computes all the nonvanishing basis functions and stores them in the array N\[0\], ..., N\[p\]

**ALGORITHM A2.2**   
\`\`\`  
BasisFuns(i, u, p, U, N)  
{  
    /\* Compute the nonvanishing basis functions \*/  
    /\* Input:  i, u, p, U       \*/  
    /\* Output: N                \*/

    N\[0\] \= 1.0;  
    for (int j \= 1; j \<= p; j++)  
    {  
        left\[j\]  \= u \- U\[i \+ 1 \- j\];  
        right\[j\] \= U\[i \+ j\] \- u;  
        saved \= 0.0;

        for (int r \= 0; r \< j; r++)  
        {  
            temp \= N\[r\] / (right\[r \+ 1\] \+ left\[j \- r\]);  
            N\[r\] \= saved \+ right\[r \+ 1\] \* temp;  
            saved \= left\[j \- r\] \* temp;  
        }

        N\[j\] \= saved;  
    }  
}  
\`\`\`

We remark that Algorithm A2.2 is not only efficient, but it also guarantees that there will be no division by zero, which can occur with a direct application of Eq. (2.5). 

Now to the third algorithm; in particular, we want to compute all $$N\_{r,p}^{(k)}(u)$$, for i-p ri  and0 ≤ k ≤ n, where n ≤ p. Inspection of Eq. (2.10) reveals that the basic ingredients are: 

* the inverted triangle of nonzero basis functions computed in Algorithm A2.2;   
* differences of knots (the sums: right \[r+1\]+left\[j-r\]), also computed in Algorithm A2.2;   
* differences of the ak,j; note that the ak,j depend on the ak-1,j, but not the as,j, for s \< k \-1

Viewed as a two-dimensional array of dimension (p \+ 1\) × (p \+ 1), the basis functions fit into the upper triangle (including the diagonal), and the knot differences fit into the lower triangle, that is   
![][image4]

Example

Ex2.4	 Let p \=2, U \= {0,0,0,1,2,3,4,4,5,5,5} and u \=52. Then u  \[u4, u5), and array becomes  
![][image5]  
Now compute $$N^{(1)}\_{4,2}\\left(\\frac{5}{2}\\right)$$  and $$N^{(2)}\_{4,2}\\left(\\frac{5}{2}\\right) $$; with i \= 4 in Eq. (2.10), we have

$$\\begin{align\*}  
a\_{1,0} &= \\frac{1}{u\_6 \- u\_4} \= \\frac{1}{2} \\\\  
a\_{1,1} &= \-\\frac{1}{u\_7 \- u\_5} \= \-1 \\\\  
a\_{2,0} &= \\frac{a\_{1,0}}{u\_5 \- u\_4} \= \\frac{1}{2} \\\\  
a\_{2,1} &= \\frac{a\_{1,1} \- a\_{1,0}}{u\_6 \- u\_5} \= \\frac{-1 \- \\frac{1}{2}}{4 \- 3} \= \-\\frac{3}{2} \\\\  
a\_{2,2} &= \-\\frac{a\_{1,1}}{u\_7 \- u\_6} \= \\frac{1}{4 \- 4} \= \\frac{1}{0} \\\\  
\\\\  
N^{(1)}\_{4,2} &= 2 \\left\[ a\_{1,0} N\_{4,1}\\left( \\frac{5}{2} \\right) \+ a\_{1,1} N\_{5,1}\\left( \\frac{5}{2} \\right) \\right\] \\\\  
\\\\  
N^{(2)}\_{4,2} &= 2 \\left\[ a\_{2,0} N\_{4,0}\\left( \\frac{5}{2} \\right) \+ a\_{2,1} N\_{5,0}\\left( \\frac{5}{2} \\right) \+ a\_{2,2} N\_{6,0}\\left( \\frac{5}{2} \\right) \\right\]  
\\end{align\*}  
$$

Now a1,1, a2,1 and a2,2 all use knot differences which are not in the array, but they are multiplied respectively by N5,1(52), N5,0(52), and N6,0(52), which are also not in the array. These terms are defined to be zero, and we are left with  
$$\\begin{align\*}  
N^{(1)}\_{4,2} &= 2 a\_{1,0} N\_{4,1} \\left( \\frac{5}{2} \\right) \= \\frac{1}{2} \\\\  
N^{(2)}\_{4,2} &= 2 a\_{2,0} N\_{4,0} \\left( \\frac{5}{2} \\right) \= 1  
\\end{align\*}$$

To check these values, recall from Section 2.2 that N4,2(u) \= 12(u \-2)2 on u  \[2, 3). The computation of $$N^{(1)}\_{3,2}\\left( \\frac{5}{2} \\right)$$, $$N^{(2)}\_{3,2}\\left( \\frac{5}{2} \\right)$$, $$N^{(1)}\_{2,2}\\left( \\frac{5}{2} \\right)$$, and $$N^{(2)}\_{2,2}\\left( \\frac{5}{2} \\right)$$ is analogous. 

Based on these observations (and Ex2.4), it is not difficult to develop Algorithm A2.3, which computes the nonzero basis functions and their derivatives, up to and including the *n*th derivative (n ≤ p). Output is in the two-dimensional array, ders. ders \[k\] \[j\] is the kth derivative of the function Ni-p+j, p, where 0 ≤ k ≤ n and 0 ≤ j ≤ p. Two local arrays are used: 

* **ndu \[p+1\] \[p+1\]**, to store the basis functions and knot differences;   
* **a\[2\] \[p+1\]**, to store (in an alternating fashion) the two most recently computed rows ak,jand ak-1, j. 

The algorithm avoids division by zero and/or the use of terms not in the array **ndu\[ \]\[ \]**. 

##### **ALGORITHM A2.3** 

\`\`\`  
DersBasisFuns (i,u,p,n,U,ders)   
{ /\* Compute nonzero basis functions and their \*/  
/\* derivatives. First section is A2.2 modified \*/   
/\* to store functions and knot differences.  \*/   
/\* Input: i,u,p,n,U \*/   
/\* Output: ders \*/   
ndu \[0\] \[0\]=1.0;   
for (j=1; j\<=p; j++)   
{   
    left\[j\]  \= u \- U\[i \+ 1 \- j\];  
    right\[j\] \= U\[i \+ j\] \- u;  
    saved \= 0.0;

    for (r \= 0; r \< j; r++)  
    {						 /\* Lower triangle \*/  
        ndu\[j\]\[r\] \= right\[r \+ 1\] \+ left\[j \- r\];          
        temp \= ndu\[r\]\[j \- 1\] / ndu\[j\]\[r\];  
						 /\* Upper triangle \*/

        ndu\[r\]\[j\] \= saved \+ right\[r \+ 1\] \* temp;                
        saved \= left\[j \- r\] \* temp;  
    }

    ndu\[j\]\[j\] \= saved;  
}  
\`\`\`

We turn our attention now to the last two algorithms, namely computing a single basis function, Ni,p(u), or the derivatives, $$N^{(k)}\_{i,p}\\left(u\\right)$$, of a single basis function. The solutions to these problems result in triangular tables of the form   
![][image6]

Example   
Ex2.5 	Let p \=2, U \= {0,0,0,1,2,3,4,4,5,5,5} and u \=52. The computation of N3,2(52)yields   
![][image7]  
N4,2(52) is obtained from  
![][image8]  
Notice that the position and relative number of nonzero entries in the table depend on *p* and on the position of the 1 in the first column. Algorithm A2.4 computes only the nonzero entries. The value Ni,p(u) is returned in Nip; m is the high index of *U (m \+ 1 knots)*. The algorithm is similar to Algorithm A2.2 in its use of the variables temp and saved. 

##### **ALGORITHM A2.4** 

\`\`\`  
OneBasisFun( p, m, U, i, u, Nip)  
{  
    /\* Compute the basis function Nip \*/  
    /\* Input:  p, m, U, i, u \*/  
    /\* Output: Nip \*/

    if ((i \== 0 && u \== U\[0\]) ||             /\* Special \*/  
        (i \== m \- p \- 1 && u \== U\[m\]))       /\* cases \*/  
    {  
        Nip \= 1.0;  
        return;  
    }

    if (u \< U\[i\] || u \>= U\[i \+ p \+ 1\])       /\* Local property \*/  
    {  
        Nip \= 0.0;  
        return;  
    }

    for (j \= 0; j \<= p; j++)             /\* Initialize zeroth-degree functs \*/  
    {  
        if (u \>= U\[i \+ j\] && u \< U\[i \+ j \+ 1\])  
            N\[j\] \= 1.0;  
        else  
            N\[j\] \= 0.0;  
    }

    for (int k \= 1; k \<= p; k++)             /\* Compute triangular table \*/  
    {  
        if (N\[0\] \== 0.0) saved \= 0.0;  
        else saved \= ((u \- U\[i\]) \* N\[0\]) / (U\[i \+ k\] \- U\[i\]);

        for ( j \= 0; j \< p \- k \+ 1; j++)  
        {  
            Uleft  \= U\[i \+ j \+ 1\];  
            Uright \= U\[i \+ j \+ k \+ 1\];

            if (N\[j \+ 1\] \== 0.0)  
            {  
                N\[j\] \= saved;  saved \= 0.0;  
            }  
            else  
            {  
                temp \= N\[j \+ 1\] / (Uright \- Uleft);  
                N\[j\] \= saved \+ (Uright \- u) \* temp;  
                saved \= (u \- Uleft) \* temp;  
            }  
        }  
    }

    Nip \= N\[0\];  
}  
\`\`\`

Now for fixed *i*, the computation of the derivatives, $$N\_{i,p}^{(k)}(u)$$, for k \= 0, ..., n, n≤p, uses Eq. (2.9). For example, if p \= 3 and n \= 3, then

$$\\begin{align\*}  
N^{(1)}\_{i,3} &= 3 \\left( \\frac{N\_{i,2}}{u\_{i+3} \- u\_i} \- \\frac{N\_{i+1,2}}{u\_{i+4} \- u\_{i+1}} \\right) \\\\  
N^{(2)}\_{i,3} &= 3 \\left( \\frac{N^{(1)}\_{i,2}}{u\_{i+3} \- u\_i} \- \\frac{N^{(1)}\_{i+1,2}}{u\_{i+4} \- u\_{i+1}} \\right) \\\\  
N^{(3)}\_{i,3} &= 3 \\left( \\frac{N^{(2)}\_{i,2}}{u\_{i+3} \- u\_i} \- \\frac{N^{(2)}\_{i+1,2}}{u\_{i+4} \- u\_{i+1}} \\right)  
\\end{align\*}$$

Using triangular tables, we must compute   
![][image9]  
In words, the algorithm is: 

1. compute and store the entire triangular table corresponding to k \= 0;   
2. to get the *k*th derivative, load the column of the table which contains the functions of degree p \- k, and compute the remaining portion of the triangle. 

Algorithm A2.5 computes $$N\_{i,p}^{(k)}(u)$$ for k \= 0, ..., n, n p. The *k*th derivative is returned in ders \[k\]. 

##### **ALGORITHM A2.5** 

##### **\`\`\`**

DersOneBasisFun (p,m,U,i,u,n,ders)   
{  
    /\* Compute derivatives of basis function Nip \*/  
    /\* Input:  p, m, U, i, u, n \*/  
    /\* Output: ders \*/

    if (u \< U\[i\] || u \>= U\[i \+ p \+ 1\])  // Local property  
    {  
        for (k \= 0; k \<= n; k++)  
            ders\[k\] \= 0.0;  
        return;  
    }

    // Initialize zeroth-degree basis functions  
    for ( j \= 0; j \<= p; j++)  
    {  
        if (u \>= U\[i \+ j\] && u \< U\[i \+ j \+ 1\])  
            N\[j\]\[0\] \= 1.0;  
        else  
            N\[j\]\[0\] \= 0.0;  
    }

    // Compute full triangular table  
    for (k \= 1; k \<= p; k++)  
    {  
        if (N\[0\]\[k \- 1\] \== 0.0)  
            saved \= 0.0;  
        else  
            saved \= ((u \- U\[i\]) \* N\[0\]\[k \- 1\]) / (U\[i \+ k\] \- U\[i\]);

        for (int j \= 0; j \< p \- k \+ 1; j++)  
        {  
            Uleft \= U\[i \+ j \+ 1\];  
            Uright \= U\[i \+ j \+ k \+ 1\];

            if (N\[j \+ 1\]\[k \- 1\] \== 0.0)  
            {  
                N\[j\]\[k\] \= saved;  
                saved \= 0.0;  
            }  
            else  
            {  
                temp \= N\[j \+ 1\]\[k \- 1\] / (Uright \- Uleft);  
                N\[j\]\[k\] \= saved \+ (Uright \- u) \* temp;  
                saved \= (u \- Uleft) \* temp;  
            }  
        }  
    }

    ders\[0\] \= N\[0\]\[p\];  // The function value

    // Compute derivatives  
    for (k \= 1; k \<= n; k++)  
    {  
        for (j \= 0; j \<= k; j++)  // Load column  
            ND\[j\] \= N\[j\]\[p \- k\];

        for (jj \= 1; jj \<= k; jj++)  // Compute table of width k  
        {  
            if (ND\[0\] \== 0.0)  
                saved \= 0.0;  
            else  
                saved \= ND\[0\] / (U\[i \+ p \- k \+ jj\] \- U\[i\]);

            for (j \= 0; j \< k \- jj \+ 1; j++)  
            {  
                Uleft \= U\[i \+ j \+ 1\];  
                Uright \= U\[i \+ j \+ p \- k \+ jj \+ 1\];

                if (ND\[j \+ 1\] \== 0.0)  
                {  
                    ND\[j\] \= (p \- k \+ jj) \* saved;  
                    saved \= 0.0;  
                }  
                else  
                {  
                    temp \= ND\[j \+ 1\] / (Uright \- Uleft);  
                    ND\[j\] \= (p \- k \+ jj) \* (saved \- temp);  
                    saved \= temp;  
                }  
            }  
        }

        ders\[k\] \= ND\[0\];  // kth derivative  
    }  
}  
\`\`\`

Finally, note that Algorithms A2.3 and A2.5 compute derivatives from the right if u is a knot. However, Eqs. (2.5), (2.9), (2.10), and others in this chapter could have been defined using intervals of the form u  \[ui, ui+1). This would not change Algorithms A2.2 through A2.5. In other words, derivatives from the left can be found by simply having the span-finding algorithm use intervals of the form (ui, ui+1\], instead of \[ui, ui+1). In the preceding example, with p \= 2 and U \= {0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5}, if u \= 2  then span i \= 3 yields derivatives from the left, and i \= 4 yields derivatives from the right. 

**EXERCISES**   
**2.1.** Consider the linear and quadratic functions computed earlier and shown in Figures 2.5 and 2.6. Substitute u \= 5/2 into the polynomial equations to obtain N3,1(52), N4,1(52), N2,2(52), N3,2(52), and N4,2(52). What do you notice about the sum of the two linear, and the sum of the three quadratic functions?   
**2.2.** Consider the quadratic functions of Figure 2.6. Using the polynomial expressions for N3,2(u), evaluate the function and its first and second derivatives at u \= 2 from both the left and right. Observe the continuity. Does Property P2.5 hold? Do the same with N4,2(u) at u \= 4  
**2.3.** Let U \= {0, 0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5, 5}. How does this change the degree 0, 1, and 2 functions of Figures 2.4-2.6? Compute and sketch the nine cubic basis functions associated with U.   
**2.4**. Consider the function  N2,2(u) of Figure 2.5,  N2,2(u) \= 12u2  on \[0,1),  \-32+3u \- u2 on \[1,2) and 12(3-u)2 on \[2,3). Use Eq. (2.10) to obtain the expressions for the first and second derivatives of  N2,2(u).   
**2.5**. Again consider  N2,2(u) of Figure 2.5. Obtain the first derivatives of  N2,1 and  N3,1 by differentiating the polynomial expressions directly. Then use these, together with Eq. (2.11), to obtain N'2,2.   
**2.6**. Again let p=2, u \=52, and U \= {0, 0, 0, 1, 2, 3, 4, 4, 5, 5, 5}. Trace through Algorithm A2.2 by hand to find the values of the three nonzero basis functions. Trace through Algorithm A2.3 to find the first and second derivatives of the basis functions.   
**2.7.** Use the same *p* and *U* as in Exercise 2.6, with u \= 2\. Trace through Algorithm A2.3 with n \= 1, once with i \= 3, and once with i \= 4\. Then differentiate the appropriate polynomial expressions for the Nj,2 given in Section 2.2, and evaluate the derivatives from the left and right at u \= 2\. Compare the results with what you obtained from Algorithm A2.3.   
**2.8**. Using the same p and U as in Exercise 2.6, let u \= 4\. Trace through Algorithms A2.2 and A2.3 to convince yourself there are no problems with double knots.   
**2.9**. With the same p and U as in Exercise 2.6, let u=1⁄2. Trace through Algorithm A2.5 and compute the derivatives $$N^{(1)}\_{3,2}\\left( \\frac{5}{2} \\right)$$ for k \= 0, 1, 2\.

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAjgAAADzCAYAAACLxWyoAAA930lEQVR4Xu3dCfwc8/3H8YpqnW1SQvxRR9oKjUhQqkLEXUeEUrRaFYm4z1ZVK+6bBFVX6ipRV0Vd1VD3EVF3qbqF0KgrmriK+T9eX4/v+O73N7M7szu7+93Z9/PxmMdvd2Z+u7OzszOf+R6f7xciERERkZL5gj9DREREpNMpwBEREZHSUYAjIiIipaMAR0REREpHAY6IiIiUjgIcERERKR0FOCIiIlI6CnBERESkdBTgiIiISOkowBEREZHSUYAjIiIipaMAR0REREpHAY6IiIiUjgIcERERKR0FOCIiIlI6CnBERESkdBTgiIiISOkowBEREZHSUYAjIiIipaMAR0REREpHAY6IiIiUjgIcERERKR0FOCIiIlI6CnBERESkdBTgiIiISOkowBEREZHSUYAjIiIipaMAR0REREpHAY6IiIiUjgKcAHzhC/oaREREiqQrawAU4IiIiBRLV9YAKMAREREplq6sAVCAIyIiUixdWQOgAEdERKRYurK22dNPP60AR0REpGC6srbZoYceqgBHRESkYLqythkBziWXXOLPFhERkQYowGkzBTgiIiLFU4DTRs8//3y0+uqrK8AREREpmAKcNnryySejb3zjGwpwRERECqYAp43uvfde08B49uzZ/iIRERFpgAKcNrIBjoiIiBRLV9c2UoAjIiLSHLq6ttGgQYOi3r17m8fvvPOOt1RERETqpQCnjb761a9GI0aMMI/HjRvnLRUREZF6KcBpIwKco446yjxWgCMiIlIcBThtpABHRESkORTgtNHee+8djR492jQ0/vOf/+wvFhERkTopwAmAelKJiIgUS1fWACjAERERKZaurAFQgCMiIlIsXVkDoABHRESkWLqyBkABjoiISLF0ZQ2AAhwREZFi6coaAAU4IiIixdKVNQAKcERERIqlK2sAFOCIiIgUS1fWACjAERERKZaurAFQgCMiIlIsXVkDoABHRESkWLqyBkABjoiISLF0ZQ2AAhwREZFi6coaAAU4IiIixdKVNQAKcERERIqlK2sAFOCIiIgUS1fWACjAERERKZaurAFQgCMiIlIsXVkDoABHRESkWLqyBkABjoiISLF0ZQ2AAhwREZFi6coaAAU4IiIixdKVNQAKcERERIqlK2sAFOCIiIgUS1fWACjAERERKZaurAFQgCMiZfToo49GH330kT9bpCV0ZQ2AAhwRKaMpU6ZE77//vj9bpCV0ZQ2AAhwREZFi6coaAAU4IiIixdKVNQAKcERERIqlK2sAFOCIiIgUS1fWACjAERERKZaurAFQgCMiIlIsXVkDoABHRESkWLqyBkABjoiISLF0ZQ2AAhwREZFi6coaAAU4IiIixdKVNQAKcERERIqlK2sAOj3A+e9//+vPEhERaavOvrKWRJYA54c//KE/KzZz5szoL3/5S3Tsscf6i+ry7LPPRgMHDvRnp2L71113XX+2iIhI29S+skrTZQlw1lprregrX/lKtPDCC1fMv//++6OFFloomnfeeaNhw4ZVLKvXUkstZaasLrrooqhPnz7Ra6+95i8SERFpi9pXVmm6LAEOFlhgAbPu+++/XzF/ueWWi7bbbruKefX64IMPom9/+9vRjBkz/EVVbbvtttHSSy8dvfLKK/4iERGRlst2ZZWmyhrgnHTSSWbdc845p2I+Ac4+++xTMa9ekyZNilZffXV/dk2ffvqp2bbnnnvOXyQiItJy2a6s0lRZApzrrrvO/N1zzz3N+i+99FK8bPnll48fN+LNN980r81f1xNPPBFNnTo1euyxx+J5Dz30UMU2gP/91re+VTFPRESkHWpfWaXpsgQ4tpHxRx99ZNY/5phj4mXNDHDuvPNOU/XE/MGDB8fzaQ/085//PH4OSn4U4IiISAhqX1ml6bIEOO466623nnn++OOPR9dff330/PPPV6zHtOOOO6a2o7nsssvigOWFF16I5x988MFm/ocffhjP23LLLaPXX3+9IsC5+uqrzXM/wLGlSyIiIu2mq1EAsgQFAwYMiB9fe+21Ue/eveNgxrrpppvix8xfZpll4ufW7bffHv8PfxdddNF42YQJE8y89957L56H2bNnm/m2lxQBzkorrVSxDhTgiEjI7rrrrrhEevHFF0+sZqfHapEl0euvv37qzWaS0047zZ8lddLVKABZgoKtt9664vkKK6zQI8Ah8LCYzw/ZN2vWrOiee+4xQYwfBCVVUWHs2LFxgEPpDsHWGmusUbEOFOCISMhefvllc/6z507yh7m+9KUvmep30l4UYdy4cdFee+2VKxkqwRVNA6RxuhoFoFZQQDWU75133jH/t/nmm8fzNtxww/jx/vvvX/V1WbbKKqtE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ueWicePG+bMr5C1x2X///aO55547fj506FDzGgQa+POf/xwvo+qKUcoZU6uat956K3rjjTcq5u22227RfPPNZ6rQXLzX888/b/5us8020SmnnJL6GS644AKzfSLdhN8Tv7usWF/y+ctf/hJ997vf9WdLl0i+4khLceFvRoDj9uii/Q6vse666zprfWbNNdc0DZinTZvmL4pdcsklUe/evU2iQR5bBDi8l4tghzY/NsChBMcvQXIpwJEQcFwzTZ482V8U3XHHHfHyWjcCWVBiybhyfslnNV/72tfUniQnvi86gEh3Sr7iSEvZi/99993nLzLuvvvu1OAgDev/85//9GenBhpUJaUFOB9++GF02GGHmXYyv//9783/2wbPSQGO5b5X2vtCAY6EglLPtGP15z//uT+rLgRIvH7eQXPtTQqZ0KW20047zeyv999/318kXaLnr1harlaAc/zxx0dbb721PzvR008/Hf3xj39MDXC++MUvJp68qwU4Fsmy+N/VV189nkeAw7ykO1E/wKFajL+PP/54vI5tg6MAR9pts802izbaaKNoxRVXNMekX32UNyBJs8EGG0Rnn322PzuT2267zbSte/LJJ/1F4qFTxY477ujPli7S80onLWcDgR/84Af+IiNPgEPwYV9vxIgR/mJTFVZvgEMbAJs80KLIvFaAQ0DD3+HDh6cGONdcc43znyKtZwMcMnxzTB5zzDH+KoVYfPHFzY1Ivdg2zglS3UILLWRKv6V79bzSScuRM+fII480bVwwfvx4M/AmHnnkkcSApGjVAhzuZAmwqKKiuJftOemkk+LlPP/Zz37m/MdnCIh+85vfVEw+Piv/r27i0m4ch1SXghIW9zi/6qqrnDUbk/R7prTB3pxQtQIeJ5XU0A6OQEzS3XPPPdEiiyziz5Yu0/OXJi1HqYob4NAwzrb8v/feexNPiEUiuCDAofjb1ldzoreNKWljwzZQ2pJUJcXzueaaK36ex6BBg8z/f/zxx/4ikZbiOKRBPMhEzvNll13WPM9agurimE4K3JN+z9/61rei5557ziyjVyXSAhx+azvvvLM/Wxw333xzdOGFF/qzpcv0/KVJy40dO9a0T3HHheIOkl5Q888/f3xCXG211UwxepEIaDgRULpCoHXnnXea+ZQc/eEPfzCPCXTWWWcdsx3cPSadODbeeGNTipNnrKyn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>

[image2]: <data:image/png;base64,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>

[image3]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPUAAACECAYAAABIz20BAAAZiUlEQVR4Xu2dCbRV0x/HLdPfHCEZIlMS1TJkToaEkFlL0bxQUolVMiZz5jFDocyzqAyVIRJRS0hE5iQZQ8ac//rstX7Xvr+3z7n3vu7p3Xf6fdY6696797nnnPfu+Z49/YblIsMwMsVyusAwjNqNidowMoaJ2jAyhonaMDKGidowMoaJ2jAyhonaMDKGidowMoaJ2jAyhonaMDKGidowMoaJ2jAyhonaMDKGidowMoaJ2jAyhonaMDKGidowMoaJ2jAyhonaMCqIb7/9VheVjInaqDX8/vvv0SOPPJLbNG+88UZe/eOPP653KQvz58+PVltttejWW2/NlX366afunO+++2702WefBa9PWG655aJzzjlHFzv4/sorr6yLS8JEbdQavv76aycI2UaMGJFX//LLL0err756rn7nnXfOqy8XEyZMiBo0aJBXttdee7lzNm/ePGrZsqV7H8fmm28eTZs2TRc7fvzxx2j77bePbrjhBl1VNPFnNowKhZZMhPvQQw/p6miVVVaJHnjgAV1cFtq1axcUbNu2baMjjzxSF+fxxx9/RMcff3y0YMECXZXHbbfd5s7x888/66qiqHp1hlHh0BrSKnPjN2nSJK9u8eLF0dprr51XVk7WW2+9YA9gm222ie67775o0aJF0Z9//qmrHT/99JO75kKi/vfff6NLLrkkmj17tq4qChO1UevYe++93au01j6vv/56NHjw4LyycvHLL7+487Vu3VpX5a5l+PDh7nW//fbTu0S77757leuNY/To0VUeWMVS3BkMo0JgHP3bb7+59wcffLATyUUXXZSrP/PMM6MpU6bkPpcTJsA4nz9BFmLkyJFuP30dlNH9LoaPP/7Y7d+/f39dVRATtVGrYLwpor777rvdjX/BBRe4Liuss846rrVOAxH133//rauiyy+/PNftFlH7D5sPPvggWmONNaKZM2e6z//884+77ssuu8y919BFN1EbmUdmv31RtW/f3pV16tTJfUbUmpNPPtmNeZ944gldlcc777zjjte0adPoxhtv1NWJoqac84CIeuzYsbl6lttkrN+5c2dXP2fOnNyk2NFHH53bVzBRG5lHRO1zxhlnuDImsPr06ROtsMIKuboxY8ZEm222WXTKKadEffv2jerUqRM1atTI+/Z/fPLJJ1G9evVcK//5559Hq666qvuuz4knnpgo6vXXX98Zj3AtfGZiTGDdmnEy1K1bN+/v4D0z9hoTtZF5mPVmHK3h5mfbcMMNo9122y1Xjsh88XTv3r3KQ0E44IADXN28efPcZzmmD8YscaKeO3duNH78+KhHjx7Re++9l1dHF3ullVbKifyll15y+wpbb711lXMBZf369dPFBal6JMOoUBA1wtSIKNhorYWOHTtGhx56aO6zdHtDnHfeeXn7hkSd1P1OgusIDQsEjun3MPxyfQ3FUPo3DKMGYP2X7vE333yjq6IffvghatasmRMAFllxUM8DoBAcg3032GCDvHIR9QknnJBXXgi+ExozQ9euXd0DBRNYn19//dV9z7rfRiZ5+umno969e7ub3O9e+7Ro0SJR1M8//7zbh6WiQlx//fVRw4YNo0mTJuWVf//99+4coXXqOBAr3+HBo+E8u+66qy52MP5ed911C07uhTBRG5kHUdGSA7PQX375pdrjPxiXM6kG77//vqqNXOtdSpf4ueeec5ZmPph/MhTARvyZZ55xm1wfsDzHcpfM6JdK8VdnGLUQRLXjjjtGs2bNcq31xhtvnFsrHjZsWN6+THAhWlpoBM0YXhNn+x3HLrvsUkXUMmGnN+Gvv/5yn5mFrw7FX51h1DK6detWRTjMQgOeVj179nRlX3zxRW72mw0xa6H5HHXUUW5GuxCMleOOkQRr6ltssYUuLprSz2gYtQS6uePGjcvbaLkFLMBE1FOnTs3tQyst70N89913bh27kHvkVlttFa211lq6OBEm43jwxLlmFoOJ2lhmQZQEJagOOHdcd911ujgP6kOz9UngELKkmKiNZZYuXbrookxgojaMjGGiNoyMYaI28iDkDksqpcLa6r333quLczAZFXIxNMqPibpCGDVqVDRx4kRdnAMngI8++siZS1511VW6uiywTIMNclxsLNZbMZoIQXCCpOWbNm3alDwTbFSP+F/BWKrccccdbinjf//7n9t8mGkleiUB94iWyZpqGhARc5999skrY61VrmnFFVd0nk8h9txzzyq20j44QRx22GFBc0mjvJioKwiEm2T0gJ+uRP0oN9OnT3e2xjpo3qBBg1zwADbiXYegu7788ss7v+Uk6NrzYMCG2kiP8N1j1AiIWcLfEi3Th+73mmuumVdWTrbbbrvo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>

[image4]: <data:image/png;base64,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AuakFM9dd91VNV78u8M0qdDosB0gEIkbk1ztoFo5tYNoKcUUiFtttVWaCRtuuKE7x+bW999/XxHuiSeecNe6k0AkbhpsI65A9P9YvkAMp035Y+PfXQQi9vV4H/5H7YL4sWfaDmI1iH48vkB84403gpC/hEWPbnchVh5mwfd14sb+ZTto57NnES2lmAKReLQ0GKOaypRwdRwCkR5qUdxyyy3uOQ4++ODwUspll12WnHPOOW6aKgue+a233gq9Hcz1F10BykxsgbjiiitW/MaF3whZNYzh3O4CxmV5z2oCcbbZZnOW0s8999zwkhMY1OXnn38+vJTSzjobK27i8D+tKN6w/VhyySWdf3cRiBjerZaH1Hddx/Gf82Fkzbd32rU8uI9FShgujk21Z28H0VKKLRD9D7V+gQnSw6p0WKHbST0CkQUgelYqkw+rZWmUt9lmm8wpYAjfsycTWyBiIV1ogYW/6g5VUfyxu5NAVH3KE4g333xzmg8cmYnxYfEJ/lhhz6OddTZG3KyyJY755psv9VO8YdwIRCzPs3CuOyCBmDeLRn2ff/75XbtEuI033rhCKLKwCH+mxfNQPtI+xiarjNpJtJRiCURWbg4YMCB56qmnUr9ll122S8aw7aJdhZBHLYF4yimnJCeeeKI7Jxwfs32OPvpo57/FFltkLvuH8D17MrEE4gknnOC+Ib7yyiupH99qldesJgW2XfD7nnvuScN1OrzPvPPOm9x6663hJbeim5Wir776qtubRthw6lN51MkCkW0BU089dcWsDTMDitufJUAgsgCnSBjFN8oxxxzjPiGxerraAj8JRAYPIU8++WTSr1+/5M4773RxKD/4LCRMIDYJ+1x48BgCkcL2uemmm7pkjARiHkz/jB07NvTO5ZlnnnG947322iu8lMJ+ONLMEogIQlbb0bP873//68KFArF///7O/9prr63w99F7olGkpxNTIIZbcvjmQSNJ/GxHAAnEPOjwsJArJixGqVbnqsG3MO6l7ubB+7AaNIs555zTXf/888+7vUAM9/hStzbZZBMXN4oGWMj25z//2S0+yhKIdBrIa9qiGJAW8eHYP41gawRmonbbbTf3/NNNN114OUUCcfPNNw8vOYG43nrruXOtRN1ss82SMWPGpGGYZsb//PPPT/1CVEYmED1ijhBDgQjs0SN+9VSqZRTTqFxDaNaC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>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAd4AAADPCAYAAABbY7BJAABYi0lEQVR4Xu2dB9QsRbW2JUqSLEmBQw6XKHCRHCXnDJdwCAeRnOQcsgSJkjMiOQcBlRwECV6QIAgKBwEREEUkyw8S5r9PMW9TU1/3dM1M90zPN/tZq1ZPV1X3VFdX166499dqhmEYhmF0ja+FHoZhGIZhlIcJXsMwjArx0EMPhV7GMMMEr2EYxv/x2WefhV5RbLbZZu64zz77BCFf8sgjj9R22GGH2muvvebO33333eQauOuuu9zxqquucse33norCdtggw1qH330kfs9cuRId3zggQeScF1zyCGHJH5cA1tssYU77rvvvu548803u+NJJ51Uu/POO2u/+93vattvv33tb3/7W+3//b//5657/fXXa88884yLd8cdd7j7X3zxxe58+eWXrz322GO1l156yT0DcA3P9oc//KF26KGH1k4++eTalVde6cLEs88+W3vjjTdq6623Xu3f//6383vhhRdqP/zhD93vG2+80R1POOGE2t1331174okn3Dl5tPrqq7vfr776am333Xev/e///q87P/fcc90RxowZk1yz7rrruvz65z//mYQfdthhtRtuuMGlH4444ojaww8/XNt5553d+TrrrOOOhI8aNSq57vrrr69ddtllyTm88sorDefw5JNP1kaPHu1+n3/++UFoOtGC9/e//31t7rnnrs0444zuOPXUU9emn3569xs30UQTJb/lZplllobzb37zm7XJJ5+8NtNMMyV+448/fm2uueZyv0eMGFH79re/7f5jyimndH76D/z9e3Fd2n/Ifetb30ruKb855pij4RruzXOE104wwQRJ3Nlmm80929e+9rWGOErXJJNMkviNO+64yW/iTzrppLUpppjC/cc000yT+M8888wuXeONN15tnHHGSfy5F0cc10w11VQuv3iWWWed1aVrzjnndOFKF9fyHxz5D8LIP/5D99V/8J+6P9dMO+20ybnSxZH/4J3omeUvN9100zWczz777O5ZdK78mmGGGRrihY7/4DrSpf9QmnGkMbwmzVGuQr/Qff3rX3fvPfTv1E044YTuvYf+oZtsssmG+HXTka98Qzrn3VOGKV9+nlNW+LYoXyqPKsP85p1SHvWOfUcZ5V5832GYOXOD4o499thQfA4hWvDS0uCmtELee+89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>

[image6]: <data:image/png;base64,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>

[image7]: <data:image/png;base64,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>

[image8]: <data:image/png;base64,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mU/axLF06dK2uHz99de2HQ4usEGMBPH8hHPKZ599ZkQP23qeoyBduEhRaNSokdlnx44dOstq0KBBTDruuOPMKyLcCPPnzzfHyLT1HAkhhIQnmnrkIJiC4EzOlenh8AKB07FLneXjcc0115hu3Jdffjl092rt2rUjC6oTtGyx/4ABA3QWIYSQXETiSpBE4GTjbDkeDhArBOgOQyKtTScYT0WXLCGEkNxN4kqQRCBQcBrJCfr3729aoWHAebX3axQQNu+2227TZkIIIbmMjBRHTHQnhBBC0kVGiiMhhBCSTiiOhBBCiILiSAghhCgojoQQQoiC4kgIIYQoKI6EkEhMnTrVLFhOSDZDcSSExAVRpnbv3m0SVtLRwfYJyTYojoSQuFSuXNmqXr26VbFixcOOJEVIboB3OCEkLrI4wKuvvkpxJHkC3uGEkNBQHElegXc4ISQ0FEeSV+AdTggJDcWR5BV4hxNCQkNxJHkF3uGEkNBQHElegXc4ISQ0FEeSV+AdToiiRIkSOVL5f/rpp1ajRo202cXll19udejQQZszFoojySvwDicpYfLkydYrr7xi3g8ePFjl/gXE5MYbb7RGjx5ttp9++mlTGaeS66+/3lT8L774os6KTMOGDeOKyIoVK0zEmfPPP19nZSQUR5JX4B1OUsL69evtShXp888/10WsPXv2GBF1ltuxY4cullSKFStmrVmzRpvNtRQvXtyqXbu2SeXLlzfXGgT2adWqlTbHgO8if/782pyRUBxJXoF3OEkZhQoVcgnfxo0bdRFDuirf7t27W3PnztVm69ChQ/Y1/f7779b9999vXoNYu3atKd++fXud5cmWLVtyhUBSHElegXc4SRmoUJ0C6SUGIkRXX321zkoqV111leneXLJkic4yQbdxTe3atbO34/HJJ59YLVu2NJ8nDL/++qs5x759+3RWRoBWPRK6m+X3E1vYz0hIboLiSFICukdRoT733HPWZZddZlewWmjmz59vHGKGDRvmsicbuZ5ly5bpLOvAgQN2vqTNmzfrYjYipl27dtVZgWCfMN2w6aBatWp2wnWWKlXK3p43b54uTkiuh+JIUsLw4cNtcQQiMrt27XKVgzhecMEF1vfff++yJxu5Hi/WrVtn59erV88kvEdrzwt5EIhKzZo1M1YcneDzjxkzRpsJySqi/4MJSQCI4+OPP25vi9jo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>

[image9]: <data:image/png;base64,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>