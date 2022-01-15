# Linear Algebra  

## Scalar, Vector, and Matrix  
* Scalar : 하나의 크기량  
* Vector : 순서가 있는 list(순서가 없으면 set)  
* Matrix : 2차원의 배열(row=행, column=열)  
    * default는 column vector  
* Row vector = Column vector의 transpose  

## Matrix Notations  
* $A \in$ $R^{n*n}$ : 정사각 행렬 (#rows = #columns)  
* $A \in$ $R^{m*n}$ : 직사각 행렬 (#rows $\neq$ #columns)  
* $A^T$ : Transpose (주대각선을 축으로 하는 반사 대칭을 가하는 행렬)  
* $A_{ij}$ : 행렬 A의 (i,j) 원소  
* $A_{i,}$ : 행렬 A의 i 행의 원소  
* $A_{,j}$ : 행렬 A의 j 열의 원소  

## Vector/Matrix Additions and Multiplications  
* Element-wise addition  
C = A + B (i.e., $C_{i,j}$ = $A_{i,j}$ + $B_{i,j}$)  
A,B,C는 같은 크기 (i.e., A,B,C $\in$ $R^{m*n}$)  
* Scalar multiple of vector/matrix  
벡터나 행렬에 상수 배  
* Matrix-matrix multiplication  
C = AB (i.e., $C_{i,j}$ = $\sum_{k}A_{i,k}B_{k,j}$)  
* AB $\neq$ BA : 교환법칙이 성립하지 않음(not Commutative)  
* A(B + C) = AB + AC : 분배법칙 성립(Distributive)  
* A(BC) = (AB)C : 결합법칙 성립(Associative)  
* $(AB)^T$ = $B^TA^T$ : 전치행렬의 속성(Property of transpose)  
