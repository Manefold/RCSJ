# RCSJ
Studying the Non-Linear Dynamics of Resistively and Capacitively Shunted Josephson Junctions
 #physics
The wave functions for both the electrodes:  $\psi_1\propto e^{i\varphi_1}$ and $\psi_2\propto e^{i\varphi_2}$ with phase difference $\Delta\varphi=\varphi_2-\varphi_1$ (or simply $\varphi$) 
$$E_{kin}=2eV$$ and we know $E=\hbar\dot{\varphi}$ hence $$V_{Josephson}=\frac{\hbar}{2e}\dot{\varphi}$$ and current $$I_{Josphson}=I_C sin\varphi$$
Model the Josephson Junction as Resistor, capacitor and a shunt in parallel. We know from classical electrodynamics that $I_{capacitor}=C\frac{dV}{dt}$ therefore $$I_{capacitor}=\frac{C\hbar}{2e}\ddot{\varphi}\tag1$$$$I_{resistor}=\frac{\hbar}{2eR}\dot{\varphi}\tag{2}$$

$$I_{shunt}=I_Csin\varphi\tag3$$
by  Kirchoff's law, $$I_{exit}=I_{capacitor}+I_{resistor}+I_{shunt}$$
Hence $$I_{exit}= \frac{C\hbar}{2e}\ddot{\varphi}+\frac{\hbar}{2eR}\dot{\varphi}+I_Csin\varphi \tag{4}$$
(4) is a second order differential equation and is analogous to the [[Pendulum]]
$$
\Gamma=mL^{2}\ddot{\theta}+b \dot{\theta}+mgL\sin\theta
$$

| Josephson                                                   | Pendulum                                   |
| ----------------------------------------------------------- | ------------------------------------------ |
| Bias current: $I_{C}$                                       | Applied torque: $\Gamma$                   |
| phase difference: $\varphi$                                 | angle from the vertical: $\theta$          |
| capacitance: $C$                                            | mass: $m$                                  |
| Voltage: $\frac{\hbar}{2e}\dot{\varphi}$                    | Angular velocity: $\dot{\theta}$           |
| Conductance: $\frac{1}{R}$                                  | damping constant: $b$                      |
| Critical Current: $I_{C}$                                   | Max gravitational torque $mgL$             |
| Change in voltage: $\dot{V}=\frac{\hbar}{2e}\ddot{\varphi}$ | Angular acceleration: $L^{2}\ddot{\theta}$ |
The above table makes the two equations completely analogous. Hence the overdamped pendulum gives an a physical interpretation of the RCSJ model. 
# Dimensionless Formulation:
we want to find conditions when it is safe to neglect the second order term. For this we use dimensionless formulation.
Just like in the overdamped oscillator case, we replace time $t$ with a dimensionless constant:
$$
\tau=\frac{2eI_{C}R}{\hbar}t\tag{7}
$$
this gives us 
$$
\beta \varphi''+\varphi'+\sin \varphi=\frac{I}{I_{C}}
$$
where $\beta=\frac{2eI_{C}R^{2}C}{\hbar}$ which is called as the ***Mc-Cumber Parameter***. 
We can safely neglect the second order term when $\beta\ll 1$, the overdamped limit. 
in that situation, we obtain the first order system, 
$$
\varphi'=f(\varphi)=\frac{I}{I_{C}}-\sin \varphi \tag{8}
$$
when $I>I_{C}$ we have no fixed points.
when $I=I_{C}$ we have one fixed point which is half stable,
when $I<I_{C}$ we have two fixed points, one stable and one unstable. 
Hence a pitchfork bifurcation has occurred at $(I,\varphi^{*})=\left( I_{C}, \frac{\pi}{2} \right)$
# Current Voltage Curve
we want to find $\langle V \rangle$ as a function of the applies constant current $I$. 
$\langle V \rangle=I_{C}R\langle \varphi' \rangle$ \\
Hence it is sufficient to find $\langle \varphi '\rangle$. There are two cases two consider: \\
When $I\leq I_{C}$ all solutions approach a fixed point $\varphi^{*}=\sin ^{-1}\left( \frac{I}{I_{C}} \right)$ Thus $\varphi '=0$ in steady state and hence $\langle V \rangle=0$ for all $I\leq I_{C}$ \\
When $I\geq I_{C}$, the solutions are periodic with a period $T$, we find $T$ by finding the time required for $\varphi$ to change by $2\pi$,
$$
T=\int dt=\int_{0}^{2\pi} \frac{d \varphi}{dt} \, d \varphi=\int_{0}^{2\pi} \frac{d\varphi}{\frac{I}{I_{C}}-\sin \varphi}=\frac{2\pi}{\sqrt{ \left( \frac{I}{IC} \right)^{2} -1 }}
$$
we compute $\langle \varphi' \rangle$ by taking average over one cycle:
$$
\langle \varphi' \rangle =\frac{1}{T} \int_{0}^{T} \frac{d\varphi}{d\tau} d\tau=\frac{1}{T}\int_{\varphi(0)}^{\varphi(T)} d\varphi=\frac{1}{t} \int_{0}^{2\pi}d\varphi=\frac{2\pi}{T}
$$
(by change of variables formula)
Substituting $T$ and $\langle \varphi' \rangle$ to the $\langle V \rangle$ formula we obtain
$$
\langle V \rangle =I_{C}R\sqrt{ \left( \frac{I}{I_{C}} \right)-1 }
$$
hence the I-V curve looks like:![[Screenshot 2024-06-04 at 1.58.00 PM.png]]
# General RCSJ
Governing equation.
$$
I_{exit}= \frac{C\hbar}{2e}\ddot{\varphi}+\frac{\hbar}{2eR}\dot{\varphi}+I_Csin\varphi \tag{4}
$$
If we introduce dimensionless $\tilde{t}=\sqrt{ \frac{{2eI_{C}}}{\hbar C} }t$ and $I=\frac{I_{exit}}{I_{C}}$, and $\alpha=\sqrt{ \frac{\hbar}{2eI_{c}R^{2}C} }$. 
Then we obtain 
$$
\phi''+\alpha \phi'+\sin \phi=I
$$
We can rewrite this as a system:
$$
\begin{array}
,\phi'=y \\
y'=I-\sin \phi-\alpha y
\end{array}
$$
## Fixed Points:
To understand the fixed points we need ![[Linear Dynamical Systems]]
For fixed points to occur $y^{*}=0$ so $\sin \phi^{*}=I$. Hence we have two fixed points when $I<1$ and no fixed points when $I>1$. 
Assume $I<1$ so the fixed points exist. 
Since our system is non linear, we will have to linearise it using ![[Linear Stability Analysis]]
Then the jacobian $A=\begin{bmatrix}0&1\\-\cos \phi^{*}&-\alpha\end{bmatrix}$. 
We obtain $\tau=-\alpha<0$ and $\Delta=\cos \phi^{*}=\pm \sqrt{ 1-I^{2} }$. So when $\Delta<0$ the fixed point is a saddle point. 
When $\Delta>0$ : two cases
We have a stable node if $\tau^{2}-4\Delta=\alpha^{2}-4\sqrt{ 1-I^{2} }>0$ i.e if the damping is strong enough or $I$ is close to $1$. 
Otherwise the sink is a stable spiral. 
At $I=1$ the stable node and the saddle point coalesce, so a ![[Saddle-Node Bifurcation]] has occurred.
## Existence of Orbits:
In the case when $I>1$:
No fixed points are available. 
We want to show that periodic solutions exist.
Observe the nullcline $y'=0$ i.e $y=\frac{1}{\alpha}(I-\sin \phi)$. ![[Screenshot 2024-06-26 at 2.03.10 PM.png]]
The flow is downward above the nullcline and upward below it.
#### Constructing a Poincare map:
All the trajectories confine themselves in $y_{1}<y<y_{2}$ as $t\to \infty$.
Since $\phi$ is a phase difference, we are only interested in the interval $(0,2\pi)$, as the rest of the patch is just its repetition.
Consider a trajectory starting at some height $y$ of the box until it intersects the right side of the box at new height $P(y)$. This is called the Poincare map. 
![[Screenshot 2024-06-26 at 2.13.30 PM.png]]
We cannot compute $P(y)$ explicitly, but observe that $y_{1}<P(y_{1})<y_{2}$. 
$P(y)$ is a continuous function. Since solutions of differential equations depend continuously on initial conditions. Then by fixed Brouwer Fixed point theorem, there exists $y^{*}$ such that $P(y^{*})=y^{*}$. 
So a periodic solution exists and is a closed orbit in the cylindrical phase space:
![[Screenshot 2024-06-26 at 2.42.18 PM.png]]
$f'(x)=\lim_{ h \to 0 } \frac{{f(x+h)-f(x)}}{h}$ 
$$
f^{n}(x)=\frac{1}{h^{n}}\sum_{k=0}^n (-1)^{n-k} {n \choose k} f(x+kh)
$$
## Homoclinic Bifurcation
A part of the limit cycle moves closer to a saddle point. At the bifurcation the cycle touches the saddle point and becomes a homoclinic orbit. Thus is another kind of infinite period bifurcation.
We slowly decrease $I$ from some value $I>1$. 
We have shown that initially it has a stable limit cycle.
The system is bistable when $I_{c}<I<1$, i.e a sink coexists with the stable limit cycle.
![[Screenshot 2024-07-25 at 11.30.30 AM.png]]
$U$ is a branch of the unstable manifold of the saddle.
As $I$ decreases, the stable limit cycle moves down and squeezes $U$ closer to the stable manifold of the saddle.![[Screenshot 2024-07-25 at 11.41.24 AM.png]]

At $I=I_{c}$ the limit cycle merges with $U$ in a homoclinic bifurcation. Now $U$ is a homoclinic orbit. 
Finally when $I<I_{c}$ the connection breaks and $U$ spirals into the sink.
![[Screenshot 2024-07-25 at 11.45.56 AM.png]]

### Python Plots for some $\alpha$ and $I$ values:
$\alpha=0.5$ and $I=1.2$
   ![[Screenshot 2024-07-31 at 3.24.11 PM.png]]

$\alpha=0.5$ and $I=0.8$ (bistable)
![[Screenshot 2024-07-31 at 3.24.29 PM.png]]

$\alpha=0.5$ and $I=0.4$
![[Screenshot 2024-07-31 at 3.24.39 PM.png]]

$\alpha=1.3$ and $I=1.2$
![[Screenshot 2024-07-31 at 3.24.53 PM.png]]

$\alpha=1.3$ and $I=0.8$
![[Screenshot 2024-07-31 at 3.25.06 PM 1.png]]

$\alpha=1.3$ and $I=0.4$
![[Screenshot 2024-07-31 at 3.25.20 PM.png]]

Notice that we do not get Homoclinic Bifurcation for $\alpha=1.3$. We obtain Bistable regions for particular values of $\alpha$ and $I$. 
If we plot $\alpha$ vs $I$ we obtain:
![[Screenshot 2024-07-25 at 11.47.31 AM.png]]
The curve that separates the bistable and the stable fixed points can be approximated analytically using an advanced Technique known as Melinkov's method (See Guckenheimer and Holmes 1983, p.202).
### Hysteretic Current Voltage Curve:
If we take a small value of $\alpha$, and start from $I=0$, we know that there exists a fixed point hence for the time average $\langle V \rangle=0$. It will remain zero until $I=1$.Because now the limit cycle exists, Now if we decrease back from $I=1$, the limit cycle will still persist for $I<1$, but the frequency will tend to zero as we are approaching an infinite period bifurcation. We know that $\langle V \rangle$ is proportional to frequency, $\langle V \rangle$ also drops to zero continuously.
![[Screenshot 2024-07-25 at 12.18.42 PM.png]]
