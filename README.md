# workshop1
clear all;
close all;
clc;
mu= .5;
N= 1;
phi= pi/6;
Force= 0.448018475;
NF=0.672027713;
a= 1.18;
b= 1.34;
c= (a+b)/2;
tol= 10^-4;
f= @(x) NF*cos(x)+mu*NF*sin(x)-N*mu;
while abs(f(c))>tol
    f(a);
    f(b);
    f(c);
    if f(a)*f(c)<0
        b=c;
    else
        a=c;
    end
    c= (a+b)/2;
end
f(c)
