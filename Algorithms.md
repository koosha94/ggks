# Introduction #

GGKS provides implementations of four k selection algorithms for use on a GPU. They are bucket select, radix select, cutting plane, and a probabilistic algorithm. For more details see the descriptions below, or the documentation included with the GGKS download.

# Bucket Select #
Bucket Select is an adaptation of [bucket sort](http://en.wikipedia.org/wiki/Bucket_sort). Instead of sorting each bucket it identifies which bucket contains the kth largest element. Bucket select then applies itself recursively until either there is only one element in the bucket containing the kth largest element, or the size of the bucket is so small that there can only be one value assigned to that bucket. There are two distinct phases of bucket select.




# Radix Select #
Radix Select is a modification of [back40computing](http://code.google.com/p/back40computing/) radix sort which is now included in [thrust](http://code.google.com/p/thrust/) which is included in [CUDA 4.0](http://developer.nvidia.com/cuda-toolkit-40). In many ways it follows a similar strategy to [bucket select](Algorithms#Bucket_Select.md). It can also be thought of as a modified [most significant digit radix sort](http://en.wikipedia.org/wiki/Radix_sort#Most_significant_digit_radix_sorts). In fact the modification is, conceptually, very similar to the modification the changes bucket sort into bucket select. Where a MSD radix sort sorts the elements based on their MSD and then calls itself recursively on each grouping, radix select sorts the elements base on their MSD and then calls itself recursively on which ever bucket contains the kth largest element.



# Cutting Plane #
Cutting Plane is the algorithm described by [Gleb Beliakov](http://www.deakin.edu.au/~gleb/cp_select.html).

# Randomized Selection #
Randomized selection is GGKS implementation of the algorithm by Monroe, Wendelberger, and Michalak.