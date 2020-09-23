# Air Core Reactor in FEMM
An FEMM analysis of an Air Core Inductor

## Introduction

Finite Element Method Magnetics (FEMM) is a finite element package for solving 2D planar and axisymmetric problems in low frequency magnetics and electrostatics.

## Model Construction and Analysis

This will take you through a step-by-step process to analyze the magnetic field of an aircored reactor sitting in open space as shown below. (the enclosed cylindrical structures are the air core reactors) . 

![img](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/air-reactor.PNG)

In FEMM, we take a cross section of this solenoid along it's axis, imagine if the inductor was kept standing with it's axis facing upwards and you took a knife and cut it like a cake. 
Basically, in a 2-D plane you will have something that looks like this...

![img](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/cut-section-of-inductor.PNG)

**We are going to perform this Magnetic Field analysis according to the following specifications**
Element | Value
------------ | -------------
Current | 1700A
Inner Diameter | 0.75m
Outer Diameter | 0.85m
Conductor Material | Aluminium

Now, open up FEMM 4.2 and follow the steps below

1) Plot the points 

(**NOTE** press the dot icon on top left and hit tab to enter the co-ordinates)

* (0,0),(0,10),(10,0),(10,10) for boundary

![bound](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/boundary.PNG)

This will create a sort of environment/ room in which our coil in placed.

* (4.575,4),(4.575,6),(4.625,4),(4,625,6) for the left side
and (5.375,4),(5.375,6),(5.425,4),(5.425,6) for the right side.

This is the cross-section of our coil.

2) Not that the plots are ready, we will have to specify the material inside these boundaries. 

* First, let's import the required materials.
    - click on ``Properties`` >> ``Materials Library`` 
    - drag and drop ``air`` and ``Aluminium 6061-T6`` as shown below.

    ![img](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/materials.PNG)

    - Now, we need to create a circuit to specify the current flowing through the coil. 
    For this, go to ``Properties`` >> ``Circuits`` >> ``Add Property`` and make the changes as shown below:

    ![ckt](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/ckt.PNG)

    - Now, select the green circle icon and then insert it anywhere inside the open space, and the two smaller rectangles. (refer diagram below)
    
        * Right click on the exterior region dot that you just inserted and hit ``space`` >> select ``Block type`` as ``Air`` >> unselect ``Let Triangle choose mesh``  >>``Mesh Size = 0.1`` >> and click ``OK`` 

        * Right click on the dot in the smaller rectangle on left that you just inserted and hit ``space`` >> select ``Block type`` as ``Air`` >> unselect ``Let Triangle choose mesh``  >> ``Mesh Size = 0.1`` >> ``In circuit`` select ``coil`` >> ``no. of turns =  -100`` >> hit ``ok``

        * Repeat everything again for the remaining dot except ``no. of turns =  100``. 

        * Make sure everything matches as is in the image below. 
    
     

![green](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/final.PNG)

5) Problem Definition: click on Problem and copy everything as shown below

![prb](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/problem_def.PNG)

4) Now, hit the ![im](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/mesh.PNG) icon >> then ![im](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/calculate.PNG) >> and finally ![view](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/view.PNG) 

4) You should now be able to see magnetic field lines emanating as you would expect from an excited coil.

5) To view a colorful distribution of the magnetic field, click on 
![](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/rainbow.PNG) >> and select show density plot

![](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/show_den_plot.PNG)

# Results

![Result Plot](https://github.com/DhruvaG2000/FEMM-inductor-tutorial/blob/master/img/results.PNG)

# Areas of Application:

1) Reactors are installed at substations to help stabilize the power system. However due to high amounts of AC current, and inductance, the resultant magnetic field can be fatal to human beings in close proximity to the reactor. Hence, using the above method, and tweaking the parameters according the reactor being used, we can very accurately predict the safety boundaries, beyond which humans can be safe. 

2) Instead of the air core, we can insert Iron or some other ferromagnetic material inside the inductor and also try to design an electromagnet. 
