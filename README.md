# Quantum Computing Laboratory: Fault-Tolerant Hadamard Gate Implementation

This repository contains the code and material developed for **Practice 3 of the Quantum Information course**. The project focuses on the implementation and simulation of a **Fault-Tolerant Logical Hadamard Gate** using the **Steane Error Correction Code [7,1,3]** via a direct matrix algebra approach.

---

## Objective

The main goal is to implement and validate a fundamental circuit for fault-tolerant quantum computation. The key objectives are:

1.  **Implement the Steane Code [7,1,3]:** Construct the encoding and decoding unitary matrices for the code.
2.  **Stabilizer Verification:** Define and verify the six stabilizer generators of the code using Pauli operators.
3.  **Design the Logical Gate:** Implement the **Logical Hadamard Gate** ($H_L$) in a **transversal** manner to ensure fault tolerance.
4.  **Simulate Noise:** Apply a simple depolarizing noise channel to simulate errors on the physical qubits.
5.  **Analyze the Error Rate:** Compare the physical error rate ($p$) with the logical error rate ($p_L$) to validate the principle of correction.

---

## Theoretical Background

### The Steane Code [7,1,3]
The **Steane code** is one of the earliest and most important **Stabilizer Codes**. it protects **one logical qubit** against any **single physical qubit Pauli error** (X, Y, or Z) using **seven physical qubits** ($[[7,1,3]]$). The code subspace is the 1-dimensional subspace stabilized by six independent stabilizer generators.

### Fault Tolerance
The **Logical Hadamard Gate** ($H_L$) is implemented **transversally**: the Hadamard operation ($H$) is applied individually to each of the 7 physical qubits, which ensures that a single error does not propagate into multiple errors.

$$H_L = H \otimes H \otimes H \otimes H \otimes H \otimes H \otimes H$$

The simulation demonstrates the **threshold theorem** property, where the logical error probability $p_L$ scales quadratically with the physical error probability $p$ for small $p$ (behavior: **$p_L \sim p^2$**).

---

## Project Structure

The notebook `Practica3ICIgnacioLopezLuisGustavo.ipynb` performs the following tasks using **matrix algebra** (operations on $128 \times 128$ matrices):

1.  **Base Matrices:** Definition of Pauli operators ($I, X, Y, Z$) and the Hadamard matrix.
2.  **Code Verification:** Construction of the logical states $|0_L\rangle$ and $|1_L\rangle$.
3.  **Logical Circuit:** Definition of the $H_L$ matrix via the tensor product.
4.  **Noise Simulation:** Application of the depolarizing channel, followed by error detection and correction.
5.  **Error Rate Analysis:** Demonstration of the reduction in the logical error probability $p_L$.

## Key Results

* **Successful Implementation:** The Steane code $[[7,1,3]]$ was implemented and verified using matrix methods.
* **Functional Correction:** Single physical qubit errors were successfully detected and corrected.
* **Fault-Tolerance Validation:** The transversal Hadamard gate preserved the error structure.
* **Fidelity Improvement:** The simulation showed a substantial improvement in the protected state's fidelity.

---

## Requirements and Installation

This project primarily relies on standard Python libraries for linear algebra.

### Prerequisites
* Python 3.8+
* Jupyter Notebook

### Installation of Dependencies
The code mainly requires scientific computing libraries:

```bash
pip install numpy scipy matplotlib
