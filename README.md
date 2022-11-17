## veritasium-fft-dft

This repo looks at seismometer data and builds a dft and fft algorithm based on the Veritasium Video: https://youtu.be/nmgFG7PUHfo

## how did veritasium explain the dft?

first import n numbers of sample points
then construct as many bins as there are sample points.
these represent harmonic frequencies starting from the fundamental
the fundamental is created from the period of the sample signal.
then multiply by the pure sine wave, and get the integral
multiply by the pure cosine wave, and get the integral
these coefficients fill the bin for the nth harmonic.
then we can try locally reconstructing the wave by adding them all up.

## COMPUTATIONAL DETAILS
where to get data? US land geo/NASA might have some.

how to store the complex numbers in the bins?
use numpy -- store a complex number

# how to compute the "integral"?
ok well its not a real integral, 
simply iterating through each of the points.
and multiplying by the exact value of cosine wave at that point.

# how to keep track of the sums?
I think z += +4i should work
i.e. z[n] += nth_cosine_integral*i