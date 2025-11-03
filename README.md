🏦 Mortgage Bucket FICO Scores – Quantization \& Credit Risk Modelling

🧠 Overview



Mortgage Bucket FICO Scores is a quantitative research notebook developed under the J.P. Morgan Chase \& Co Quantitative Research Virtual Experience.

It models credit risk segmentation by quantizing borrower credit scores into risk buckets and applying dynamic programming to optimize loan portfolio allocation and minimize expected losses.



The project explores how statistical learning, optimization theory, and probabilistic inference converge in modern credit analytics — the same framework used by quant teams at Jane Street, Goldman Sachs, and J.P. Morgan.



💹 Objective



To design a model that dynamically estimates credit risk using FICO score segmentation, combining:



Quantization theory to discretize continuous risk variables,



Dynamic programming for portfolio optimization, and



Statistical estimation (Mean Squared Error \& Log-Likelihood) for model calibration.



The result: a system that identifies optimal lending decisions while maintaining capital efficiency and regulatory compliance.



📊 Key Components



Quantization of FICO scores into discrete risk buckets



Portfolio optimization using Dynamic Programming (DP)



Loss function minimization via Mean Squared Error (MSE)



Model calibration using Log-Likelihood Estimation (LLE)



Risk visualization and sensitivity analysis



Comparison of deterministic vs stochastic credit risk models



🧮 Core Mathematical Framework

🔹 1. Quantization of Credit Risk



Let 

𝑋

X be a continuous credit score variable. Quantization maps it into discrete buckets 

𝑄

(

𝑋

)

Q(X):



𝑄

(

𝑋

)

=

𝑞

𝑖

if 

𝑋

∈

\[

𝑏

𝑖

,

𝑏

𝑖

\+

1

)

Q(X)=q

i

&nbsp;	​



if X∈\[b

i

&nbsp;	​



,b

i+1

&nbsp;	​



)



Each bucket 

𝑞

𝑖

q

i

&nbsp;	​



&nbsp;represents a FICO risk segment, allowing the model to treat heterogeneous borrowers as homogeneous risk groups for statistical estimation.



🔹 2. Dynamic Programming (DP) Optimization



Define 

𝑉

𝑡

(

𝑠

)

V

t

&nbsp;	​



(s) as the maximum expected profit at time 

𝑡

t given state 

𝑠

s (e.g., loan portfolio composition).



The Bellman Equation for credit risk decision-making:



𝑉

𝑡

(

𝑠

)

=

max

⁡

𝑎

∈

𝐴

\[

𝑅

𝑡

(

𝑠

,

𝑎

)

\+

𝛾

 

𝐸

\[

𝑉

𝑡

\+

1

(

𝑠

′

)

∣

𝑠

,

𝑎

]

]

V

t

&nbsp;	​



(s)=

a∈A

max

&nbsp;	​



\[R

t

&nbsp;	​



(s,a)+γE\[V

t+1

&nbsp;	​



(s

′

)∣s,a]]



Where:



𝑅

𝑡

(

𝑠

,

𝑎

)

R

t

&nbsp;	​



(s,a) = immediate reward (profit or loss from lending decision)



𝛾

γ = discount factor



𝑠

′

s

′

&nbsp;= next state determined by borrower behavior and default probability



This allows optimal policy computation — determining lending actions that minimize long-term expected default loss.



🔹 3. Mean Squared Error (MSE)



Used to measure model prediction accuracy:



𝑀

𝑆

𝐸

=

1

𝑛

∑

𝑖

=

1

𝑛

(

𝑦

𝑖

−

𝑦

^

𝑖

)

2

MSE=

n

1

&nbsp;	​



i=1

∑

n

&nbsp;	​



(y

i

&nbsp;	​



−

y

^

&nbsp;	​



i

&nbsp;	​



)

2



Where:



𝑦

𝑖

y

i

&nbsp;	​



&nbsp;= actual default indicator (0 or 1)



𝑦

^

𝑖

y

^

&nbsp;	​



i

&nbsp;	​



&nbsp;= predicted default probability



MSE penalizes large prediction errors and aids in hyperparameter tuning for robust risk estimation.



🔹 4. Log-Likelihood Estimation



For logistic regression–based credit models, the Log-Likelihood (LL) function is given as:



ln

⁡

𝐿

(

𝛽

)

=

∑

𝑖

=

1

𝑛

\[

𝑦

𝑖

ln

⁡

(

𝑝

𝑖

)

\+

(

1

−

𝑦

𝑖

)

ln

⁡

(

1

−

𝑝

𝑖

)

]

lnL(β)=

i=1

∑

n

&nbsp;	​



\[y

i

&nbsp;	​



ln(p

i

&nbsp;	​



)+(1−y

i

&nbsp;	​



)ln(1−p

i

&nbsp;	​



)]



Where:



𝑝

𝑖

=

𝑃

(

𝑌

𝑖

=

1

∣

𝑋

𝑖

)

=

1

1

\+

𝑒

−

(

𝛽

0

\+

𝛽

𝑋

𝑖

)

p

i

&nbsp;	​



=P(Y

i

&nbsp;	​



=1∣X

i

&nbsp;	​



)=

1+e

−(β

0

&nbsp;	​



\+βX

i

&nbsp;	​



)

1

&nbsp;	​





𝑌

𝑖

Y

i

&nbsp;	​



&nbsp;= binary default outcome



𝑋

𝑖

X

i

&nbsp;	​



&nbsp;= borrower features



Maximizing this log-likelihood ensures that the model parameters 

𝛽

β best explain the observed defaults.



🧰 Tech Stack



Language: Python

Libraries: NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn, SciPy

Optimization Tools: Numpy vectorization, Dynamic Programming (custom implementation)

Environment: Jupyter Notebook

Version Control: Git \& GitHub



⚙️ Setup



Clone the repository and install dependencies:



git clone https://github.com/HarishxWEB3/Mortgage\_BucketFICOScores.git

cd Mortgage\_BucketFICOScores

pip install -r requirements.txt





Run the notebook:



jupyter notebook Mortgage\_BucketFICOScores.ipynb



📈 Insights



Quantized borrower segments improve credit score interpretability



Dynamic programming minimizes expected loss over lending horizon



MSE and Log-Likelihood metrics confirm model robustness



Optimal credit allocation policy yields higher portfolio stability



💡 Future Enhancements



Integrate Markov Decision Processes (MDPs) for stochastic borrower transitions



Apply Reinforcement Learning to learn adaptive risk policies



Introduce Bayesian updating for time-dependent credit score distributions



Extend quantization to multi-dimensional borrower attributes



👨‍💻 Author



Harish R

Quant Research Enthusiast | AI \& Finance Innovator



🌐 GitHub Profile



🧾 License



This project is licensed under the MIT License — open for academic, research, and applied financial use.

