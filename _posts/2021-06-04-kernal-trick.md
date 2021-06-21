
The goal here is to reduce bias. We can do that by taking higher order features or probably the interactions between them. 

If we have {x_1, x_2, x_3 ... x_d} as features where d is the number of features. There is a good shot at reducing bias if we use higher order features such as {x_1^{(2)}, x_1x_2, x_1x_2x_3} and so on.

These feature computations are expensive. But, we are in luck. Turns out, if we are using gradient descent and our gradient is combination of all inputs, we can express the weights as a linear combination of the inputs. That is

\begin{equation}
w &= \sum_{i=1}^{n} \alpha_ix_i
\end{equation}

n is the number of data-points(training data-points to be specific). This can be proved for the square error as following:

INSERT PROOF HERE
## Kernel Trick

As can be seen, we don't need to calculate the weight w while optimization. Also, as it can be seen here that we don't need to calculate the weight at the test time as well:

INSERT TEST TIME EQUATION

The notable thing here is that not only we don't need to calculate the weight {w}, we don't actually calculate the features as well, only the dot product between them needs to be calculated. The update rule also needs only the dot or inner-product between features.

Now, just take a moment and appreciate what just happened. We don't need to calculate the features explicitly but only the inner products between the features. The inner-product between two features is just a number. This is what is going to allow us consider high-dimensional features as we can easily calculate the inner-product even of \textbf{infinite-dimensional} features with single computation.

Here is an example of how the polynomial feature vector can be `kernelized`

\textbf{Original features:} {x_1, x_2, x_3 ... x_d} 

\textbf{Desired features:} {1, x_1, x_2..., x_1x_2, ... , x_1x_2..x_d} \(dimension is {2^d}\)

\textbf{inner product between x and y:} {1 + x_1y_1 + x_2y_2... + x_1y_1x_2y_2,..., x_1y_1x_2y_2x_3y_3...x_dy_d}

The dot product is O({2^d}). However it can be calculated in O(d) in the following way.


INSERT KERNEL FUNCTION HERE


So, we can just use the dot product and get results of polynomial features without even calculating the features explicitly.

There are a few popular kernels:

\textbf{Linear:} This is just using raw features. Not much gain here - EQUATION

\textbf{Radial Basis Function:} This is one of the most popular kernels. The inner-product is Gaussian function with mean being the one of the features. The inner-product is calculated as the following:


INSERT EQUATION HERE.

The important note here is that this is the dot product. We have to do some thinking to reverse engineer what the feature space is. Turns out, the features vectors are polynomials of different degree and of infinite dimension.

What is the RBF kernel really doing?


Can any function be a Kernel function?


What loss function can be kernelized? What if w is not the same dimension as x?
Does the kernelization ability depends only on the loss function or the hypothesis model as well?
