# Quaternions

quaternions are a class of hypercomplex numbers with one real part 1 and three imaginary parts i, j, k. with these base elements every quaternion **q** can be described by four real numbers a, b, c, d using the linear combination:  

**q** = a*1 + b*i + c*j + d*k = a + b*i + c*j + d*k  

with   

i² = j² = k² = i*j*k = -1  

the absolute value |q| (the length) of q is one real number:  

|**q**| = sqrt( a² + b² + c² + d² )  

the quaternion set that solve this equation with |**q**|=r are equivalent to the set of 4-dimensional points on a 3-sphere with radius r.   

a 3-sphere is the surface of a 4-dimensional sphere. it means all 4-dimensional points with the same distance r to the origin. it is called 3-sphere, because it has only 3 dimensions, like the surface of a sphere in our 3-dimensional space has only 2 dimensions.   

imagine you live on a 3-dimensional sphere (hehe ;) then you can move only into 2 directions, like a point on a plane surface with x and y axis. a direct connection between two points on a sphere is a vector on a 2-sphere. it is sure that a vector on a 2-sphere has its corresponding vector in the 3-dimensional space because a vector on a sphere is like a translation of a 3-dimensional point on a circle. and this is like rotating a vector in a 2-dimensional plane.  

now think all one dimension higher. then a vector on a 3-sphere is a translation of a 4-dimensional point on a 3-dimensional circle. and a 3-dimensional circle is a sphere in 3-dimensional space. this is like rotating a vector in the 3-dimensional space. this means also, that a 3-dimensional rotation can be described by a 4-dimensional vector.  

the quaternion subset defined by the equation:  

|**q**| = sqrt( a² + b² + c² + d² ) = 1  

are equivalent to the set of 4-dimensional points on the unit 3-sphere. a differece vector between them are a 4-dimensional vector that describes a translation on a 3-dimensional circle in R4 ergo on a sphere in R3.   

some intelligent people discovered, that a subset of the quaternions with |**q**| = 1 together with the quaternion multiplication are such 4-dimensional vectors, that discribe all translations on a 3-dimensional sphere (2-sphere) and this are the 3-dimensional rotations.   

the easiest formula to set up a vvvv quaternion **q** = ( x, y, z, w) that represents a rotation is defined by an angle phi around a direction given by an unit vector **n** = (nx, ny, nz):  

**q** = ( x, y, z, w ) = ( **n** * sin(phi/2) , cos(phi/2) ) =  

**q** = ( nx * sin(phi/2), ny * sin(phi/2), nz * sin(phi/2), cos(phi/2) )  

vvvv node: [axisangle-(quaternion-set):](TODO INTERNALLINK:axisangle-(quaternion-set):) or [axisangle-(quaternion-set-vector):](TODO INTERNALLINK:axisangle-(quaternion-set-vector):)  

this is a much simpler representation of a rotation than the usual 3x3 matrices. rotate a vector by a quaternion and the combination of many rotations can be computed with quaternions also faster than with 3x3 matrices. thats why they are used in 3-d computer graphics.  

for more mathmatical information go:  
[http://www.gamedev.net/reference/articles/article1095.asp]    

*by <span class="user"><a href="https://vvvv.org/users/tonfilm" class="extURL" target="_blank">tonfilm</a></span>*