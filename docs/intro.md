# Matrices

## Matrix



## Addition and Subtraction of Matrices

Adding or subtracting matrices is straightforward. For example, given two matrices
$$
\begin{aligned}
    A &= \begin{bmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \end{bmatrix} \\
    B &= \begin{bmatrix} b_{11} & b_{12} & b_{13} \\ b_{21} & b_{22} & b_{23} \end{bmatrix} \\
    A + B &= \begin{bmatrix} a_{11} + b_{11} & a_{12} + b_{12} & a_{13} + b_{13} \\ a_{21} + b_{21} & a_{22} + b_{22} & a_{23} + b_{23} \end{bmatrix} \\
    A - B &= \begin{bmatrix} a_{11} - b_{11} & a_{12} - b_{12} & a_{13} - b_{13} \\ a_{21} - b_{21} & a_{22} - b_{22} & a_{23} - b_{23} \end{bmatrix}
\end{aligned}
$$
In other words, you only need to add or subtract individual components. And since $A$ and $B$ have to have the same dimension to be added or subtracted, the positions always match up.

## Multiplying and Dividing a Matrix with a Number

This is another straightforward operation on matrices. To multiply an arbitrary matrix $A$ with a number $u$, you only need to multiply each component of $A$ by $u$. Similarly for division, each component should be divided by the number individually.

## Multiplying a Matrix with a Vector

Things get a little complicated when we consider the multiplication of a matrix with not a number (when compared to vectors and matrices, a number is sometimes called a scalar), but a vector. Let's approach this step by step.

First, we need to know what can be multiplied and what can not. Given a $m$ by $n$ matrix $A$ (meaning it has $m$ rows and $n$ columns) and a $q$-dimensional vector $x$, they can be multiplied together if and only if $n = q$.

Second, the result of multiplying matrix $A$ with vector $x$ is a new vector $b$ (denoted by $Ax=b$). Note that in the first step, the number of rows $m$ does not matter in determining whether or not the matrix can be multiplied with a vector. Instead, it determines the dimension of the output vector $b$. In other words, $b$ will be a $m$-dimensional vector.

Lastly, let's get to the actual operation of multiplying. Let's say $A$ is a 2 by 3 matrix and $x$ is a 3-dimensional vector. Then
$$ Ax = 
\begin{bmatrix} a_{11} & a_{12} & a_{13} \\ a_{21} & a_{22} & a_{23} \end{bmatrix}
\begin{bmatrix} x_1 \\ x_2 \\ x_3 \end{bmatrix}
=
\begin{bmatrix} a_{11}x_1 + a_{12}x_2 + a_{13}x_3 \\
                a_{21}x_1 + a_{22}x_2 + a_{23}x_3 \end{bmatrix}
=
\begin{bmatrix} b_1 \\ b_2 \end{bmatrix}
$$

Admittedly this looks confusing. Let us try to break it down. One way to approach this is to think $Ax$ as a sum of vectors. Notice that
$$
\begin{aligned}
Ax &=
\begin{bmatrix} a_{11}x_1 + a_{12}x_2 + a_{13}x_3 \\
                a_{21}x_1 + a_{22}x_2 + a_{23}x_3 \end{bmatrix} \\
&=
\begin{bmatrix} a_{11}x_1 \\ a_{21}x_1 \end{bmatrix} +
\begin{bmatrix} a_{12}x_2 \\ a_{22}x_2 \end{bmatrix} +
\begin{bmatrix} a_{13}x_3 \\ a_{23}x_3 \end{bmatrix} \\
&=
x_1 \begin{bmatrix} a_{11} \\ a_{21} \end{bmatrix} +
x_2 \begin{bmatrix} a_{12} \\ a_{22} \end{bmatrix} +
x_3 \begin{bmatrix} a_{13} \\ a_{23} \end{bmatrix} \\
\end{aligned}
$$
This is one way we can understand the procedure. Instead of looking at the matrix and the vector as a whole, it can be viewed as a **linear combination** of the **columns** of the matrix $A$.

## Multiplication of Matrices

Matrix multiplication can be used as a convenient and concise way to represent a system of equations. For example, the system of equations
$$ \begin{aligned}
\dot{x} &= v \\
\dot{v} &= -\frac{\rho}{m}-\frac{k}{m}+\frac{1}{m}u
\end{aligned} $$
Can be represented by the following equation:
$$ \begin{aligned}
    \begin{bmatrix} \dot{x} \\ \dot{v} \end{bmatrix}
    = 
    \begin{bmatrix} 0 & 1 \\ -\frac{k}{m} & -\frac{\rho}{m} \end{bmatrix}
    \begin{bmatrix} x \\ v \end{bmatrix}
    +
    \begin{bmatrix} 0 \\ \frac{1}{m} \end{bmatrix}
    u
\end{aligned} $$
You won't be wrong to argue that the second form seem more complicated than just using the two simpler equations above. However, as we'll see later in the course, the matrix form allows us to analyze the system as a whole instead of treating them as individual equations.

# Differential Equations

