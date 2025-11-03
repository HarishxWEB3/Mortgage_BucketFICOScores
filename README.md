📘 Mortgage Bucket FICO Scores – Quant Credit Risk Modelling
🧠 Overview

Mortgage Bucket FICO Scores is an advanced quantitative credit-risk modelling project that applies data science, probability theory, and optimization to mortgage loan portfolios.
The goal is to evaluate borrower risk tiers using FICO score buckets and build models that estimate expected loss, default probability, and optimal pricing structures under dynamic market conditions.

This notebook simulates how quant researchers at leading financial firms use statistical learning, dynamic programming, and optimization to manage portfolio risk and improve capital efficiency.

🎯 Objective

To construct a data-driven model that segments mortgage borrowers by FICO score buckets and predicts risk metrics such as:

Probability of Default (PD)

Expected Loss (EL)

Risk-Adjusted Return (RAR)

The outcome helps financial institutions quantize credit risk and design pricing models that align with both profitability and regulatory capital constraints.

🧩 Core Mathematical Foundations
1. Dynamic Programming for Risk Optimization

Dynamic programming (DP) is used to compute optimal decisions over time — such as when to approve, reject, or price a loan based on evolving borrower risk.

General form:

V(s) = max_a [ R(s, a) + γ * Σ P(s' | s, a) * V(s') ]

Where:

V(s) → Value function of state s (expected long-term return)

a → Action (approve, reject, reprice)

R(s, a) → Immediate reward (profit or cost)

γ → Discount factor (time value of money)

P(s' | s, a) → Probability of transitioning to new state s'

2. Mean Squared Error (MSE)

Used to evaluate model performance and ensure predictive accuracy for default probability estimations.

MSE = (1/n) * Σ (yᵢ − ŷᵢ)²

Where:

yᵢ → Actual default indicator

ŷᵢ → Predicted probability of default

n → Number of observations

A lower MSE implies higher predictive accuracy.

3. Log-Likelihood Function

The likelihood quantifies how well model parameters fit observed data. In logistic regression for credit default:

L(β) = Σ [ yᵢ * log(pᵢ) + (1 − yᵢ) * log(1 − pᵢ) ]

Where pᵢ = 1 / (1 + exp(−βᵀxᵢ)).
Maximizing the log-likelihood gives the most probable parameter estimates for borrower risk.

4. Quantization of Credit Risk

Credit risk is discretized into FICO score buckets or quantized risk classes. Each bucket captures a homogeneous group of borrowers for which expected loss is computed as:

Expected Loss (EL) = PD × LGD × EAD

Where:

PD → Probability of Default

LGD → Loss Given Default

EAD → Exposure at Default

Quantization allows efficient portfolio segmentation and stress-testing under changing economic conditions.

🧰 Tech Stack

Language: Python
Libraries: NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, SciPy, Joblib
Environment: Jupyter Notebook
Version Control: Git & GitHub

⚙️ Setup

Clone the repository and install dependencies:

git clone https://github.com/HarishxWEB3/Mortgage_BucketFICOScores.git
cd Mortgage_BucketFICOScores
pip install -r requirements.txt


Then launch the notebook:

jupyter notebook Mortgage_BucketFICOScores.ipynb

📈 Insights

Built multi-stage dynamic programming model for portfolio optimization

Quantized credit risk into discrete FICO buckets

Evaluated predictive performance with MSE and log-likelihood

Simulated macro-economic stress impacts on default probabilities

Provided visualizations for expected loss across score tiers

💡 Future Enhancements

Integrate Bayesian inference for uncertainty estimation

Deploy model as an interactive credit risk dashboard

Add Monte Carlo simulations for scenario testing

Incorporate macro-economic covariates (e.g., unemployment, inflation)

👨‍💻 Author

Harish R
Aspiring Quant Researcher | AI & Finance Engineer
🌐 GitHub Profile

🧾 License

This project is open-source and available under the MIT License.
