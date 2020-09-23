# FEMM-inductor-tutorial
An FEMM simulation of an Air Core Inductor

## Introduction

Finite Element Method Magnetics (FEMM) is a finite element package for solving 2D planar and axisymmetric problems in low frequency magnetics and electrostatics.

## Model Construction and Analysis

This will take you through a step-by-step process to analyze the magnetic field of an aircored solenoid sitting in open space as shown below. 

![img](https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcSQ6wTWwvR_pGUFzuGJ9f3pEal-LdEjtEMSKA&usqp=CAU)

In FEMM, we take a cross section of this solenoid along it's axis, imagine if the inductor was kept standing with it's axis facing upwards and you took a knife and cut it like a cake. 
Basically, in a 2-D plane you will have something that looks like this...
![img]()
I = 1700A
Inner Dia = 0.75m
OD = 0.85m
Material: Aluminium

1) Plot the points 
(0,0),(0,10),(10,0),(10,10) for boundary

# results

![Result Plot](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/results.PNG)
