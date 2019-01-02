# Bivariate symbolic regression model (BSRM) {-}

## Preliminaries {-}

Let $Y = \{y_1,\ldots,y_n\}$ be a set of observations that represents a random sample of the interval-valued variable $Y$.  Each observation $y_{i} = [y_{Li},y_{Ui}] \in Y$ is defined as an interval $y \in \Im = \{[y_{L},y_{U}] : y_{L}, y_{U} \in \Re, y_{L} \leq y_{U}\}$ and represents the observed value of the interval variable $Y$. Despite the loss of information, we consider an interval-valued variable $Y$ as a two-dimensional or a bivariate  quantitative feature vector $\mathbf y_{i}=(y_{1i},y_{2i})$, where the variables $Y_1$ and $Y_2$ are one-dimensional random variables representing, for example, the lower and upper boundaries $(Y^{L},Y^{U})$ or the midpoint and half-range $(Y^{m},Y^{r})$ of the intervals or any other pair of interval features possible to be represented.

Consider that the joint density probability function of the bivariate quantitative
feature vector $\mathbf y_{i}=(y_{1i},y_{2i})$ belongs to the bivariate exponential family of 
distributions \citep{IT2005} defined by

\begin{equation}
    f(\mathbf y; \pmb \theta)=
    \mathrm{exp}\left[\phi^{-1}\{y_{1}\theta_{1} + y_{2}\theta_{2} -
    b(\theta_{1},\theta_{2},\rho)\}+ c(y_{1},y_{2},\rho,\phi)\right],
    (\#eq:random)
\end{equation}

\noindent where \boldmath$\theta$\unboldmath=
$(\theta_{1},\theta_{2})$ is the vector of canonical parameters, $\phi$ is a common dispersion parameter
and $\rho$ is a constant correlation parameter between these two
random variables. We assume that the functions
$b(\cdot,\cdot,\cdot)$ and $c(\cdot,\cdot, \cdot, \cdot)$ are known.
The function $b(\cdot,\cdot,\cdot)$ is the cumulant generating
function of (\ref{eq:random}) and the mean and variance of the bivariate 
random vector $\mathbf Y=(Y_1, Y_2)$ can be obtained from well-known 
equations of natural exponential families and presents a direct relation with the GLM framework. The log-likelihood function for the $i$th observation can be written as

\begin{equation}
  l_{i} = l_{i}(\pmb \theta,\phi,\rho) =
        \phi^{-1} \{y_{1i}\theta_{1} +                                                                           y_{2i}\theta_{2}-b(\theta_{1},\theta_{2},\rho)\}+c(y_{1i},y_{2i},\rho,\phi).
(\#eq:loglikelihood)
\end{equation}

The use of the bivariate exponential family of distributions allows to extend the GLM framework for the case of interval-valued variables.

## The model {-}

Let $E=\{e_1,\ldots,e_n\}$ be a set of examples that are described by
$p+1$ interval-valued variables $Y$, $T_{1},\ldots,T_{p}$. The interval-valued 
variable $Y$ is a dependent variable and it is related to a set of interval-valued 
variables $T_j$ ($j=1,2,\ldots,p$), known as independent variables. Each example
$e_{i}\in E$ ($i=1,\ldots,n$) is denoted by an interval quantitative feature
vector $(\mathbf t_{i},y_{i})$, with $\mathbf t_{i} = (t_{i1},\ldots,t_{ip})$, 
where $t_{ij}=[a_{ij},b_{ij}] \in \Im = \{[a,b]: a, b \in \Re, a \leq b\}$ $(j=1,\ldots,p)$ 
  and $y_{i} = [y_{Li},y_{Ui}] \in \Im$ are the observed values of $T_{j}$ and $Y$, 
respectively. 


Now, let $Y_1$, $X_{1j}$ and $Y_2$, $X_{2j}$ ($j=1,2,\ldots,p$) be quantitative variables 
that represent any pair of interval features from the interval-valued variables $Y$ and $T_{j}$, respectively. In case where those variables represent, respectively, the lower and upper boundaries of the interval variables $Y$ and $T_{j}$,
each example $e_{i} \in E$ ($i=1,\ldots,n$) will be denoted by two vectors: $(\mathbf x^{L}_{i},y^{L}_{i})$ 
and $(\mathbf x^{U}_{i}, y^{U}_{i})$, with $\mathbf x^{L}_{i} =
(x^{L}_{i1}, \ldots, x^{L}_{ip})$ and $\mathbf x^{U}_{i} = (x^{U}_{i1},\ldots,
x^{U}_{ip})$, where $x^{L}_{ij} = a_{ij}$, $x^{U}_{ij} = b_{ij}$, $y^{L}_{i} = y_{Li}$ and $y^{U}_{i} = y_{Ui}$
are the observed values of the quantitative variables $X^{L}_{j}$, $X^{U}_{j}$, $Y^{L}$ and $Y^{U}$, respectively. Likewise, for the case where those variables
represent, respectively, the midpoint and half-range of the interval variables $Y$ and $T_{j}$,
each example $e_{i} \in E$ ($i=1,\ldots,n$) will be denoted by the vectors
$(\mathbf x^{m}_{i}, y^{m}_{i})$ and $(\mathbf x^{r}_{i}, y^{r}_{i})$,
with $\mathbf x^{m}_{i} = (x^{m}_{i1}, \ldots, x^{m}_{ip})$ and $\mathbf x^{r}_{i} = (x^{r}_{i1},\ldots,
x^{r}_{ip})$, where $x^{m}_{ij} = (a_{ij} + b_{ij})/2$, $x^{r}_{ij}=(b_{ij}-a_{ij})/2$, 
$y^{m}_{i}=(y_{Li}+y_{Ui})/2$ and $y^{r}_{i} = (y_{Ui} - y_{Li})/2$ are the observed values of 
the variables $X^{m}_{j}$, $X^{r}_{j}$, $Y^{m}$ and $Y^{r}$, respectively.

Following the GLM framework, \cite{LimaNetoetal2011} consider a \textbf{BSRM} with probabilistic support 
defined by two components (a random and a syste\-ma\-tic component) to model interval-valued data. 
The random component considers the bivariate random vector \[\textbf{Y} = \left[\begin{array}{c}
Y_{1}\\
Y_{2}\end{array}\right],\] having the bivariate exponential family (\ref{eq:random}). 
In the systematic component, the explanatory variables $X_{1j}$ and $X_{2j}$ ($j=1,2,\ldots,p$) 
are responsible for the variability of $Y_{1}$ and $Y_{2}$, respectively, and they are defined by

\begin{equation}
\pmb \eta_{1} = g_{1}(\pmb \mu_{1})= \pmb X_{1} \pmb \beta_{1}\,\, \mbox{and}\,\, \pmb \eta_{2} = g_{2}(\pmb \mu_{2})= \pmb X_{2} \pmb \beta_{2},
(\#eq:systematic)
\end{equation}
where $\pmb X_{1}$ and $\pmb X_{2}$ are known model matrices
formed by the observed values of the variables $X_{1j}$ and $X_{2j}$, 
respectively, $\pmb \beta_{1}$ and $\pmb \beta_{2}$
are vectors of parameters to be estimated,
$\pmb \eta_{1}$ and $\pmb \eta_{2}$ are
the linear predictors, $\pmb \mu_{1}$ and $\pmb \mu_{2}$ 
are the mean of the res\-pon\-se variables $Y_{1}$ and $Y_{2}$, respectively, with
$\pmb \eta_{l}$=$(\eta_{l_{1}},\ldots,
\eta_{l_{n}})^\top,$ $\pmb \mu_{l}$ = $(\mu_{l_{1}},\ldots,
\mu_{l_{n}})^\top$ and $\pmb \beta_{l}$ $=(\beta_{l_{0}},\ldots,\beta_{l_{p}})^\top$, $l = 1,2$. Here, $g_{1}(\pmb \mu_{1}$) and $g_{2}(\pmb \mu_{2}$) 
are well-known link functions that connect the mean of the res\-pon\-se variables $Y_{1}$ and $Y_{2}$ with the explanatory variables $X_{1j}$ and $X_{2j}$ ($j=1,\ldots,p$), respectively, being possible to choose different link functions. 
A few functions available for the \textbf{BSRM} are:
\textit{identity, logarithmic, inverse, power}, among others.
However, some link functions have particular properties and can be preferred
in some situations. For example, if one considers the half-range of intervals in the
random component, the logarithmic link function will guarantee positiveness
for the predicted values of $\hat{y}_{i}^{r}$ ($\hat{y}_{i}^{r} >0$)
and this result implies that $\hat{y}_{i}^{L} \leq \hat{y}_{i}^{U}$, $i = 1, \ldots, n$.

---
# References {-}