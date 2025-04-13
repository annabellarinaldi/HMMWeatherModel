# HMMWeatherModel

This project models the relationship between daily weather and ice cream consumption using a Hidden Markov Model (HMM). It was completed as part of COMP 560: Artificial Intelligence at UNC Chapel Hill.

---

## 🧊 Project Overview

Johnathan, a devoted TA and ice cream lover, tends to eat more ice cream on warmer days. Given a sequence of observed ice cream servings, this project uses a Hidden Markov Model (HMM) to infer the most likely sequence of temperatures (hot, warm, cold) over a span of days.

- **Hidden states**: Temperature (0 = hot, 1 = warm, 2 = cold)  
- **Observed states**: Ice cream servings per day (0, 1, or 2)

---

## 📊 Objectives

### Part A: Exact Inference

#### 🔹 Joint Probability
Implemented a function to calculate the joint probability:  
\[
P(Y_1, ..., Y_n, X_1, ..., X_n)
\]  
where \( Y \) represents temperature (hidden) and \( X \) represents observed ice cream consumption.

#### 🔹 Most Likely Sequences (Complete Enumeration)
- Enumerated all possible hidden temperature sequences  
- Calculated the posterior distribution:  
\[
P(Y_1, ..., Y_n \mid X_1, ..., X_n)
\]  
- Sorted and returned the top 10 most probable temperature sequences along with their joint probabilities

---

### Part B: Gibbs Sampling

#### 🔹 Conditional Weights
Implemented a function to compute:  
\[
P(Y_i = y \mid Y_{i-1}, Y_{i+1}, X_i)
\]  
Used this for iterative resampling in the Gibbs sampler.

#### 🔹 Gibbs Sampler
- Sampled new values for each hidden state across multiple iterations  
- Collected 5000 samples of temperature sequences  
- Used sample frequencies to approximate the posterior distribution

#### 🔹 Likely Hidden States (Sampling-Based Inference)
- Counted frequency of each sampled sequence  
- Reported the top 10 most probable sequences and compared them with the exact inference results

---

## 🛠️ Tools and Technologies

- **Language**: Python  
- **Platform**: Google Colab  
- **Libraries**: NumPy, random  
- **Techniques**: Hidden Markov Models, Complete Enumeration, Gibbs Sampling

---

## 📁 File Structure

- `HMM.py`: Starter HMM class with transition, emission, and initial distributions  
- `main.ipynb`: Implementation and results  
- `README.md`: You’re here!

---

## 🧠 Key Concepts

- Joint and conditional probability  
- Hidden Markov Models (HMMs)  
- Complete enumeration of hidden sequences  
- Gibbs sampling for approximate inference  

---

## 🚀 How to Run

1. Open `main.ipynb` in Google Colab  
2. Define an observed sequence of ice cream servings (e.g., `X = [0, 2, 1, 2, 0]`)  
3. Run all cells to:
   - Calculate joint probabilities
   - Rank sequences by posterior probability
   - Run Gibbs sampling and compare results

---
