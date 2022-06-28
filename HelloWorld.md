## This is a markdown file
I will use this markdown to test and practice different commands in R

# R objects


## Vectors
R objects have classes  
- numeric  
- logical  
- character  
- integer  
- complex  

R vectors can contain any of a single type of these classes. Lists but not vectors can contain multiple types of different classes. 

```
a <- c(1, 2, 3, 4, 5)
b <- vector("logical", length = 3)
c <- c("z", "y", "x")
d <- 1:10
e <- c(0+1i, 3+3i)
f <- list("t", F, 7.5, 6L)
cat(class(a), "-", a, "\n", class(b),"-", b, "\n",class(c), "-",c, "\n", class(d), "-", d, "\n", class(e), "-", e)
print(f)

```

If you try to make a vector with mixed classes, R will coerce each element of the vector into the least common denominator compared with the other elements.

```
g <- c(FALSE, 5)
h <- c("u", T)
i <- c(7, "p")
cat(class(g), "-", g, "\n", class(h), "-", h, "\n", class(i), "-", i)

```

You can convert vectors of one class into another with some exceptions

```

cat(as.logical(g),"\n",as.character(a), "\n", as.complex(d))


```

## Matrices

In R, matrices are filled by column.

```

a <- matrix(1:10, nrow = 2, ncol = 5)
print(a)

```

You can apply matrix dimensions to an existing vector

```

dim(d) <- c(5,2)
print(d)

```

You can also bind separate vectors together to create a new matrix.

```

bb <- cbind(b, c)
print(bb)

cc <- rbind(b, c)
print(cc)

```

## Factors

Factors are objects that hold categorical values like "male", "female", "yes", "no". These are helpful because the relevance of the value is encoded in the object itself. You can think of factors as a set of integers where each integer has a label.You can apply factors to an existing vector. Factors are treated specially by modeling functions like 'lm()' and 'glm()'

```

b <- c(b, T)
dd <- factor(b)
dd
unclass(dd)
print(dd)

```

Factors can be ordered or unordered. You can change which level is determined to be "baseline". The default baseline is whichever factor comes first in the alphabet.

```

dd <- factor(b, levels <- c("TRUE", "FALSE"))
print(dd)


```

## Dataframes

Data frames are similar to matrices in that you can store data in tabular form. However, unlike matrices, each element (column) in the dataframe can store a different class of data. Each element in the dataframe needs to be the same length. Dataframes are usually created by calling 'read.csv()' or 'read.table()'. You can convert a dataframe to a matrix using 'data.matrix()'. You can also create a dataframe using 'data.frame(<element1>, <element2>, <...>)'


### Naming objects

R can add names to objects such as elements of vectors, lists, and matrices.

```

gg <- c(g, 7, 13)
names(gg) <- c("first", "second", "third", "fourth")
print(gg)

```

You can also add a names attribute to a matrix in which case each row and column will be named.

```

dimnames(d) <- list(c("uno", "dos", "tres", "quat", "cinc"), c("foo", "bar"))
print(d)

```


