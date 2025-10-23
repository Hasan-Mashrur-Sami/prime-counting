# prime-counting
In this project, I explore Number Theory and AI. The goal is to train a neural network to learn the prime-counting function  $\pi(x)$

### Problem
The prime-counting function, $\pi(x)$, counts the number of prime numbers less than or equal to some real number $x$. 
There is no exact formula for $\pi(x)$. However, the Prime Number Theorem provides a famous approximation:
$\pi(x) \approx \frac{x}{\ln(x)}$
This project attempts to answer the question: Can we train a model to learn the true $\pi(x)$ function more accurately than this theorem?

### Method
We frame this as a simple regression task. First, we generate dataset $(x, \pi(x))$ for $x = 1,...,N=100000$. We use a simple Multi-Layer Perceptron (MLP) architecture, built using PyTorch. The model takes inpute $x$ and outputs the prediction, $\hat{\pi}(x)$.

### Comparison to Theorem
We evaluate model's performance by comparing its predictions against two benchmarks:
- The true value of $\pi(x)$ from the generated dataset.
- The theorem's approximation, $\frac{x}{\ln(x)}$.

The neural network learned a significantly more accurate approximation than the $x/\ln(x)$ formula for the range it was trained on ($x \le 100,000$). The theorem's approximation clearly underestimates the true count, and the gap widens as $x$ increases.