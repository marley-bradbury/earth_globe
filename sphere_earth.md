# Sphere Earth Calculations
## 1.0 - Variables described by a triangle formed by 3 points:
### 1.1 - Point description
$P_{satellite}$ = the location of the satellite when an image is taken

$P_{target}$ = the location of the target being imaged

$P_{earth.center}$ = the location of the center of the earth
### 1.2 - Independant Variable
$\alpha$ = off nadir angle = $\angle P_{earth.center}P_{satellite}P_{target}$
### 1.3 - Dependant Variables
$\beta$ = earth centered angle between satellite and target = $\angle P_{target}P_{earth.center}P_{satellite}$

$\gamma$ = imaging angle + $90^\circ\Rightarrow$ = $\angle P_{satellite}P_{target}P_{earth.center}$

$dist$ = distance between satellite and target = $\overrightarrow{P_{satellite}P_{target}}$
### 1.4 - Constants
$R_E$ = Radius of the earth = $6378.14km$ = $\overrightarrow{P_{target}P_{earth.center}}$

$h$ = altitude = $500km$

$SMA$ = Semi Major Axis = $R_E+h$ = $6878.14 km$ = $\overrightarrow{P_{earth.center}P_{satellite}}$
## 2.0 - Derivation of functions to describe dependant variables
### 2.1 - Equalities gained from the sine rule
$\frac{R_E}{sin\alpha}$ = $\frac{dist}{sin\beta}$ = $\frac{SMA}{sin\gamma}$, $\frac{sin\alpha}{R_E}$ = $\frac{sin\beta}{dist}$ = $\frac{sin\gamma}{SMA}$
### 2.2 - Functions
$\gamma$ = $180^\circ-arcsin(\frac{SMA}{R_E}sin\alpha)\leftarrow$ as $90^\circ<\gamma\leq 180^\circ\leftarrow$ from 3.1

$\beta$ = $180^\circ-\alpha-\gamma$

$dist$ = $R_E\frac{sin\beta}{sin\alpha}$  = $R_E\frac{sin(180^\circ-\alpha-\gamma)}{sin\alpha}$

from 1.4 $\rightarrow SMA$ = $h+R_E\Rightarrow\gamma$ = $180^\circ-arcsin(\frac{R_E+h}{R_E}sin\alpha)$ = $180^\circ-arcsin((1+\frac{h}{R_E})sin\alpha)$

$dist$ = $R_E\frac{sin(180^\circ-\alpha-(180^\circ-arcsin((1+\frac{h}{R_E})sin\alpha)))}{sin\alpha}$ = $R_E\frac{sin(arcsin((1+\frac{h}{R_E})sin\alpha)-\alpha)}{sin\alpha}\leftarrow$ [click to see interactive graph of this equation to see how changing the altitude (h) affects the relationship between off nadir angle and distance between the satellite and the target](https://www.desmos.com/calculator/umkzskb8p2)

from 1.4 $\rightarrow\gamma$ = imaging angle + $90^\circ\Rightarrow$ imaging angle = $\gamma-90^\circ$

$\therefore$  imaging angle = $90^\circ-arcsin((1+\frac{h}{R_E})sin\alpha)\leftarrow$ [click to see interactive graph of this equation to see how changing the altitude (h) affects the relationship between off nadir angle and imaging angle](https://www.desmos.com/calculator/fn1thtjpv3)
## 3.0 - Angle limitations
### 3.1 - Mathematical limitations of γ
WHEN $\gamma\leq 90^\circ\Rightarrow($ imaging angle $\leq 0)\leftarrow$ IMPOSSIBLE (images cannot be taken pointing at or beyond the surface of the earth)

WHEN $\gamma>180^\circ\Rightarrow(\alpha<0\leftarrow)$ IMPOSSIBLE (off nadir angle cannot be less than 0)

$\therefore90^\circ<\gamma\leq 180^\circ$
### 3.2 - Physical limitations of α
off nadir angle cannot be less than 0

the satellite is incapable of slewing past $45^\circ$

$\therefore 0\leq\alpha\leq 45^\circ$ 
### 3.3 - Derived mathematical limitations of α
$\alpha$ = $arcsin(\frac{R_E}{SMA}sin\gamma)\leftarrow$ gained by rearraging equalities in 2.1

$90^\circ<\gamma\leq 180^\circ$

$arcsin(\frac{R_E}{SMA}sin90^\circ)$ = $arcsin(\frac{R_E}{SMA})$ = $68.019^\circ$ 

$arcsin(\frac{R_E}{SMA}sin180^\circ)$ = $0$

$\therefore 0\leq\alpha<68.019^\circ$

$\therefore$ the phyisical limitations of the satellite are within the mathematical limitations of $\alpha$ so images can be taken at all possible angles at which the satellite is physically capable of pointing