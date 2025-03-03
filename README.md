java c
MA585 
Homework 5 
1. Sample mean X = 0:157 was computed from a sample of size 100 generated from a MA(1) process with mean μ and θ = -0.6, σ2 =   1. Construct   an approximate   95%   CI   for   μ. Are   the   data   compatible   with   the   hypothesis   that   μ   =   0? 
2. Suppose you have a sample of size 100 and obtained (1) = 0:432 and (2) = 0:145: Assuming that data was generated from a MA(1) process, construct a 95% CI for ρ(1) and ρ(2): Based on these two conÖdence intervals, is the data consistent with a MA(1) model with θ = 0:6?
3. For each one of the following ARMA processes, choose parameters such that the process is causal and invertible. In each case, use the arima.sim function in R to generate a sample realization of size 100: Generate a time series plot of the simulated series, and in each case plot both population and sample ACF and PACF.
(i) AR(2)
(ii) ARMA(1,1)
(iii) MA(1)
(iv) ARMA(1,2)
R Note: acf and pacf functions in R can be used to obtain sample acf and pacf. The following code was used to generate the plots for AR(2) example in lecture note 4.
x=arima.sim(n=100, list(ar=c(1.5,-0.75)))
plot.ts(x)
title(main="Simulated Data from the AR(2) Process X(t)-1.5X(t-1)+0.75X(t-2)=e(t)")
par(mfrow=c(2,2))
y = ARMAacf(ar=c(1.5,-0.75),lag.max = 20)
y = y[2:21]
plot(y, x = 1:20, type = "h", ylim = c(-1,1), xlab = "h",
ylab = "Autocorrelation", main = "AR(2) Population ACF")
abline(h = 0)
y = ARMAacf(ar=c(1.5,-0.75),lag.max = 20,pacf=T)
plot(y, x = 1:20, type = "h", ylim = c(-1,1), xlab = "h",
ylab = "Partial Autocorrelation", main = "AR(2) Population PACF")
abline(h = 0)
acf(x,main="Sample ACF", ylim = c(-1,1))
pacf(x,main="Sample PACF", ylim = c(-1,1))
For general ARMA processes, you modify the list of parameters as ar=c(..,..),
ma=c(..,...). For example, to simulate a sample realization from an ARMA(2,1)
process, use
>arima.sim(n=100,list(ar=c(1.5,-0.75), ma=c(0.3))) # n=100 observations
from X(t)-1.5X(t-1)+0.75X(t-代 写MA585 Homework 5SQL
代做程序编程语言2)=e(t)+0.3e(t-1).
Also, the following code was used to generate the MA(2) example. Note
how the option ci.type="ma" a§ects the conÖdence bounds for sample acf.
par(mfrow=c(3,1))
y=arima.sim(100, model=list(ma=c(-1.5,0.75)))
plot.ts(y,main="Sample Realization from a MA(2) Process")
acf(y,xlim=c(1,20), ylim=c(-0.6,0.6),xaxp=c(0,20,10), main="Sample ACF",ci.type="ma")
pacf(y,xaxp=c(0,20,10), ylim=c(-0.6,0.6), main="sample PACF")
4. The graphs below show the sample ACF and PACF of three time series of length 100 each. On the basis of the available information, choose an ARMA model for the data. You need to identify the order of the model and, if possible, provide approximate values of the ARMA parameters φ and θ: Justify your answer.
a.

b.

c.

d.

5. For a series of length 169, we find that (1) = 0:41; (2) = 0:32; (3) = 0:26; (4) = 0:21;and (5) = 0:16:What ARMA model fits this pattern of autocorrelations? Justify your answer.
6. A stationary time series of length 121 produced sample partial autocor-relation of φ11 = 0:8, φ22 = -0.6,φ33      =   0.08,   and   φ44      =   0.00.    Based   on   this information   alone,   what   model   would   we   tentatively   specify   for   the   series? 
7.      Consider   the   annual   sunspots   data   in   R   given   in   data   file   sunspot.year   (yearly   numbers   of   sunspots   from 1700   to 1988).                If   you      don't      know   what sunspots   are,   check   on   the   internet. 
(i)   Plot   the   time   series   and   describe   the   features   of   the   data.
(ii) Generate   a   new   time   series   by   transforming   the   data   as   newsunspot=sqrt(sunspot.year).   Plot   the   new   time   series.         Why   is   the   square-root   transformation   necessary? 
(ii)   Plot   ACF   and   PACF   of   the   transformed   data. Based   on   these   plots,   propose   a   plausible   model   and justify   your   answer. 





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
