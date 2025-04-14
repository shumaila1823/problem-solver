# problem-solver
 Math problem solver:      
1. Introduction

The Math Problem Solver is a Python-based software tool designed to solve mathematical problems from Algebra, Calculus, and Linear Algebra. It is ideal for students, educators, and developers who need to perform symbolic or numerical math operations quickly and efficiently.

This system uses Python libraries like SymPy (for symbolic math) and NumPy (for matrix operations) to automate complex calculations.


2. System Components

Input Module: Takes user input (type of problem, values, expressions).

Processing Module: Uses algorithms and Python libraries to solve math problems.

Output Module: Displays step-by-step or direct results to the user.

Module Structure:

algebra/: Linear and quadratic equations.

calculus/: Derivatives.

linear_algebra/: Matrix operations.

3. Class Design

For simplicity and modularity, functions are grouped logically in modules. Here’s a high-level class design:

MathSolver
├── AlgebraSolver
│   ├── solve_linear(a, b)
│   └── solve_quadratic(a, b, c)
├── CalculusSolver
│   └── find_derivative(expr)
└── MatrixSolver
    ├── matrix_addition(A, B)
    ├── matrix_multiplication(A, B)
    └── matrix_determinant(A)

These can later be turned into classes if an Object-Oriented version is needed.

4. Functionalities

Algebra Solver:

Solves linear and quadratic equations.


Calculus Solver:

Computes derivatives of mathematical expressions.


Matrix Solver:

Adds, multiplies matrices and finds their determinant.

5. Approach

1. Modular Development: Separate files for each math area.


2. Library Integration: Used SymPy for algebra/calculus and NumPy for matrix operations.


3. Interactive CLI: A simple command-line interface to take input and show output.


4. Test Cases: Included example matrices and equations for demonstration.

6. Achievements

Successfully solved symbolic and numerical math problems.

Built an expandable and modular Python application.

Applied real-world libraries to automate tasks like differentiation and matrix calculation.

Ready for future GUI/web integral.

7. Conclusion

The Math Problem Solver project demonstrates how programming can enhance learning and problem-solving in mathematics. It is an effective tool for quick calculations and can be a solid foundation for more advanced applications such as math tutors or educational software.

 Full Python Program

# main.py

from sympy import symbols, Eq, solve, diff
import numpy as np

x = symbols('x')

# Algebra Solver
def solve_linear(a, b):
    eq = Eq(a * x + b, 0)
    return solve(eq, x)

def solve_quadratic(a, b, c):
    eq = Eq(a * x**2 + b * x + c, 0)
    return solve(eq, x)

# Calculus Solver
def find_derivative(expr_str):
    expr = eval(expr_str)
    return diff(expr, x)

# Matrix Solver
def matrix_addition(A, B):
    return np.add(A, B)

def matrix_multiplication(A, B):
    return np.dot(A, B)

def matrix_determinant(A):
    return np.linalg.det(A)

# Main Program
print("\n--- Math Problem Solver ---")
print("1. Algebra\n2. Calculus\n3. Linear Algebra")
choice = input("Enter your choice: ")

if choice == '1':
    print("1. Linear Equation\n2. Quadratic Equation")
    sub = input("Choose option: ")
    if sub == '1':
        a = float(input("Enter a: "))
        b = float(input("Enter b: "))
        print("Solution:", solve_linear(a, b))
    elif sub == '2':
        a = float(input("Enter a: "))
        b = float(input("Enter b: "))
        c = float(input("Enter c: "))
        print("Solutions:", solve_quadratic(a, b, c))

elif choice == '2':
    expr = input("Enter expression in x (e.g. x**2 + 3*x): ")
    print("Derivative:", find_derivative(expr))

elif choice == '3':
    A = np.array([[1, 2], [3, 4]])
    B = np.array([[5, 6], [7, 8]])
    print("Matrix A:\n", A)
    print("Matrix B:\n", B)
    print("A + B:\n", matrix_addition(A, B))
    print("A x B:\n", matrix_multiplication(A, B))
    print("Determinant of A:", matrix_determinant(A))

else:
    print("Invalid choice")
