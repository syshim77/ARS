# Linear System  

## Linear Equation  
* linear equation : $a_1x_1$ + $a_2x_2$ + $a_nx_n$ = b  -> $a^TX$ = b  
* linear system : set of linear equations  
* Inverse matrix : 정사각행렬에서만 해당 됨  
    * 직사각행렬의 경우 일부의 경우만 찾을 수 있음(작아지는 쪽)  
* $x$ = $A^{-1}b$  
    * A가 역행렬이 있다면 근이 1개  
    * A가 역행렬이 없다면 근이 없거나 무수히 많음  
* Rectangular Matrix A in $Ax = b$(e.g., A $\in$ $R^{m*n}$, where m $\neq$ n)  
    * m < n : more variables than equations  
        * usually infinitely many solutions exits (under-determined system)  
    * m > n : more equations than variables  
        * usually no solution exists (over-determined system)  

## Linear Combination  
* linear combination : $c_1v_1$ + $c_2v_2$ + $\cdots$ + $c_pv_p$(p개 벡터에 상수배 해서 다 더해줌)  
* Span : the set of all linear combinations of $v_1, $\cdots$ v_p$(재료벡터들을 가지고 만들수 있는 가능한 모든 선형결합 벡터들의 집합)  
* 미지수: 세로 벡터들의 개수  
* 방정식: 주어진 벡터들의 차원  
* 방정식이 많다는 뜻은 차원이 많다.  
* Sum of outer products is widely used in machine learning  
    * Covariance matrix in multivariate Gaussian  
    * Gram matrix in style transfer  

## Linear independence  
* solution exists only b $\in$ Span {$a_1,a_2,a_3$}  
    * $a_1, a_2,$ and $a_3$ are linearly independent : unique  
    * $a_1, a_2,$ and $a_3$ are linearly dependent : infinitely many solutions  
* Linearly dependent  
    * $v_j \in$ Span{$v_1, v_2, \cdots , v_{j-1} $} (j = 1, ... , p)  
    * at least one such $v_j$ is found, then {$v_1, \cdots , v_p$}  
* Linearly independent  
    * $v_j \in$ Span{$v_1, v_2, \cdots , v_{j-1} $} (j = 1, ... , p)  
    * no such $v_j$ is found, then {$v_1, \cdots , v_p$}  
* trivial solution  
    * $x_1v_1 + x_2v_2 \cdots + x_pv_p = 0$  
    * one solution is $x = 0벡터$  
    * linearly independent이면 trivial solution이 유일한 해  
    * linearly dependent이면 other nontrivial solutions가 있음  
* linearly dependent vector does not increase Span!  

## Span ans Subspace  
* Subspace  
    * Span이랑 유사함  
    * $R^n$의 부분집합이면서 linear combination에 닫혀있음  
* basis  
    * 기저벡터  
    * subspace의 요소  
    * linearly independent  
    * fully spans the given subspace H  
* Rank  
    * basis의 개수  

## Linear transformation  
* Domain(정의역) : set of all the possible values of x  
* Co-Domain(공역) : set of all the possible values of y  
* Image(함수의 상) : a mapped output y, given x  
* Range(치역) : set of all the output values mapped by each x in the domain  
* 선형변환  
    * $T(cu + dv) = cT(u) + dT(v)$  
