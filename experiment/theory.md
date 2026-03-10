





#### 1. What is Integer Factorization?

Integer factorization is the process of decomposing a composite number into its prime factors.

Example:

15 = 3 × 5

For small numbers this is simple, but for very large numbers (hundreds of digits), factorization becomes computationally difficult.

Modern cryptographic systems like RSA rely on this classical difficulty.

Shor’s Algorithm provides a quantum solution to factor large integers efficiently.



#### 2. Why is Factorization Hard Classically?

Classical factorization algorithms include:

- Trial Division
- Pollard’s Rho Algorithm
- Number Field Sieve

These methods require exponential or sub-exponential time for large inputs.

As the number size increases, the required computation time increases dramatically.

Quantum computing offers a polynomial-time alternative.



#### 3. What is Shor’s Algorithm?

Shor’s Algorithm is a quantum algorithm introduced in 1994.

It factors large integers efficiently by reducing the problem to a period-finding problem.

The algorithm combines:

- Quantum parallelism
- Modular exponentiation
- Quantum Fourier Transform (QFT)
- Classical post-processing



#### 4. Core Idea: Period Finding

To factor a number N:

1. Choose a number a such that:
   1 < a < N

2. Define the function:
   f(x) = a^x mod N

3. This function is periodic, meaning:
   f(x + r) = f(x)

4. The goal is to find the period r.

Once r is known, factors can be computed using:

gcd(a^(r/2) ± 1, N)



#### 5. Quantum Superposition

Instead of computing f(x) for each x one by one, a quantum system prepares:

Σ |x⟩ |f(x)⟩

This allows simultaneous evaluation of many inputs using superposition.

This is known as quantum parallelism.



#### 6. Modular Exponentiation

The quantum circuit computes:

|x⟩ |0⟩ → |x⟩ |a^x mod N⟩

This step encodes the periodic structure into the quantum state.



#### 7. Quantum Fourier Transform (QFT)

The QFT is the quantum version of the Discrete Fourier Transform.

It transforms the periodic quantum state into a frequency representation.

The peaks in this representation reveal the period r.



#### 8. Measurement and Classical Post-Processing

After applying QFT:

- The system is measured
- The result provides information about the period
- Classical continued fraction methods are used to compute r
- Finally, gcd(a^(r/2) ± 1, N) gives the non-trivial factors



