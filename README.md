# Combinatorial Optimization (MO824) - Assignment 1

- [Original Brief](enunciado.pdf)
- [Report](relatorio.pdf)

## 1 Goal

Model a linear-programming problem and solve it with **Gurobi**. Work in teams of **2 - 3 students** (teams of two earn a bonus).

## 2 Problem description

A company has **F** factories that must meet the demand of **J** customers.
Each factory can choose among **L** machines and **M** raw-material types to produce **P** product types.
The task is to create a production-and-shipping plan that **minimises total cost** by deciding:

* how much of each product to make on each machine at each factory, and
* how much of each product to ship from each factory to each customer.

Parameters

| Symbol      | Meaning                                                                      |
| ----------- | ---------------------------------------------------------------------------- |
| $D_{j,p}$   | Demand (t) of customer **j** for product **p**                               |
| $r_{m,p,l}$ | Raw material **m** (t) needed per tonne of product **p** on machine **l**    |
| $R_{m,f}$   | Available raw material **m** (t) at factory **f**                            |
| $C_{l,f}$   | Production capacity (t) of machine **l** at factory **f**                    |
| $p_{p,l,f}$ | Production cost (per t) of product **p** on machine **l** at factory **f**   |
| $t_{p,f,j}$ | Transport cost (per t) of product **p** from factory **f** to customer **j** |

---

## 3 Assignment requirements

### 3.1 Model formulation

Write the complete **linear-programming model**, defining decision variables and constraints.

### 3.2 Instance generation

Create **10 random instances** with $|J| = \{100,200,\dots,1000\}$ and sample the remaining parameters **uniformly over the integer ranges**:

| Parameter   | Range        |   |          |   |     |   |    |
| ----------- | ------------ | - | -------- | - | --- | - | -- |
| (           | F            | ) | (\[      | J | , 2 | J | ]) |
| (           | L            | ) | $[5,10]$ |   |     |   |    |
| (           | M            | ) | $[5,10]$ |   |     |   |    |
| (           | P            | ) | $[5,10]$ |   |     |   |    |
| $D_{j,p}$   | $[10,20]$    |   |          |   |     |   |    |
| $r_{m,p,l}$ | $[1,5]$      |   |          |   |     |   |    |
| $R_{m,f}$   | $[800,1000]$ |   |          |   |     |   |    |
| $C_{l,f}$   | $[80,100]$   |   |          |   |     |   |    |
| $p_{p,l,f}$ | $[10,100]$   |   |          |   |     |   |    |
| $t_{p,f,j}$ | $[10,20]$    |   |          |   |     |   |    |

### 3.3 Experiments

Solve all ten instances with **Gurobi**. Record the **run time** and **solution cost**.

### 3.4 Submission

Turn in:

- **Source code**
- The **generated instances**
- A **\~3-page report** containing
  - **Mathematical model** - variables, parameters, constraints
  - **Results table** - variables count, constraints count, solution cost, run time per instance
  - **Analysis** - discuss solution costs and computational times

### 3.5 Grading criteria

| Aspect          | What matters                                                       |
| --------------- | ------------------------------------------------------------------ |
| **Text**        | Clarity, concision, structure                                      |
| **Model**       | Correct definitions of variables, parameters, constraints, domains |
| **Experiments** | Machine setup, instance generation, programming language           |
| **Analysis**    | Insight into solution quality and computational effort             |

---

## 4 References

1. *Installing and licensing Gurobi* - [https://www.gurobi.com/documentation/9.0/quickstart\_linux/index.html](https://www.gurobi.com/documentation/9.0/quickstart_linux/index.html)
2. *Gurobi example code* - [https://www.gurobi.com/resource/functional-code-examples/](https://www.gurobi.com/resource/functional-code-examples/)
