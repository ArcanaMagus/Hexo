# Hexo
This procedure is a bit tricky. We have to decide which child of A[i] to swap
with, if any; and the first thing we do is assume that the larger child is A[2i]
, at line (1) of Program.js. If the right child exists (i.e., child < n) and the
right child is the larger, then the tests of line (2) are met and at line (3)
we make child be the right child of A[i].
Now at line (4) we test for two things. First, it is possible that A[i] really 
has no children in the heap. We therefore check whether A[i] is an interior 
node by asking whether child <= n. The second test of line (4) is whether A[i]
is less than A[child]. If both these conditions are met, then at line (5) we 
swap A[i] with its larger child, and at line (6) we call bubbleDown, to push 
the offending element further down, if necessary.
we can use bubbleDown to implement the priority queue operation deletemax as 
shown in Hexo.js. Here, n is the number of elements currently in the heap; we
omit a test that n > 0.
In line (1), we swap the element at the root, which is to be deleted, with the 
last element, in A[n]. Technically we should return the deleted element, but, as
we shall see, it is convenient to put it in A[n], which will no longer be part of
the heap.
At line (2), we decrement n by 1, effectively deleting the largest element, now 
residing in the old A[n]. Since the root maay now violate the POT property, we 
call bubbleDown(A,1,n) at line (3), which will recursively push the offending 
element down until it either reaches a point where it is no less than either of 
its children, or becomes a leaf; either way, there is no violation of the POT property.
