R-Programming---Caching-Inverse-Matrix

makeCacheMatrix <- function(x = matrix()) {
inv <- NULL
set <- function(y) {
x <<- y
inv <<- NULL
  }
get <- function() x
setInverse <- function() inv <<- solve(x) #calculate the inverse
getInverse <- function() inv
list(set = set, get = get, setInverse = setInverse, getInverse = getInverse)
}


Exemplo

x = rbind(c(5, 3/6), c(3/6, 5))
m = makeCacheMatrix(x)
m$get()
         [,1]  [,2]
   [1,]  5.0    0.5
   [2,]  0.5    5.0

cacheSolve(m)
        
            [,1]        [,2]
[1,]  0.20202020 -0.02020202
[2,] -0.02020202  0.20202020
