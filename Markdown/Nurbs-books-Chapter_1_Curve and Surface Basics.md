## *CHAPTER ONE* 

## *Curve and Surface Basics* 

## **1.1 	Implicit and Parametric Forms** 

The two most common methods of representing curves and surfaces in geometric modeling are implicit equations and parametric functions. 

The implicit equation of a curve lying in the *xy* plane has the form *f*(*x*, *y) \= 0\.* This equation describes an implicit relationship between the x and *y* coordinates of the points lying on the curve. For a given curve the equation is unique up to a multiplicative constant. An example is the circle of unit radius centered at the origin, specified by the equation *f(x*, y) \= x2 \+ *y2* \- 1 \= 0 (Figure 1.1). 

In parametric form, each of the coordinates of a point on the curve is represented separately as an explicit function of an independent parameter 

C(*u*) \= (x(u)*, y(*u))  a≤ *u≤* b 

Thus, C(u) is a vector-valued function of the independent variable, u. Although the interval \[a, b\] is arbitrary, it is usually normalized to \[0, 1\]. The first quadrant of the circle shown in Figure 1.1 is defined by the parametric functions 

x(u) \= cos(u) 

*y(u*) \= sin(*u)*      0≤u≤ π/ 2 				(1.1)

Setting t \= tan(u/2), one can derive the alternate representation 

[![][image1]](https://www.codecogs.com/eqnedit.php?latex=x\(t\)%20%3D%20%5Cfrac%7B1%20-%20t%5E2%7D%7B1%20%2B%20t%5E2%7D#0)

[![][image2]](https://www.codecogs.com/eqnedit.php?latex=y\(t\)%20%3D%20%5Cfrac%7B2t%7D%7B1%20%2B%20t%5E2%7D#0) 		0 ≤ t≤1  		(1.2)

Thus, the parametric representation of a curve is not unique.   
(1.1) 

![][image3]  
Figure 1.1. A circle of radius 1, centered at the origin. 

It is instructive to think of C(u) \= (x(*u)*, *y*(u)) as the path traced out by a particle as a function of time; *u* is the time variable, and \[*a, b*\] is the time interval. The first and second derivatives of C(u) are the velocity and acceleration of the particle, respectively. Differentiating Eqs. (1.1) and (1.2) once yields the velocity functions 

[![][image4]](https://www.codecogs.com/eqnedit.php?latex=%5Cmathbf%7BC%7D'\(u\)%20%3D%20\(x'\(u\)%2C%20y'\(u\)\)%20%3D%20\(-%5Csin\(u\)%2C%20%5Ccos\(u\)\)#0)

[![][image5]](https://www.codecogs.com/eqnedit.php?latex=%5Cmathbf%7BC%7D'\(t\)%20%3D%20\(x'\(t\)%2C%20y'\(t\)\)%20%3D%20%5Cleft\(%20%5Cfrac%7B-4t%7D%7B\(1%20%2B%20t%5E2\)%5E2%7D%2C%20%5Cfrac%7B2\(1%20-%20t%5E2\)%7D%7B\(1%20%2B%20t%5E2\)%5E2%7D%20%5Cright\)#0)

Notice that the magnitude of the velocity vector, C'(*u)*, is a constant 

[![][image6]](https://www.codecogs.com/eqnedit.php?latex=%7C%5Cmathbf%7BC%7D'\(u\)%7C%20%3D%20%5Csqrt%7B%5Csin%5E2\(u\)%20%2B%20%5Ccos%5E2\(u\)%7D%20%3D%201#0)

i.e., the direction of the particle is changing with time, but its speed is constant. This is referred to as a *uniform parameterization*. Substituting t \= 0 and t \= 1 into C′(t) yields C′(0) \= (0,2) and C′(1) \= (−1,0), i.e., the particle's starting speed is twice its ending speed (Figure 1.2). 

A surface is defined by an implicit equation of the form *f*(*x*, y, z) \= 0\. An example is the sphere of unit radius centered at the origin, shown in Figure 1.3 and specified by the equation *x2+y2 \+z2 \- 1 \= 0*. A parametric representation (not unique) of the same sphere is given by S(u, v) \= (x(u*, v*), y(*u*, v), z(u, v)), where 

[![][image7]](https://www.codecogs.com/eqnedit.php?latex=x\(u%2Cv\)%20%3D%20%5Csin\(u\)%20%5Ccos\(v\)#0)

[![][image8]](https://www.codecogs.com/eqnedit.php?latex=y\(u%2Cv\)%20%3D%20%5Csin\(u\)%20%5Csin\(v\)#0)

[![][image9]](https://www.codecogs.com/eqnedit.php?latex=z\(u%2Cv\)%20%3D%20%5Ccos\(u\)#0) 		[![][image10]](https://www.codecogs.com/eqnedit.php?latex=0%20%5Cleq%20u%20%5Cleq%20%5Cpi%2C%5Cquad%200%20%5Cleq%20v%20%5Cleq%202%5Cpi#0)			(1.3)

![][image11]  
Figure 1.2. Velocity vectors C'(u) and C′(t) at *u*, *t* \= 0, and 1\. 

Notice that two parameters are required to define a surface. Holding u fixed and varying v generates the latitudinal lines of the sphere; holding v fixed and varying *u* generates the longitudinal lines. 

![][image12]  
Figure 1.3. A sphere of radius 1, centered at the origin. 

Denote the partial derivatives of S(u,v) by Su(u,v) \= (xu(u,v), yu(u,v), zu(u,v)) and Sv(u,v) \= (xv(u, v), yv(u, v), zv(u, v)), i.e., the velocities along latitudinal and longitudinal lines. At any point on the surface where the vector cross product Su  Sv, does not vanish, the unit normal vector, N, is given by (Figure 1.4)   
[![][image13]](https://www.codecogs.com/eqnedit.php?latex=%5Cmathbf%7BN%7D%20%3D%20%5Cfrac%7B%5Cmathbf%7BS%7D_u%20%5Ctimes%20%5Cmathbf%7BS%7D_v%7D%7B%7C%5Cmathbf%7BS%7D_u%20%5Ctimes%20%5Cmathbf%7BS%7D_v%7C%7D#0)				(1.4)

The existence of a normal vector at a point, and the corresponding tangent plane, is a geometric property of the surface independent of the parameterization. Different parameterizations give different partial derivatives, but Eq. (1.4) always yields N provided the denominator does not vanish. From Eq. (1.3) it can be seen that for all v, 0 ≤ v ≤ 2π, Sv(0, v) \= Sv(, v) \= 0, that is, Sv, vanishes at the north and south poles of the sphere. Clearly, normal vectors do exist at the two poles, but under this parameterization Eq. (1.4) cannot be used to compute them. 

Of the implicit and parametric forms, it is difficult to maintain that one is always more appropriate than the other. Both have their advantages and dis- advantages. Successful geometric modeling is done using both techniques. A comparison of the two methods follows: 

Z 

N   
• 

•   
Power Basis Form of a Curve 5 

By adding a z coordinate, the parametric method is easily extended to repre- sent arbitrary curves in three-dimensional space, C(u) \= (*x*(u), y*(u*)*, z*(*u*)); the implicit form only specifies curves in the *xy* (or xz or *yz*) plane; 

It is cumbersome to represent bounded curve segments (or surface patches) with the implicit form. However, boundedness is built into the parametric form through the bounds on the parameter interval. On the other hand, unbounded geometry (e.g., a simple straight line given by *f(x, y*) \= *ax* \+ *by*\+*c*\-0) is difficult to implement using parametric geometry; Parametric curves possess a natural direction of traversal (from C(a) to C(b) if *a* ≤ u ≤ *b*); implicit curves do not. Hence, it is easy to generate ordered sequences of points along a parametric curve. A similar statement holds for generating meshes of points on surfaces; 

The parametric form is more natural for designing and representing shape in a computer. The coefficients of many parametric functions, e.g., Bézier and B-spline, possess considerable geometric significance. This translates into intuitive design methods and numerically stable algorithms with a distinctly geometric flavor; 

. The complexity of many geometric operations and manipulations depends   
greatly on the method of representation. Two classic examples are: 

compute a point on a curve or surface \- difficult in the implicit form; given a point, determine if it is on the curve or surface \- difficult in the parametric form; 

In the parametric form, one must sometimes deal with parametric anoma- lies which are unrelated to true geometry, An example of this is the unit sphere (see Eq.\[1.3\]). The poles are parametric critical points which are algorithmically difficult, but geometrically the poles are no different than any other point on the sphere. 

We are concerned almost exclusively with parametric forms in the remainder of this book. More details on implicit and parameteric forms can be found in standard texts (\[Faux81; Mort85; Hoff89; Beac91\]).   
\=   
S, 

1.2   
Power Basis Form of a Curve 

Su 

Figure 1.4. Partial derivative and unit normal vectors of S(u, v).   
Clearly, by allowing the coordinate functions x(u), *y(*u), and z(u) to be arbi- trary, we obtain a great variety of curves. However, there are trade-offs when implementing a geometric modeling system. The ideal situation is to restrict ourselves to a class of functions which 

⚫ are capable of precisely representing all the curves the users of the sys- 

tem need; 

⚫ are easily, efficiently, and accurately processed in a computer, in particu- 

lar: 

the computation of points and derivatives on the curves is efficient;   
6 Curve and Surface Basics 

numerical processing of the functions is relatively insensitive to float- ing point round-off error; 

the functions require little memory for storage; 

⚫ are simple and mathematically well understood. 

A widely used class of functions is the polynomials. Although they satisfy the last two criteria in this list, there are a number of important curve (and surface) types which cannot be precisely represented using polynomials; these curves must be approximated in systems using polynomials. In this section and the next, we study two common methods of expressing polynomial functions, power basis and Bézier. Although mathematically equivalent, we will see that the Bézier method is far better suited to representing and manipulating shape in a computer. 

An nth-degree power basis curve is given by 

The ai   
n 

C(u) \= (x(u), y(u), z(u))   
Σau   
0 ≤ u≤1   
(1.5) 

(*xi*, Yi, Zi) are vectors, hence 

*n*   
n   
i=0 

x(u) \= \[¤¡u\* y(u) \= \[μ   
Στι 

i=0   
\=Σy;ui z(u) \= Σziu2 

i=0   
n 

i=0 

In matrix form Eq. (1.5) is 

1 

*U* 

C(u) \= \[ao ai   
an\]   
\= \[a\] \[*u2*\]   
(1.6) 

(We write a row vector as the transpose of a column vector.) 

Differentiating Eq. (1.5) yields 

C(i)(u)|u=0   
ai   
i\! 

where C(1)(u)|u=o is the ith derivative of C(u) at u 0\. The n \+ 1 functions, {*u*}, are called the basis (or blending) functions, and the {a} the coefficients of the power basis representation. 

Given *up*, the point C(u。) on a power basis curve is most efficiently computed using Horner's method 

⚫ for degree 1: C(uo) \= à1uo \+ão 

2: C(uo) \= (a2uo \+ a1) uo \+ão   
The general algorithm is 

ALGORITHM A1.1 

Horner1(a,n,u0,C)   
Power Basis Form of a Curve 7 

{ /\* Compute point on power basis curve. 

/\* Input: a,n,u0 \*/ 

/\* Output: C \*/ C a\[n\]; 

for (i=n-1; i\>=0; i--) 

} 

Examples   
C   
C\*u0+a\[i\];   
\*/ 

Ex1.1 n 1\. C(u)   
а \+ à1u*,* 0 ≤ *u* ≤ 1, is a straight line segment between the points ao and a \+ a1 (Figure 1.5). The constant C′(u) \= a1 gives the direction of the line. 

Ex1.2   
n \= 2\. In general, C(u) \= a+a1u+a1⁄2ú2, 0 ≤ u≤ 1, is a parabolic arc between the points a and a \+ a1 \+ a2 (Figure 1.6). This is shown by 1\. transforming C(u) into the *xy* plane (C(*u*) does lie in a unique plane); 2\. setting xx0 \+ *x1u* \+ x2u2 and *y* 30 \+ 31 \+2, and then eliminating u and *u2* from these equations to obtain a second-degree implicit equation in x and *y*; 

3\. observing that the form of the implicit equation is that of a parabola. 

Notice that the acceleration vector, C′′(u) \= 2a2, is a constant. There are two special (degenerate) cases of interest, both occurring when the vector a2 is parallel to the initial tangent vector, a1 (when X192 \= X2Y1). In this case, the tangent vector does not turn, i.e., we get a straight line. The vector a2 can point in the same direction as a1 (Figure 1.7a), or in the opposite direction (Figure 1.7b). In Figure 1.7b, a1 \+2a2u0 \= 0 for some 0 ≤ uo ≤ 1 (velocity goes to zero, the particle stops), and a portion of the line segment is retraced in the opposite direction. 

a1   
ao \+ ai 

degree 

ao   
degree \= n : C(uo) \= ((· · · (anuo \+ an-1) uo \+ an−2) uo \+ ·   
\+ ao   
Figure 1.5. Straight line segment, C(u) \= ao \+ à1u.   
8 Curve and Surface Basics 

مة   
ai 

ao \+ a \+ a2 

a1 \+ 2a2   
مة 

a2   
a1 

C(uo) 

ao \+ a \+ az 

(b)   
Bézier Curves 9 

Figure 1.6. Parabolic arc, C(u) 

Ex1.3   
ao \+ à1u+a2u2. 

www.w   
n 3\. The cubic, C(u) à \+ à ̧μ \+ à ̧μ2 \+ aзu3, is a very general curve; it can be a truly *twisted* three-dimensional curve, not lying in a single plane (Figure 1.8a); it can have an inflection point (Figure 1.8b); a cusp (Figure 1.8c); or a loop (Figure 1.8d). A twisted curve results if a0, a1, a2, a3 do not lie in a unique plane. An inflection point on a planar curve is defined as a point where the curve is smooth (no cusp) and the tangent line at that point passes through the curve. This implies a change in the turning direction of the curve. At an inflection point, either C"(u) \= 0, or C'(u) || C" (u). A necessary (but not sufficient) condition for a cusp at u \= uo is C'(uo) \= 0 (velocity zero). Conditions for a loop to occur are also known (see \[Ferg66, 67, *69,* 93; Forr70, 80; Wang81; Ston89; Su89\]). 

21 

(a)   
ao \+ a \+ a2 

ao 

a2 

Figure 1.7. a1 and a2 parallel. (a) Same direction; (b) opposite directions.   
Figure 1.7. *(Continued*.*)* 

1.3   
Bézier Curves 

Next we study another parametric polynomial curve, the Bézier curve. Since they both use polynomials for their coordinate functions, the power basis and Bézier forms are mathematically equivalent; i.e., any curve that can be represented in one form can also be represented in the other form. However, the Bézier method is superior to the power basis form for geometric modeling. Our presentation of Bézier curves is rather informal; for a more rigorous and complete treatment the reader should consult other references \[Forr72; Bezi72, 86; Gord74a; Chan81; Fari93; Yama88; Hosc93; Roge90\]. 

The power basis form has the following disadvantages: 

•   
it is unnatural for interactive shape design; the coefficients {a} convey very little geometric insight about the shape of the curve. Furthermore, a designer typically wants to specify end conditions at both ends of the curve, not just at the starting point; 

algorithms for processing power basis polynomials have an algebraic rather than a geometric flavor (e.g., Horner's method); 

numerically, it is a rather poor form; e.g., Horner's method is prone to round-off error if the coefficients vary greatly in magnitude (see \[Faro87, 88; Dani89\]). 

The Bézier method remedies these shortcomings. 

An nth-degree Bézier curve is defined by 

n 

C(u) \= ΣBi,n(u)Pi 

i=0   
0 \<u≤ 1   
(1.7)   
10 Curve and Surface Basics 

*X* 

*y*   
2 

Twisted cubic 

(a)   
*Y* 

C'(u)||C"(*u*) 

or 

C"(u) \= 0 

Inflection point 

(b)   
*X* 

Figure 1.8. Cubic curves. (a) Three-dimensional twisted; (b) inflection point; (c) cusp; (d) loop. 

The basis (blending) functions, *{Bi*,n(u)}, are the classical nth-degree Bernstein polynomials (\[Bern12; Lore86\]) given by 

n\!   
*Bi*,n(u) \=   
*u2* (1 — *u*)n—i   
i\!*(n* − i)\!   
Loop 

Figure 1.8. (*Continued*.*)* 

Ex1.5 

(1.8) 

The geometric coefficients of this form, {P}, are called *control points*. Notice that the definition, Eq. (1.7), requires that u € \[0, 1\]. 

Examples 

Ex1.4   
n   
www.   
1 u and *B1*,1(*u)*   
www.m   
1\. From Eq. (1.8) we have *Bo*,1(u)   
u; and Eq. (1.7) takes the form C(u) \= (1 − u) Po \+ u P1. This is a straight line segment from Po to P1 (see Figure 1.9).   
C'(u) \= 0   
Cusp 

(c) 

(d)   
Bézier Curves 11 

n \= 2\. From Eqs. (1.7) and (1.8) we have C(u) *2u* (1 \- u) P1 \+ u2 P2. This is a parabolic arc from Figure 1.10). Notice that 

•   
(1 \- *u*)2 Po \+ 

Po to P2 (see 

⚫ the polygon formed by {Po, P1, P2}, called the *control polygon*, ap- 

proximates the shape of the curve rather nicely; 

•   
Po \= C(0) and P2 \= C(1); 

the tangent directions to the curve at its endpoints are parallel to 

P1 \- Po and P2 – P1 (this is derived later); 

the curve is contained in the triangle formed by Po P1 P2.   
12 Curve and Surface Basics 

Pi 

P2   
P1 \= C(1)   
Bézier Curves 13 

Po \= C(0) 

Figure 1.9. A first-degree Bézier curve. 

Ex1.6 n \= 3\. We have C(u) \= (1−u)3 Po+3u(1−u)2 P1 \+*3u2*(1−u) P2+u3 P3. Examples of cubic Bézier curves are shown in Figures 1.11a to 1.11f. Notice that 

⚫ the control polygons approximate the shapes of the curves;   
• 

•   
Po= C(0) and P3 \= C(1); 

www.   
⚫ the endpoint tangent directions are parallel to P1 \- Po and P3 \- P2; 

• convex hull property: the curves are contained in the convex hulls of their defining control points (Figure 1.11c); 

•   
variation diminishing property: no straight line intersects a curve more times than it intersects the curve's control polygon (for a three- dimensional Bézier curve, replace the words 'straight line' with the   
Po 

Figure 1.11. Cubic Bézier curves.   
(a)   
P3 

word 'plane'). This expresses the property that a Bézier curve follows its control polygon rather closely and does not wiggle more than its control polygon (Figure 1.11f); 

initially (at *u* \= 0\) the curve is turning in the same direction as PoP1 P2. At u \= 1 it is turning in the direction P1 P2 P3; 

• a loop in the control polygon may or may not imply a loop in the The transition between Figure 1.11e and Figure 1.11f is a curve with a cusp.   
curve. 

Pi   
Pi 

P2   
P3 o 

Po   
Po \= C(0)   
P2 \= C(1) 

(b) 

Figure 1.10. A second-degree Bézier curve.   
Figure 1.11. (*Continued*.*)*   
14 Curve and Surface Basics 

Pi   
P3 

P2   
Po 

Ро 

(c) 

P2 

Pi   
Q 

P2   
P2   
Pi 

(e)   
י 

Pi   
Bézier Curves 15 

P3 

Po P3 

(d) 

Figure 1.11. *(Continued*.*)* 

Ex1.7   
*n*   
wwwww   
6\. Figure 1.12 shows a sixth-degree, closed Bézier curve. The curve 

is smooth at C(0) ( \= C(1)) because P1 \- Po is parallel to P6 \- P5. By smooth we mean that the tangent vectors at *u*   
0 and *u* 1 have the same direction. 

In addition to the previously mentioned properties, Bézier curves are invariant under the usual transformations such as rotations, translations, and scalings;   
Figure 1.11. (*Continued*.*)*   
Ро   
P3 

(f) 

that is, one applies the transformation to the curve by applying it to the control polygon. We present this concept more rigorously in Chapter 3 for B-spline curves (of which Bézier curves are a special case). 

In any curve (or surface) representation scheme, the choice of basis functions determines the geometric characteristics of the scheme. Figures 1.13a-d show the basis functions *{Bi*,n(u)} for n \= 1,2,3,9. These functions have these properties: 

P1.1   
nonnegativity: *Bi*,n(u) \> 0 for all *i,* n and 0 ≤u ≤1;   
16 Curve and Surface Basics 

P2 

Pi 

Po \= P6   
P3 

P5   
PA 

Figure 1.12. A smooth, closed, sixth-degree Bézier curve. 

Σ20   
P1.2 partition of unity: *Bi*,n(u) \= 1 for all 0 ≤ *u* ≤ 1;   
\< \< 

P1.3   
*Bo*,n(0) \= *Bn*,n(1) \= 1; 

P1.4 

U-   
*Bi*,n(u) attains exactly one maximum on the interval \[0, 1\], that is, at 

\= i/*n;* 

P1.5   
symmetry: for any *n*, the set of polynomials {*Bi*,n(u)} is symmetric with respect to u — 1/2; 

B1,1   
Bo,1   
Bo,2 

B1,2 

(b)   
B2,2   
Bézier Curves 17 

Figure 1.13. *(Continued*.) 

P1.6 

P1.7   
—   
recursive definition: *B1*,n(u) \= (1 − *u*)*Bi,*n−1(u) \+ *uBi*−1,n−1(u) (see Figure 1.14); we define *Bi*,n(u) \= 0 if i \< 0 or *i \>* n; 

derivatives: 

*Bi*,n(u)   
*dBi*,n(*u) du* 

with   
n*(Bi*\-1,n−1(u) — *Bi,*n−1(u)) 

*B-*1,n-1(u) \= *Bn*,n−1(*u*) \= 0 

Figure 1.15a shows the definition of *B2,5*, and Figure 1.15b illustrates all the cubic derivative functions. 

B0,3 

B2,3   
B1,3 

(a)   
(c)   
Figure 1.13. The Bernstein polynomials for (a) n \= 1; *(*b) n \= 2; (c) n \= \= 3; *(d)* n 9\.   
Figure 1.13. (*Continued*.*)*   
B3,3   
18 Curve and Surface Basics 

B0,9   
B9,9 

B8,9   
B1,9 

Figure 1.13. (*Continued*.)   
(d) 

From Eq. (1.8) we have *Bo*,o(u) quadratic Bernstein polynomials are   
1\. Using property P1.6, the linear and 

*Bo*,1(u) \= (1-*u*)B0,0(u) \+ *uB-*1,0(u) \= 1 − *u* 

*B1*,1(u) \= (1-*u)*B1,0(u)+*uBo*,o(u) \= *u* 

*Bo,2*(u) \= (1 – u)*Bo*,1(u)+*uB\_*,1(u) \= (1 – u)2 

B1,2(u) \= (1 − u*)*B1,1(u) \+ uB0,1(u) \= (1 − u)u \+ u(1 − u) \= 2u(1 − *u*) *B2,2*(u) \= (1 − u)*B2,1*(u) \+ *uB1,1*(u) *\=* u2   
B'2,5 

B2,5 

B2,4   
B1,4 

B1.3   
(a) 

B'3,3 

B'2.3   
Bézier Curves 19 

B0,2 

B1,3   
(1 \- u)   
U 

B1,2 

Figure 1.14. The recursive definition of the Bernstein polynomial, *B1*,3(u).   
B0,3 

(b) 

Figure 1.15. Derivatives. (a) The derivative B2,5(u) in terms of B1,4(u) and *B2,4*(u); (b) the derivatives of the four cubic Bernstein polynomials, *Bó*,3(u); *Bí*,3(u); B2,3(u); B3,3(*u*). 

Property P1.6 yields simple algorithms to compute values of the Bernstein polynomials at fixed values of u. Algorithm A1.2 computes the value *Bi*,n(u) for fixed *u.* The computation of B1,3 is depicted in Table 1.1.   
Bézier Curves 21   
20 Curve and Surface Basics 

ALGORITHM A1.2 

Bernstein(i,n,u,B) 

{ /*\** Compute the value of a Bernstein polynomial. \*/ 

/\* Input: i,n,u \*/ 

/\* Output: B \*/ 

for (j=0; j\<=n; j++) 

www   
temp\[j\] 0.0; 

\=   
temp \[n-1\] 1.0; 

u1   
1.0-u; 

for (k=1; k\<=n; k++) 

for (j-n; j\>=k; j--) 

B \= 

}   
/\* compute the columns \*/ 

/\* of Table 1.1 \*/ 

/\* in a temporary array \*/ 

temp\[j\] \= u1\*temp \[j\] \+ u\*temp\[j-1\]; temp\[n\]; 

Algorithm A1.3 computes the n \+ 1 nth-degree Bernstein polynomials which are nonzero at fixed u. It avoids unnecessary computation of zero terms. The algorithm is depicted in Table 1.2 for the cubic case. 

ALGORITHM A1.3 

AllBernstein(n,u,B) 

Table 1.1. The computation of B1,3.   
Table 1.2. Computation of all the cubic Bernstein polynomials. 

B-1,0   
B-1,1 

B0,1 

1 \= B0,0 

B1,1 

B1,0 

B2,1   
B0,2 

B1,2 

B2,2   
B0,3 

B1,3 

B2,3 

B3,3 

0 \- *B*\-2,0 

0 \= *B*\-1,0 

1 \= B0,0 

0 \= B1,0   
*B*\-1,1 

Bo,1 

B1,1   
B-1,2 

B0,2 

B1,2 

B2,2   
/\*   
{ /\* Compute all nth-degree Bernstein polynomials. \*/   
Input: n,u \*/   
B0,3   
/\*   
Output: B (an array, B\[0\],....... ,B\[n\])   
\*/ 

B\[0\]   
www   
1.0; 

u1   
www   
1.0-u; 

B1,3 

B2,3   
for (j=1; j\<=n; j++) 

{ 

saved \= 0.0; 

for (k=0; k\<j; k++) 

{ 

temp   
www   
B\[k\]; 

B\[k\]   
saved+u1\*temp; 

saved   
www   
u\*temp; 

} 

B\[j\] \= saved; 

} 

} 

Algorithm A1.4 combines A1.3 and Eq. (1.7) to compute the point on an nth-degree Bézier curve at a fixed *u* value.   
22 Curve and Surface Basics 

ALGORITHM A1.4 

PointOnBezierCurve (P,n,u,C)   
{ /\* Compute point on Bezier curve.   
/\* Input: P,n,u \*/   
/\* Output: C (a point) \*/ 

AllBernstein (n,u,B) 

C \= 0.0;   
\*/ 

/\* B is a local array \*/ 

for (k=0; k\<=n; k++)   
C \= C \+ B\[k\] \*P \[k\] ; 

}   
Using property P1.7, it is easy to derive the general expression for the deriva- tive of a Bézier curve 

C'(u)   
N 

Bi‚n(u)Pi   
n 

i=0   
*Bin* (u) Pi   
*du*   
i=0 

n   
\= Σn(*Bi*\-1,n−1(u) – *Bi*,n−1(u)) Pi 

i=0 

n-1 

\= nΣBi,n-1   
\-п   
www. 

Bi,n-1(u)(Pi+1 − Pi) 

i=0   
(1.9) 

From Eq. (1.9) we easily obtain formulas for the end derivatives of a Bézier 

curve, e.g. 

C′(0) \= n(P1 – Po) 

C′(1) \= n(P2 \- Pn-1)   
C"(0) \= *n*(n − 1)(Po \- 2P1 \+ P2)   
\- 

C′′(1) \= *n(n* − 1)(P2 − 2Pn-1+ Pn-2) (1.10) 

Notice from Eqs. (1.9) and (1.10) that 

•   
the derivative of an nth-degree Bézier curve is an (*n* − 1)th-degree Bézier curve; 

the expressions for the end derivatives at *u* O and *u* (due, of course, to the symmetry of the basis functions);   
1 are symmetric 

the kth derivative at an endpoint depends (in a geometrically very intuitive manner) solely on the k \+ 1 control points at that end. 

Let n \= 2 and C(u) \= Σ20 *B¡*,2(u) P1. Then 

C(u) \= (1-u)2 Po \+ 2u(1 − *u*) P1 \+ u2 P2   
Poo   
P1,0   
P2,0 

*น*   
\= 2/5   
P1 

P1,1   
Bézier Curves 23 

P2 

Figure 1.16. Obtaining a point on a quadratic Bézier curve by repeated linear inter- polation at uo \= 2/5. 

www.m   
Assuming a fixed *u* \= uo and letting P1,0 (1 uo) Po+uo P1, P1,1 (1 uo) Pi+*uo* P2, and P2,0 \= (1 − uo) P1,0 \+ uo P1,1, it follows that C(uo) \= P2,0. The situation is depicted in Figure 1.16, and the cubic case is shown in Figure 1.17. 

Denoting a general nth-degree Bézier curve by Cn(Po,........., Pn), we have 

Ca(Po,..., Pn) \= (1 − u)Cn-1(Po,..., Pn-1) 

\+uCn-1(P1,..., Pn)   
(1.11) 

P1,0   
P2   
P1,1   
Pi 

P2,1 

P2,0 

P3,0   
P1,2 

(1 − u) ( (1 − u) Po \+ u P1 ) \+ u ( (1 − u) P1 \+uP2 

linear   
linear 

Thus, C(u) is obtained as the linear interpolation of two first-degree Bézier curves; in particular, any point on C(u) is obtained by three linear interpolations.   
Po   
U   
2/5   
P3 

Figure 1.17. A point on a cubic Bézier curve by repeated linear interpolation at uo   
2/5.   
24 Curve and Surface Basics 

This follows from the recursive definition of the basis functions (see P1.6). Fixing *u* up and denoting P; by Po,i, Eq. (1.11) yields a recursive algorithm for computing the point C(uo) \= Pn,o (uo) on an nth-degree Bézier curve, i.e. 

Pk,i(Uo) \= (1 − uo) Pk−1,¿(Uo) \+*uo* Pk−1,i+1(Uo) for   
n   
J *k* 

i 0,   
1, 

n*\-*k (1.12)   
} 

Equation (1.12) is called the *de Casteljau Algorithm* (see \[Boeh84; deCa86, 93\]). It is a corner cutting process (see Figures 1.16 and 1.17) which yields the triangular table of points shown in Table 1.3. 

ALGORITHM A1.5 

deCasteljaul (P,n,u,C)   
{ /\* Compute point on a Bézier curve \*/ 

/\* using deCasteljau \*/   
\*/   
/\* Input: P,n,u /\* Output: C (a point) 

for (i=0; i\<=n; i++) 

Q\[i\]   
\=   
P\[i\]; 

for (k-1; k\<=n; k++) 

for (i=0; i\<=n-k; i++)   
\*/ 

/\* Use local array so we do not \*/ /\* destroy control points \*/ 

Q\[i\] (1.0-u)\*Q\[i\] \+ u\*Q\[i+1\]; 

C \= Q\[0\]; 

}   
Pa 

We conclude this section with a comparison of the Bézier and power basis methods. Clearly, the Bézier form is the more geometric of the two. Equation (1.10), together with the convex hull and variation diminishing properties, makes 

Table 1.3. Points generated by the deCasteljau algorithm. 

Po 

P1,0 

P.   
P2,0 

P1,1 

P2 

:   
Rational Bézier Curves 25 

Bézier curves more suitable for interactive curve design. The control points give 

the designer a more intuitive handle on curve shape than do the power basis coefficients. Furthermore, the deCasteljau algorithm is less prone to round-off error than Horner's algorithm. This is intuitively clear when one considers that the deCasteljau algorithm is simply repeated linear interpolation between points, all of which lie in the vicinity of the curve. The only disadvantage of the Bézier form is that point evaluation is less efficient (see Algorithms A1.1, A1.4, and A1.5, and Exercise 1.13 later in the chapter). 

1.4   
Rational Bézier Curves 

Next we introduce the concepts of rational curves and homogeneous coordinates. To illustrate these concepts we give a brief introduction to rational Bézier curves. These curves are special cases of rational B-spline curves and as such are treated more completely and rigorously in subsequent chapters. 

Although polynomials offer many advantages, there exist a number of im- portant curve and surface types which cannot be represented precisely using polynomials, e.g., circles, ellipses, hyperbolas, cylinders, cones, spheres, etc. As an example, we give a proof that the unit circle in the *xy* plane, centered at the origin, cannot be represented using polynomial coordinate functions. To the contrary, let us assume that 

*x*(u) \= ão \+*α1u* \+· \+ *anun* 

y*(*u) *\= bọ* \+ *b1u* \+ \+*bnun* 

Then x2 \+ *y2* \- 1 \= 0 implies that   
... 

0 \= (ao \+ *a1u* \+ ··· \+ *anu2*)2 \+ (bo \+ *b1u* \+ ··· \+ b1u2)2 – 1 

(*a2* \+ *b2* − 1\) \+ 2(a0a1 \+ *bob1*)u \+ *(a2* \+ *2a0a2* \+b2 \+ *2bob2*)u2 

\+...+*(*a22-1+*2an*\-2αn \+ b2-1 \+ 2bn-2bn)u2   
\+b32-1 

\+2(*anan*\-1 \+ bnbn−1)u2n−1 \+ *(a2* \+ *b2)*u2n   
\+*(a2*\+*b2)*u2n   
*2n*\-2 

This equation must hold for all *u,* which implies that all coefficients are zero. Starting with the highest degree and working down, we show in n steps that all 

0 and *b2* \= 0 for 1 ≤ i ≤ n.   
Pn-1,0 

*ai*   
:   
Pn,0   
C(uo) 

Step   
Pn-1,1   
: 

1\. a2+b2 \= 0 implies *an*   
bn   
0\.   
:   
Pn-2 

P1,n-2   
2\. a2-1+*2an*\-2an+b2-1+2bn-2bn \= 0 and Step 1 imply that a2-1+b2 \= 0   
which implies that *an*\-1   
*bn*\-1 : 0\.   
Pn-1   
P2,n-2 

P1,n-1 

Pn   
26 Curve and Surface Basics 

n. a2+2a0a2+ *b2* \+ *2bŋb2* \= 0 and Step n 1 imply that a \+ b2 \= 0, which 

implies that *a1 b1* 0\.   
............. 

Thus, x(u) \= ao and *y(*u) \= *bo*, which is an obvious contradiction.   
It is known from classical mathematics that all the conic curves, including the circle, can be represented using *rational functions*, which are defined as the ratio of two polynomials. In fact, they are represented with rational functions of the form   
*X*(*u)* x(u) \=   
W (u)   
*Y*(*u*)   
*Y*(*u*)   
W(u)   
(1.13) 

where *X(u*), *Y*(u), and *W*(u) are polynomials, that is, each of the coordinate functions has the same denominator. 

Examples 

Ex1.8 Circle of radius 1, centered at the origin   
Rational Bézier Curves 27 

Define an nth-degree *rational Bézier curve* by (see \[Forr68; Pieg86; Fari83, 89\]) 

n 

*Bin* (u)wi Pi 

C(u) \=   
i=0   
0 ≤ u≤ 1   
n   
(1.14) 

*Bin*(u)wi 

i=0 

The Pi (Xi, Yi, Zi) and B¿n(u) are as before; the w; are scalars, called the *weights.* Thus, *W*(u) Σo *Bin*(u)w*;* is the common denominator function. Except where explicitly stated otherwise, we assume that w; \> 0 for all i. This ensures that W*(u*) \> 0 for all u € \[0, 1\]. We write 

where   
n 

C(u) \= ΣRi,n(u)P; 

*Ri,n*(u)   
i=0 

*Bin*(u)wi 

n 

ΣBj,n(u)wj   
0≤u≤1   
(1.15) 

1-*u2* x(*u)* \=   
1 \+ u2   
y*(u)*   
2u 1 \+ u2 

Ex1.9 Ellipse, centered at the origin; the y-axis is the major axis, the x-axis is the minor axis, and the major and minor radii are 2 and 1, respectively 

x*(u*)   
1 u2 1 \+ *u2*   
*y*(*u)*   
*4u* 1+u2 

Ex1.10 Hyperbola, center at P 

x(u) \=   
*y(*u):   
(0, 4/3); the y-axis is the transverse axis 

\-1+*2u* 1+*2u \- 2u2*   
4u(1 \- *u)* 1+*2u \- 2u2* 

The lower branch (with vertex at P \= (0, 2/3)) is traced out for 

1€ (1-13 1+13)   
*u* E   
} 2   
√3 

2 

Ex1.11 Parabola, vertex at the origin; the y-axis is the axis of symmetry 

x(u) น *y(*u) \= u2 

Notice that the parabola does not require rational functions. The reader should sketch these functions. For the circle equations it is easy to see that for any *u,* (x(u), *y*(u)) lies on the unit circle centered at the origin 

*น*   
2 2   
(x(u))2 \+ (v(u))2 \= ('—-—=— u2 )2 \+   
(1+ ( 24 )   
u2   
*2u* 

1 \+ 

1 \- *2u2* \+ *u1* \+ *4u2* 

(1 \+ u2)2   
2 

(1 \+ *u2*)2   
1   
(1 \+ u2) 2   
*j*\=0 

The *Ri*,n(u) are the rational basis functions for this curve form. Figure 1.18a shows an example of cubic basis functions, and Figure 1.18b a corresponding cubic rational Bézier curve. 

The *Ri*,n(u) have properties which can be easily derived from Eq. (1.15) and the corresponding properties of the *Bin*(*u)*: 

P1.8   
nonnegativity: *Ri*,n(u*)* \> 0 for all *i,* n and 0 ≤ *u* ≤ 1; P1.9 partition of unity: Σ?\_0 *Ri*,n(u) \= 1 for all 0 ≤ *u* ≤ 1; P1.10 Ro,n(0) \= *Rn*,n(1) \= 1;   
i=0 

P1.11 *Ri,*n(u) attains exactly one maximum on the interval \[0, 1\]; 

P1.12 if   
Wi 1 for all i, then R¿‚n(u) *\=* Bin (u) for all i; i.e., the *B¿*,n(u) are a special case of the *R¿*,n(u). 

These yield the following geometric properties of rational Bézier curves: 

convex hull property: the curves are contained in the convex hulls of their defining control points (the P;);   
P1.13 

P1.14 transformation invariance: rotations, translations, and scalings are ap- 

plied to the curve by applying them to the control points; 

P1.15 variation diminishing property: same as for polynomial Bézier curves (see 

previous section); 

P1.16 endpoint interpolation: C(0) \= Po and C(1) — Pn; P1.17 the kth derivative at u   
0 (u   
1\) depends on the first (last) k \+ 1 control points and weights; in particular, C'(0) and C'(1) are parallel to P1- Po and Pn \- Pn-1, respectively; 

P1.18 polynomial Bézier curves are a special case of rational Bézier curves.   
28 Curve and Surface Basics 

Ro,3 

R1,3   
R2,3   
R3,3 

(a) 

W1 \= 3   
W2   
7 

Pi   
P2 

Ро 

Wo   
1 

(b)   
P3 

*W3*   
1   
У 

(0,1) 

*y*   
Rational Bézier Curves 29 

(1,0) 

(a)   
៧   
*I* 

W2 \= 2 

P2   
Pi 

*ພ*1   
1 

*wo* 

X 

Po 

(b) 

Figure 1.18. Rational cubic. (a) Basis functions; (b) Bézier curve. 

Example 

Ex1.12 Let us consider the rational Bézier circular arc. 

\- *u2 2u* 1 \+ u2' 1 \+ u2   
C(u) \= (x(u), y(u)) \= (1 \+   
0 \<u≤1 

represents one quadrant of the unit circle, as shown in Figure 1.19a. We now derive the quadratic rational Bézier representation of this circular arc. Clearly, from P1.16 and P1.17, Po (1,0), Pi P2 \= (0,1). For the weights we have 

2   
(1,1), and 

*W*(u) \= 1 \+ u2 \= \[*B¡,2*(u)w; \= (1 − *u)2wo* \+ 2u(1 − u)w1 \+ *u2w2* 

i=0   
Figure 1.19. Representation of the unit circle. (a) *x*(u) (1 − u2)/(1 \+ u2) and y(u) (2u)/(1+u2) for one quadrant; (b) the Bézier representation corresponding   
to Figure 1.19a (wo \= 1, w1 \= 1, w2 \= \= 2). 

wwwwww.   
*w2*   
Substituting u 0 yields wo   
1, and u 1 yields w2 \= 2\. Finally, substituting u \= 1/2 yields *5/4* 1/4w0+ 1/2w1 \+ 1/4w2, and using wo \= 1 and w22 yields w1 \= 1 (see Figure 1.19b). 

Rational curves with coordinate functions in the form of Eq. (1.13) (one com- mon denominator) have an elegant geometric interpretation which yields efficient processing and compact data storage. The idea is to use *homogeneous coordi- nates* to represent a rational curve in n-dimensional space as a polynomial curve in *(*n+1)-dimensional space (see \[Robe65; Ries81; Patt85\]). Let us start with a point in three-dimensional Euclidean space, P (*x*, y, z). Then P is written *(wx, wy,* wz, w) \= *(X, Y*, *Z, W*) in four-dimensional space, w 0\. Now   
as Pw   
Rational Bézier Curves 31   
30 Curve and Surface Basics 

P is obtained from Pw by dividing all coordinates by the fourth coordinate, *W*, i.e., by mapping Pw from the origin to the hyperplane *W* 1 (see Figure 1.20 for the two-dimensional case, P (x, y)). This mapping, denoted by *H*, is a perspective map with center at the origin 

P \= *H*{P} \= *H*{(*X, Y*, *Z,W*)}   
X *Y Z* 

'   
\>   
{( W W W XY, 2\)   
if *W* 0 

0   
(1.16)   
direction (*X, Y,* Z) if W 

Notice that for arbitrary x, y, *z*, w1, w2, where w1 \#w2 

*H*{Pw1} \= *H*{(w1x, w1y, w1z, w1)} \= (*x*, y*, z*) 

*H*{(w2x, way, w2z, w2)} \= *H*{PW2} 

Now for a given set of control points, {P}, and weights, {w;}, construct the weighted control points, Pw \= (WiXi, WiYi, WiZi, w1). Then define the *nonrational* (polynomial) Bézier curve in four-dimensional space 

*n* 

Cw(u) \= Bin (u) Pw 

i-0 

*W* 

(*X,Y,W*)   
Then, applying the perspective map, *H*, to C*(u*) yields the corresponding rational Bézier curve of Eq. (1.14) (see Figure 1.21), that is, writing out the coordinate functions of Eq. (1.17), we get 

n 

*X*(u) \= Σ *Bin(*u)W;Xi 

i=0 

n 

*Z(*u) \= ΣBin(u)W; Zi 

i=0   
n   
*Y*(u) \= Σ *Bin(U)W¡Yi* 

i=0 

n 

*W*(u) \=ΣBin(u)wi 

i=0 

Locating the curve in three-dimensional space yields 

n 

Bin(u)WiXi   
*X*(u)   
i-0   
x(u) \=   
*W(u)*   
n 

Σ *Bin* (u)wi 

i=0 

(1.17)   
*Y*(*u)*   
i=0   
*y(u*):   
\=   
*W*(u)   
n 

ΣBin (u)*wiyi* 

n 

ΣBin(u)wi 

i-0 

n 

ΣBi,n(u)wi Zi 

n 

ΣBin(u)Wi 

i=0   
z(*u*) \=   
*Z*(*u*) *W*(u)   
i=0 

X   
8   
(x, y)   
W   
1 

*Y* 

Figure 1.20. A representation of Euclidean points in homogeneous form.   
Using vector notation, we get 

C(u) \= (x(u), *y*(u), z(*u*)) \=   
n 

Bi,n(u)Wi(Xi, Yi, Zi) 

i=0 

n 

*n* 

i=0 

n   
Σ Bin (u)wi 

i=0 

Bin(u)wi Pi 

Σ Bin (u)ω; 

i=0   
(1.18)   
32 Curve and Surface Basics 

*X*   
Pu 

*X*   
P   
W 

P 

P2/ 

P1   
Po 

P3   
P 

సా   
*Y* 

*X*   
Po \= P 

P1 \= Pw   
W   
Rational Bézier Curves 33 

P2 

*Y*   
P 

Figure 1.21. A geometric construction of a rational Bézier curve.   
Y 

For algorithms in this book we primarily use the form given by Eq. (1.17), and an analogous form for rational B-spline curves. Thus, nonrational forms are processed in four-dimensional space, and the results are located in three- dimensional space using the map *H.* We refer interchangeably to either C(*u)* or C(u) as the rational Bézier (or B-spline) curve, although strictly speaking, C(u) is not a rational curve. 

Examples 

Ex1.13 Let us return to the circular arc of Figure 1.19b. We have Po   
\=   
(1,0), 

P1 (1,1), P2 (0,1), and wo 1, wi 1, w2 2\. Hence, for Eq. (1.17) the three-dimensional control points are P (1,0,1), PW (1, 1, 1), and P \= (0,2,2). Then Cw(u) \= (1-u)2 P+2u(1-u) P+ u2 P is a parabolic arc (nonrational), which projects onto a circular arc on the *W* \= 1 plane (see Figure 1.22).   
2 

Let up be fixed. Since Cw(*u*) is a polynomial Bézier curve, we use the deCasteljau algorithm to compute C (uo); subsequently, C(uo) \= *H*{Cw(uo)}. Thus, we apply Eq. (1.12) to the P 

P(uo) \= (1 − uo) P–   
(1 − *uo*) P-1,i \+uo Pk−1,i+1   
for   
J k   
1,   
... 3   
*n* 

i \= 0,...,n \- *k*   
Figure 1.22. A homogeneous representation of a circular arc. 

" 2   
Ex1.14 Let us apply Eq. (1.19) to compute the point at u \= 1/2 on the rational 

Bézier circular arc of Example 1.13. The arc is given by Cw(*u*) (1 − u)2 Pv \+ 2u(1 − u) P2 \+ u2 P, where P (1,0,1), Pw \= (1,1,1), P2 \= (0,2,2). The triangular set of generated points is shown in Table 1.4. Then C(11⁄2) \= *H*{Cw(11⁄2)} \= *H*{(3⁄44, 1, 5/4)} — (3/5, 4/5). 

Now let us compute the point using the other representations we have developed. Let 

C(u) \=   
(1 \- u2) (1 \+ u2)' (1 \+ u2)   
(*2u)* 

Table 1.4. Generation of the point C(2) on the circular arc. 

(1,0,1) 

(1, 1, 1\) 

(0,2,2)   
(1/1) 

3 3 

2'2   
(14)   
(1)- \~-(1)   
1, 

(1.19)   
34 Curve and Surface Basics 

1.5   
Then   
2(글)   
· ( ) \- ( \- § 3 ) \- ( \-4) 

Using Eq. (1.17) 

Cw   
2   
1+   
(1)3 

c\* (}) \= Σ Ba({}) Pr –   
i-0   
Bi. 

2   
1+   
(1) 

(1,0,1)+2   
1   
− (1 − ( ) )\* (1.0.1) \+ 2( ) (1 − ( )) (1,1,1) 

\+(+)\*(0,2,2) 

· 1   
\= (1,0,1)+(1,1,1)+(0,2,2) \= (1) 

Projecting yields (3/5, 4/5). Equations (1.18) and (1.15) yield the same result. 

Finally, we note that C(11⁄2) \= (3⁄45, 4/5) is not the midpoint of the circular arc in the first quadrant; i.e., the parameterization is not uniform (see Section 1.1). The point (3/5, 4/5) is more than half the arc length from the starting point. This is intuitively correct, since by differentiating C(u) one can see that the starting speed is twice the end speed. 

Tensor Product Surfaces 

The curve C(*u)* is a vector-valued function of one parameter. It is a mapping (deformation) of a straight line segment into Euclidean three-dimensional space. A surface is a vector-valued function of two parameters, u and v, and represents a mapping of a region, R, of the *uv* plane into Euclidean three-dimensional space. Thus it has the form S(u*,* v) \= (x(u, v), *y(u, v*), z(*u*, v)), (*u*, *v*) € R. There are many schemes for representing surfaces (see \[Hosc93; Pieg89a, 93\] and the many references cited in \[Pieg89a\]). They differ in the coordinate functions used and the type of region R. Probably the simplest method, and the one most widely used in geometric modeling applications, is the *tensor product* scheme. This is the method we use in the remainder of this book. 

The tensor product method is basically a bidirectional curve scheme. It uses basis functions and geometric coefficients. The basis functions are bivariate func- tions of *u* and *v*, which are constructed as products of univariate basis functions.   
Tensor Product Surfaces 35 

The geometric coefficients are arranged (topologically) in a bidirectional, n × m net. Thus, a tensor product surface has the form 

where   
n   
m 

S(u, v) \= (x(u, v), y(u, v), *z*(*u*, v)) \= ΣΣfi(u)9; (v)bi,j 

i=0 j=0 

 ́bi,j \= (*Xi,j*, Yi,j, Zi,*j)* 

0 ≤ *u*, v ≤ 1   
(1.20) 

Note that the (*u*, v) domain of this mapping is a square (a rectangle, in general). Note also that S*(u,* v) has a matrix form 

S(u,v) \= \[ fi(u)\]1 \[b1,j\] \[ 9; (v)\] 

where \[f;(u)\] is a (1) × (*n* \+ 1\) row vector, \[*g*;(v)\] is a (*m* \+ 1\) × (1) column vector, and \[bi,j \] is a (n \+ 1\) × (m \+ 1\) matrix of three-dimensional points.   
As an example we consider the power basis surface 

n   
m 

s(u,v) \= ΣΣa¿¡u1ví *\=* \[u2\]” *\[*a¿‚;\]\[v3\] 

i=0 *j*\=0 

We have fi(u)   
\= *u*\* and *g;* (v) *{u'v3*}. If we fix *u* \= uo, then 

where   
m   
ai,j \= (*Xi*,j, Yi,j, *Zi,j)* 0 ≤ *u*, v ≤ 1 (1.21) 

v3, and the basis functions are the products, 

*m*   
Cuo (v) \= S(uo, v) \= Σ (£ a¡¡ už) v2 \= Σ b;(uo) vì 

j=0 

n 

bj(uo) \= Σai, już 

i=0   
ai,j 

j=0   
(1.22) 

is a power basis curve lying on the surface, S(u, v). Similarly, C„(u) is a power basis curve lying on S(*u,* v); and the curves Cu, (v) and Cv (u) intersect at the surface point, S(uo,vo). These curves are called *isoparametric curves* (or *isocurves*). Cu。(v) is called a v *curve,* С...(u) a u *curve* (see Figure 1.23). 

Equation (1.21) can be written as 

S(u, v) \= {a0,0 \+ a0,1v+ão,2v2 \+   
\+ao,*mvm* 

bo 

\+u{a1,0 \+ a1,1v+a1,2v2 \+ ·   
\+ a1*,*mvm} 

bi 

\+a2,mvm*}*   
\+u2{a2,0 \+ a2,1v+a2,2v2 \+ 

:   
b2 

\+ u^{an,0 \+ an,1V \+ an‚2v2 \+ · 

\= bọ \+ b1u *\+* b2u2 \+   
bn 

\+bnun   
\+an,mvm}   
36 Curve and Surface Basics 

Z 

S(0,1) 

Cuo(v),   
Cvo (u)   
S(1,1) 

(S(uo,vo)| 

S(0,0) 

S(1,0)   
X   
Tensor Product Surfaces 37 

Nonrational Bézier surfaces are obtained by taking a bidirectional net of con- trol points and products of the univariate Bernstein polynomials 

n   
m 

S(u, v) \= ΣΣ *Bi*,n(u*)Bj*,m(v)Pi,j 

i=0 *j*\=0   
0 ≤ u*,* v ≤1   
(1.23) 

The basis function B0,2(*u*)B1,3(v) is shown in Figure 1.24a, and Figure 1.24b shows a quadratic × cubic Bézier surface. 

For fixed *u uo* 

n   
m 

Cu。 (v) \= S(uo, v) \= ΣΣBi‚n(U0)Bj,m(v)Pi,j 

i=0 *j*\=0 

m   
*B2m* (U) (B1,n(40) P2,5)   
Pi,j   
ย 

*y* 

(uo, vo) 

น 

Figure 1.23. A tensor product surface showing isoparametric curves. 

The terms in the braces are simple polynomials that can be evaluated by the Horner Algorithm (A1.1), yielding bo, b1,..., bn. Using the bs and reapplying the algorithm, we obtain the point on the surface. Thus we have Algorithm A1.6. 

ALGORITHM A1.6 

Horner2(a,n,m,u0,vo,S) 

{ /\* Compute point on a power basis surface. 

/\* Input: a,n,m,u0,v0 \*/ 

/\* Output: S \*/ 

for (i=0; i\<=n; i++)   
\*/ 

Horner1 (a\[i\]\[\],m,vo,b\[i\]); /\* a\[i\]\[\] is the ith row \*/ Horner1(b,n,u0,S); 

} 

Algorithm A1.6 is typical of the algorithms for tensor product surfaces. They can usually be obtained by extending from the curve algorithms, often by process- ing the *n* (or *m*) rows of coefficients (as curves) in one direction, then processing one or more rows in the other direction. 

Differentiating Eq. (1.21), we obtain 

n   
m 

i-1   
Su(u, v) \= ΣΣ i a¿‚j u1—1ñ3 

i=1 *j*\=0   
U 

Notice that for fixed (uo,vo), Su(uo,vo)   
n   
m 

S, (u, v) \=Σjāju3vi-*1*   
i=0 j=1 

www.   
C' (uo) and S, (uo, Vo) \= Cuo (vo).   
The normal vector, N, is computed using Eq. (1.4).   
n 

where   
Q;(uo) \= ΣBi,n(U0) Pi,j 

i=0   
j=0 

m 

ΣBj,m(v)Q;(uo) 

j=0 

*j*\=0,...,m   
(1.24) 

is a Bézier curve lying on the surface. Analogously, Cvo (u) \= Σï-0Bin(u)Q¿(vo) is a Bézier *u* isocurve lying on the surface. 

1 

B1,3(v) 

0   
1 

*Bo*,2(u) 

B0,2(u*)*B1,3(v)   
1 

น 

(a) 

Figure 1.24. (a) The Bézier tensor product basis function, *Bo*,2(u)B1,3(v); (b) a quadratic × cubic Bézier surface.   
38 Curve and Surface Basics 

As is the case for curves, because of their excellent properties Bézier surfaces are better suited for geometric modeling applications than power basis surfaces. In particular, 

• 

• 

• 

•   
nonnegativity: *B¿‚n*(u)*Bj,m*(v) ≥ 0 for all *i, j*, *u, v*; 

m   
partition of unity: Eizo Eo Bin(*u)B,,*m(v) \= 1 for all u and v;   
i=0 

S(u*,* v) is contained in the convex hull of its control points; 

transformation invariance; 

the surface interpolates the four corner control points; 

when triangulated, the control net forms a planar polyhedral approximation to the surface. 

It is interesting to note that there is no known variation diminishing property for Bézier surfaces *(*see \[Prau92\]). 

The deCasteljau algorithm (A1.5) is also easily extended to compute points on a Bézier surface. Refer to Eq. (1.24) and Figure 1.25*.* Let (uo, vo) be fixed. For fixed jo, Qjo (0) \= 0 *Bi*,n(uo) Pi,jo is the point obtained by applying the deCasteljau algorithm to the *jo* row of control points, i.e., to {Pi,jo}, i \= 0, ......., *n*. Therefore, applying the deCasteljau Algorithm *(m* \+ 1\) times yields Cu, (v); and applying it once more to Cu, (v) at v vo yields Cuo (vo)   
vo yields Cu。(vo) \= S(uo,vo). This process requires   
Tensor Product Surfaces 39 

linear interpolations (see Exercise 1.21). By symmetry, we can compute Cv。(u) first (n \+ 1 applications of deCasteljau) and then compute C, (o) \= S(*uo*, vo). This requires   
*m(*m \+ 1\)*(n* \+ 1\)   
\+   
*n(n* \+ 1\) 

2   
2   
(1.26) 

linear interpolations. Thus, if n \> m compute C, (u) first, then C。 (uo); oth- erwise, compute Cu。 (v) first, then Cu。 (vo). 

ALGORITHM A1.7 

deCasteljau2 (P,n,m,u0, vo,S)   
{ /\* Compute a point on a Bézier surface \*/ 

/\* by the deCasteljau.   
\*/ 

/\* Input: P,n,m,u0, v0 \*/ 

/\* Output: S 

if (n \<= 

{   
m) 

for (j=0; j\<=m; j++) /\* P\[j\] \[\] is jth row \*/ 

deCasteljau1 (P\[j\] \[\],n,u0,Q\[j\]); 

deCasteljau1(Q,m,vO,S); 

} 

else 

Po,0 

*x*   
n(*n* \+ 1)(*m* \+ 1\)   
m*(m* \+ 1\)   
\+   
2   
2 

Po,1 

Figure 1.24. (*Continued*.*)*   
Z 

Po,3 

P2,3 

P2,0 

(b)   
\- མ   
P2,2 

У   
(1.25)   
{ 

for (i=0; i\<=n; i++) 

Po,0   
2 

Po,1 

Q1 (uo) 

 ́S(uo,vo)   
Po,3   
Q3 (20) 

P2,3   
Cuo 

(Q2 (*10*) 

P2,2 

Qo (20) 

20 

P2,0 

Figure 1.25. The deCasteljau algorithm for a Bézier surface.   
У   
Tensor Product Surfaces 41   
40 Curve and Surface Basics 

deCasteljau1 (P\[\] \[i\],m,vo, Q\[i\]); 

deCasteljaul(Q,n,u0,S); 

} } 

We define a *rational Bézier surface* to be the perspective projection of a four- dimensional polynomial Bézier surface (see \[Pieg86; Fari89\]) 

n   
m 

sTM (u, v) \= ΣΣBin(u)*B ̧*,m(v) P1⁄4,j 

i=0 j=0 

n   
m 

ΣΣB¿*,n*(u)*B ̧*,m(v)Wi‚j Pi‚j 

i=0 j=0   
and   
S(u*,* v) — *H*{STM (*u,*v)} \=   
n   
m 

where   
wwwww.w   
ΣΣBin(u)B ̧,m(v)Wi,j 

i=0 j=0 

n   
m 

ΣΣ *Ring* (u, v) Pinj 

i=0 *j*\=0 

*Ri*,*j* (u, v)   
n   
Bi,n(u)Bj,m(v)wi,j 

m 

ΣΣBr,n(u*)Bs*,m(v)Wr,s 

T-08-0   
(1.27) 

(1.28) 

Notice that the *R2,;(u,* v) are rational functions, but they are not products of other basis functions. Hence, S(u, v) is not a tensor product surface, but Sw*(u,* v) is. As with curves, we generally work with Eq. (1.27) and project the results. Figure 1.26a shows a rational basis function, and Figure 1.26b de- picts a quadratic × cubic rational Bézier surface. Compare these figures with Figures 1.24a and 1.24b. 

Assuming wi,*j* \> 0 for all i and j, the properties listed previously for nonra- tional Bézier surfaces (and the product functions Bin (u)*Bj*,m(v)) extend natu- rally to rational Bézier surfaces. Furthermore, if w¿,j 1 for all i and *j*, then *Ri,j*(u,v) \= *Bi*,n(*u*)*Bj*,m(v), and the corresponding surface is nonrational. 

Example 

Ex1.15 Let us construct a cylindrical surface patch. From Section 1.4 we know 

that   
2 

Cw (u)   
www.   
ΣBi,2(u) Py 

i-0   
0   
B1,3(v)   
1 

Bo,2(*u*) 

Ro,1 (*u*, v) 

200,1 \=5 

(a) 

Figure 1.26. (a) The rational basis function *Ro*,1(u,v) (with wo,1 weights equal to one); (b) a quadratic × cubic rational Bézier surface. 

where 

and   
2   
2   
1 

5 and all other 

C (u) \= ĹB1,*2*(u)P0\_and\_Cï' (u) \= \[*B;*,*2*(u)P%, 

i=0   
i=0 

{P} \= {(1, 1, 0, 1), (1, 1, 1, 1), (2, 0, 2, 2)} 

{P} \= {(−1, 1, 0, 1), (−1, 1, 1, 1), (−2, 0, 2, 2)} 

are circular arcs in the x \= 1 and \-1 planes, respectively (see Figure 1.27). A linear interpolation between C and C yields a cylin- drical surface, i.e. 

2 1 

sw (u,v) \= ΣΣBi,*2*(u*)B*;,1(v)Puj 

นก   
i=0 j=0 

For fixed u \= *uo*, Cu (v) \= Σ;-0 *Bj*,1(v) Qu(uo) is a straight line seg- ment from C(uo) to Cu(uo) parallel to the x-axis. For fixed v \= vo, C \= Sw(u,vo) \= Eizo *Bi,2*(u) Qu (vo) is a circular arc in the plane   
00   
2 

X (1 − vo)(1) \+ vo(−1) \= 12vo. Now let us compute the point S(1/2, 1/2), using Algorithm A1.7. Note that n \> m. First obtain C-1/2(u) 

for {P} \= {(0, 1, 0, 1), (0, 1, 1, 1), (0, 0, 2, 2)}, is a circular arc in the *yz* plane. Using translation (P1.14, Section 1.4)   
(1,1,0,1) 

(-1,1,0,1)   
(0,1,0,1) \= Qu (vo)   
42 Curve and Surface Basics 

*200,1* \-5   
Po,1 

Po,0   
Z 

Po,3 

P2,2   
P2,3   
2 

P2,0   
P2,1 

Cu= 1/2(v) 

P1,0   
· 

Cv=11⁄2 (u)   
P1,1 

Po,1 

У   
Exercises 43 

Figure 1.26. (b) *(Continued*.)   
P2,0 

(b) 

(1, 1, 1, 1\) 

(0, 1, 1, 1\) \= Quo (vo) 

(-1, 1, 1, 1\) 

(2,0,2,2) 

(-2,0,2,2)   
(0,0,2,2) \= Q(vo) 

Now C1 \= 1/2(u) \= Σ2=*0* B1,2(u) QUo (vo) is the circular arc in the *yz* plane. Then 

(0, 1, 0, 1\) 

(0, 1, 1, 1\) 

(0,0,2,2) 

And projecting yields 

S   
(0,1,1,1) 

1 3 3 

2'2' 2 

*H*   
3   
ว   
3   
1,   
Sw 

$ (1, 2\) \- {(0, 2, 1, 3)} \= (0, 1, 1\)   
}   
I   
P0,0 

Figure 1.27. A cylindrical surface patch as a rational Bézier surface. 

EXERCISES 

1.1. Consider the two parametric representations of the circular arc given by Eqs. (1.1) and (1.2). Using Eq. (1.1), compute the curve point at u \= π/4 and, using Eq. (1.2), the point at t 1/2. Explain the results. 

1.2. Compute the acceleration vector, C"(u), for Eq. (1.1). Explain the result. 1.3. Using trigonometric functions, give a parametric definition of the bounded sur- face of 

• a right circular cone, with apex at the origin and axis of symmetry along the z-axis; 

•   
the cone is opening upward, and is bounded above at z \= 2 by the circle with radius   
www   
1\. 

Modify Eq. (1.2) to get another representation of the same cone. Compute the first partial derivatives, S, and S,, of the trigonometric representation. What are the values of these derivatives at the apex of the cone? 

1.4.   
u2),   
Consider the parabolic arc C(u) (*x(*u), y(u))   
www.   
(-1 · u \+ 2u2, *−2u* \+ u2 

0 ≤ u≤ 1\. Sketch this curve. The curve is rotated and translated by applying the transformations to the functions x(u) and *y*(u). Apply the two transformations 

(1) 90° rotation about the origin. The rotation matrix (applied from the left) is 

\[-\] 

(2) translation with the vector (-1,-1).   
Exercises 45   
44 Curve and Surface Basics 

The implicit equation of the underlying parabola is x2 \- *4xy \+* 4y2 \- 4x − *y* − 5 — 0\. Sketch this curve. Apply the previous rotation and translation to this equation. Hint: let I, be the transformed coordinates. Find expressions x \= *f*(x, y) and *y g*(*x*,*y)* and substitute these into the implicit equation to obtain the implicit equation of the transformed parabola. 

1.5. Determine formulas for the number of additions and multiplications necessary to compute a point on an nth-degree three-dimensional power basis curve. 

1.6. Construct a cubic power basis curve with a loop. Hint: think about what end- points and end derivatives, C′(0) and C′(1), are necessary. 

1.7. Construct a cubic power basis curve with a cusp. Hint: think about C'(*u*) and C"(u). Sketch what x′*(u*), *y’*(u), *x'*(u), and *y′′*(u) need to *look* like as functions of *u*. Determine a suitable C”(*u)*, and then integrate to obtain C′(u) and C(u). 

1.8. Construct a cubic power basis curve with an inflection point. 

1.9. Let C(u) (x(u), y(u)) (1 \+ u 2u2 \+ u3, 1 2u \+ u3), −1 ≤ u ≤ 1\. Let *u* \= 2v- 1\. Derive the curve C(v) by substituting 2v 1 for u in C(u). What degree is the curve C(v)? Compute C(u) for u \-1,0,1. Compute C(v) for v \= 0, 2, 1\. What can you say about the curves C(u) and C(v)? C(v) is called a *reparameterization* of C(u*)*. 

1.10. Check the property P1.7 of the Bernstein polynomials for the cases n \= 2 and 

\= 3\.   
n 

1.11. It is sometimes necessary to reverse a curve, i.e., given C1(u), 0 ≤ *u* ≤ 1, produce C2(v), 0 ≤ v ≤ 1, such that the two curves are the same geometrically, but C1(0) C2(1) and C1(1) \= C2(0). How would you do this using the Bézier form? The power basis form? 

1.12. Consider the *xy* planar cubic Bézier curve given by the control points Po (0,6), P1 \= (3,6), P2 \= (6,3), P3 (6,0). Compute the point C(13) using the deCasteljau algorithm. Compute the same point by using Eqs. (1.7) and (1.8) directly, i.e., evaluate the basis functions at u= 1/3 and multiply by the appropriate control points. 

1.13. Determine formulas for the number of additions and multiplications necessary to compute a point on an nth-degree three-dimensional Bézier curve using the deCasteljau algorithm, A1.5, and algorithm A1.4. Compare the results with Exercise 1.5 (the Horner algorithm). 

1.14. For given *n*, row vector *\[Bo*,n(u), ... ... ..., Bn,n(u)\] can be written as \[1, u,   
‚*u*"\]*M*, where *M* is an (n \+ 1\) × (n \+ 1\) matrix. Thus, a Bézier curve can be written in matrix form, C(u) \= \[u1\]TM *M*\[P\]. Compute the matrices *M* for n 1,2,3. Notice that setting 

\[a\] \= *M*\[P\] yields the conversion of a Bézier curve to power basis form. Assuming 0 ≤ *u* ≤ 1, \[Pi\] \= *M*\~1\[a;\] gives the conversion from power basis to Bézier form. 

1.15. Compare this with Exercise 1.9. It is also possible to define a Bézier curve on a parameter interval other than \[0, 1\]. This is equivalent to reparameterizing a Bézier curve. Let 

n 

C(u) \= Σ *Bin* (U) Pi   
u Є \[0,1\] 

i=0 

Let vЄ *\[a*,b\]. Then *u* \= (v — a)/(*b − a*). Substitute this equation into Eq. (1.8) and derive this expression for the reparameterized curve   
n 

1   
n\!   
C(v) \=   
*(b \- a*)n   
i\!(n \-- i)\!   
i=0   
· (v *— a)*' (*b −* v)”—i Pi 

It is interesting to note that the control points do not change, only the basis functions. Reparameterization of the power basis form changes the geometric coefficients but not the basis functions. 

1.16.   
Consider the circle 

C(u) \=   
*u2 2u* 1 \+ u2' 1 \+ u2 

Determine which ranges of the parameter u yield which quadrants of the circle. Do these equations yield the entire circle? What can you say about the parameterization? 

1.17. Consider the following rational cubic Bézier curve in the *xy* plane: Po \= (0,6), 

Pi   
· (3,6), P2 \= (6,3), P3 \= (6,0), wo 4, w1 1, wz 1, w3 4\. Compute the 

point C(23) by expanding the deCasteljau table. 

1.18. What characteristic is it of the rational functions we are using that allows us to use the homogeneous coordinate representation? Why is this representation advantageous? 

1.19. Find the rational Bézier representation of the circular arc in the second quad- rant, i.e., determine the P; and wi. Hint: use symmetry and check your result by showing that *(x*(u))2 \+ *(y*(u))2 \= 1 for all u € \[0,1\]. 

1.20. The circular arc in the first quadrant is also given by the equation 

C(u)   
1+(√2-2)u+ (1 \- √2)u2   
√2 u ((√2 − 2)u \+ 2\)   
2 

1 \+ (√2 − 2)u \+ (2 − √2 )u2 1 1+ (√2 − 2)u \+ (2 − √2)*u2*   
wwwww 

―   
\- 

Determine the rational Bézier representation corresponding to these equations. Hint: the P; must be the same as before – (1,0), (1, 1), (0,1); Why? Compute the weights wi by equating polynomials and substituting u \= 0, 12, 1, as done previously. Compute the point C(2), using any method. What is interesting about C(11⁄2)? 

1.21. Derive Eqs. (1.25) and (1.26). Hint: use the formula 1+2+ \+n- n(n+1)/2. 1.22. For the cylindrical surface example (Ex1.15) compute the control points Q (uo) for the isocurve Cu。=1(v). 

3 and *m* \= 2\. Consider the nonrational Bézier surface defined by the   
1.23. control net   
Let n 

{P1,0} \= {(0, 0, 0), (3, 0, 3), (6, 0, 3), (9, 0, 0)} 

{P,1}={(0, 2, 2), (3, 2, 5), (6, 2, 5), (9, 2, 2)} 

{Pi,2} \= {(0,4,0), (3, 4, 3), (6, 4, 3), (9, 4, 0)} 

a. sketch this surface;   
❤ 

b. use the deCasteljau algorithm to compute the surface point S(11⁄2, 11⁄2); c. fix uo 1/2 and extract the Bézier representation (control points) of the curve   
Cuo=1/2(v).   
46 Curve and Surface Basics 

1.24. Let 

m 

S(u, v) \-ΣΣBin(U*)*B ̧,m(v) Pi,j 

and assume that Po,o= P1,0   
i-0 3-0 

Pn,0. How does this affect S(*u*, v), the derivatives (1,0,0) for i \= 0, 1, 2 2\. What type of surface do   
Su(*u*, v) and S, (u, v), and the curves C。 (*u*)? Assume that Pi,o 

in Example Ex1.15, with W0,0 1, W1,0 you get?   
1,   
and w2,0   
w 

1.25. The prerequisite for this problem is Exercise 1.14. The rational Bézier surface (Eq. \[1.27\]) has a matrix form 

Sw(u, v) \= \[*Bi*,n(u)\]† \[P;,;\] \[Bj,m(v)\] \= \[u' \]T *Mn* \[P%; \] *M„*\[w\] 

where \[u\] and \[v3\] are vectors, M2 is an (n+1) × (n+1) matrix, *M1⁄2* is a (m+1) × *(m* \+ 1\) matrix, and \[P\] is an (n \+ 1\) × *(m* \+ 1\) matrix of four-dimensional points. Write this form down explicitly for the cylindrical surface example, Ex1.15. Using this matrix form, compute the point Sw(11⁄2, 11⁄2), and then project to obtain S(11⁄2, 1/2). There is no direct matrix form for S(u, v); why not? 

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGMAAAAoBAMAAAAYilkJAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMARIm73e92MmarzVQiEJktzfMGAAAALUlEQVR4XmP8z0Ai+MiELkIYjGohFYxqIRWMaiEVjGohFYxqIRWMaiEV0EcLAIgXAkCq18M2AAAAAElFTkSuQmCC>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGEAAAAlBAMAAACg4ZrqAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEFSr3e/NiTJEIplmu3ak7QEkAAAAKUlEQVR4XmP8z0Aa+MiELkIQjOogHozqIB6M6iAejOogHozqIB6MXB0A5K4COm8uNIUAAAAASUVORK5CYII=>

[image3]: <data:image/png;base64,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>

[image4]: <data:image/png;base64,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>

[image5]: <data:image/png;base64,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>

[image6]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAPsAAAAgBAMAAAAmpRN5AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAELvvZjKJIqvNRN12mVSTYmz0AAAANElEQVR4Xu3NIQEAIADAMKB/WRKAJwAzn7z5PAPa6y1/tYfaQ+2h9lB7qD3UHmoPtYfaQxdYIwIw4K30fgAAAABJRU5ErkJggg==>

[image7]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKcAAAARBAMAAABKq6G3AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMARIm73e92MmarzVQiEJktzfMGAAAAI0lEQVR4XmP8z0B18JEJXYQaYNRQ6oNRQ6kPRg2lPhjhhgIABdwCEu/SK/UAAAAASUVORK5CYII=>

[image8]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKQAAAARBAMAAAChnBq0AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEFSr3e/NiTJEIplmu3ak7QEkAAAAIUlEQVR4XmP8z0BtwIQuQDkYNZJ6YNRI6oFRI6kHRqyRAN//ASGLY1Y+AAAAAElFTkSuQmCC>

[image9]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHUAAAARBAMAAAART/7DAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZqvd780Qu4mZMiJEdlTva7LgAAAAH0lEQVR4XmP8z0Au+MiELkICGNVLPBjVSzwY1Us8AADH1wISqurdNgAAAABJRU5ErkJggg==>

[image10]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAALkAAAAPBAMAAABKEHMHAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAMnarzd3vRFS7ZhCJmSKMG7yZAAAAJklEQVR4XmP8z0A78JEJXYSqYNR0XGDUdFxg1HRcYNR0XIC2pgMArAoCDpkB4fsAAAAASUVORK5CYII=>

[image11]: <data:image/png;base64,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>

[image12]: <data:image/png;base64,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/RIAKAgCOABZmT17dkKws//++5sll3IVwCXj7k/8Po4fP97sNwAUCgEcgLTMnTvXefXVV81tUQUzRx99tNO1a1fn0ksvtVfNmXwGcLbevXubjhNuMKd2dToeAJBPBHAASrV06VJn1KhRsaDlvPPOM0uhFDKAs+k4xNfO6TgBQK4RwAFIauvWrc69994bC0xuuukm57XXXrNXKwg/BXDxdIzigzkdPwDIBQI4AAkeeOABp2LFiiYAeeihh8ziN34N4OLpuGm4Em2rergCgJcI4AA4zz77rNOwYcNYzdHYsWOdP//8017NN4IQwMXT8dQ2n3322XYWAGSEAA6IsLffftsM76Hg4q233nJWrVplr+JLfg7g3AGCP/zwQyvHcR5++GGz7RpYmIGEAWSDAA6IIAU/e+65pwkmvvzyy4Q89TLV4Luisc9c6nUqzzzzjPP666/H0gshnwHc5MmTzb5rPDv91dKoUSOnXLlyCe3dSls0WLDbc9dd1IP13XfftT8SAEpFAAdEyN57720CETeAqF69ull22mmnIgGHvTz44IPOtddeWyQ9filfvrxz3XXXOffcc4/90Z7afvvtcxrA/fTTT061atUS9u3OO+90Vq5cmbCkU2PpvkazTtjHTZ+luV0BIFUEcEAE/P777wkBQ6VKlczSvXt3e9Ws6X1V2+R+lmrrvG5Pp/f1KoDTVFvxx8c9Nvly5plnms9zP1/bsn79ens1AEhAAAeE2MKFC2OBgXpErl271l4lpy6//HJT6xcfPGqbspVtAKdtUI2au03aRi2FFn+stI2qCQSAZAjggBCaPn16LBBo166dM2fOHHuVgtC2tG7dOrZt2s5MZBrA6fOGDBkSOy5PPvmkvYovfP31107z5s3Ndp577rl2NgAQwAFh8sILL5hCv0GDBs5pp51mZ/uKts8N5K688sq0apuaNm2acgD3xhtvxI6LFr8fl3jqJexut/YBAFwEcEAI9O/f3xTyN954o50VGNp2N1gpbfDg0mrg3nnnHee+++4z611wwQXOunXr7FUCJ/74bNy40c4GEDEEcECAub1C77//fjsrsIYNG2b2qWrVqs7AgQPtbOOwww4rNoBr3769eX23bt2cxYsX29mBNm7cONMbWPt366232tkAIoQADggojSGmgnzMmDF2VuD98ccfphZO+6dBb0eOHJmQr8GH7QBO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5+1kzyiAK1u2rJ2cle23396pW7eunYyAev31152ffvrJTjbU+9jrYE+9QksKsLIxd+5c896nn366nRVTsWJFZ5999rGTAZQgN1cs4HOlzYWqAuXzzz+3kz2hAE63Pb20efPmYgtg7YeWQgzWiszst99+sVrS+PPwiCOOKPZ7zlYu3leT05crV85OLiIXnw2EHVcNIimVGjAVKlu2bLGTs6ZbtGeffbad7Dm1r1JPR+3HMccckzBlEYJB35sWl75L3Y7MBdXieknTvZVW8ybuegDSw1WDSNJk9rVq1bKTE6hTgwqWZ5991s7KioLHq666yk723N133+0cdNBBdjICSr03kw2B45WqVavaSRl77bXXzLWzdu1aO6sI9UwlgAPSx1WD0Fm1apWdVITaEJUWwLm87tTg9fvZ/D73JjIzevRo57nnnnNuvPHGnEw+rwBul112sZPTpoGB1eM02Vhvyajzwu+//24nAygFARwiSQGc2rmlol+/fk61atXs5Iylcvs2ExoG4pFHHjG1GePGjbOzERL/+te/zHd8/fXX21lZ8SKAmzhxotm2yy+/3M4qVq6aKgBhRwCHyErnto1qE7S+F5OSex3A6XasOmVo+zTCv+ZZTWffEDyqidN3XKVKFTsrY5dccklWAZymCdM2LV682M4q1l133cW5CmSIKweRpbZtrVq1spOLtXr1alPYZNsOycsATjUdbuAW79prrzW3sRB8+n5Vs5qMOgB4JZsaOJ1/2s4lS5bYWSVSzfaTTz5pJwNIAQEcImvFihVmzLd0qaB6/PHH7eSUpTKsQqpUM5js9pMG683VMCjIHwU3PXr0sJOT2mOPPczwI5nKNICbOnWquSY0PVi6qH0DMsfVg1DRnKbpyKQA0SwO11xzjVOjRg07KyXZBnCZfi6CRRPV6/xMtYG/zkvdTtdrdI7MmTPHXqVEunbSDeBmz55tPi+V3qbJqMMDgMykX3oBIaJCrmPHjnZySnT70r51WRr1HswkgNu2bZspKDVW1/33329nI4Q0FIfapWXi1FNPNUPlpCvVf2jc6dgy+QyXBp+ePn26nQwgRaldrYBPFDeHaaYUwKVaaCWjW7AqaBVgpUJthNIN4ObPn28+J9M2bZ07d87JsBMIDs3+kYpUrgXNW6pOM3//+9/trLScd955zsyZM+1kACkq/WoFQk6FlgqTTB16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46XjBpSkTJky5q8b7IsbwG3bti1+VSABARyAtGgIDS1u7ZwWdYiIUkN87avdCcQ9LkC63HPp+OOPN8/dcwooCWcIgKy0bt3a2W+//WKFjuZj1bJy5Up71cBy90kFrLuf2mft+ymnnGKvDqQlWQBXv379xJUACwEcAE+pEFK7nvjaKQ1JojY+EoSG2dpWt02SuzRr1szs25w5c+zVgay4AZw8+uij5nFxQ9AALgI4ADmjwuj88883S7du3WLBUPPmzc3fp556yiz57pm5ePFi81djtunzVZOmv+72de3aNbbdQK7F18Cde+65BHBICQEcEnz22WcJz5ctW5bwHMjWgw8+6CxYsMD0atUSX8vlLv369TN59957r1k0U4TmDNXguBMmTDBjqiXz5ZdfmqFQxH2tlttuu838tT9Hi7sdWn799VfrHYH80PnXsGHD2HkJlIazBIZqJDTm16GHHmp+PDQ1kvtDcsEFF9irAznx0EMPFVn23XffIkFXqoter44F8e+n2g7AL9TLu2LFirHnOm87deoUtwaQHAEcDP1ovPfee7HHWqRJkyam0AP8RmNkjR8/3jx229cBQaOhQvR7++qrr5r2lXr81Vdf2asBRRDAwVADbVd8AAcAyK34WuOvv/7azgaSopRGEfoR0UCSAIDc27p1K7VuSBsBHBIMHz7cBHCDBw+2swAAgE8QwME0oj3ggAPM44EDB8Zun27YsME8/vbbb+NXBwAABUYAB9MDVYHa0KFDnSpVqpjHffv2NX9nzpxprw4AAAqMAA5Gu3btnN69eyc8f+edd/63AgAA8A0COAAAgIAhgAMAAAgYAjgAAICAIYADAAAIGAI4AACAgCGAAwAACBgCOAAAgIAhgAMAAAgYAjgAAICAIYADAAAIGAI4AACAgCGAAwAACBgCOAAAgIAhgAMAAAgYAjgAAICAIYADAAAIGAI4AACAgCGAAwAACJj/D6rVRZylFkq+AAAAAElFTkSuQmCC>

[image13]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAG0AAAAoBAMAAAAGQ2m6AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAVO+rIt3Nu4lmMnaZRBACcO+DAAAAMUlEQVR4XmP8z0AO+MiELkIkGNWHHYzqww5G9WEHo/qwg1F92MGoPuxgVB92MFT0AQAnCAJAGLTnnAAAAABJRU5ErkJggg==>