# AdvanceMaths
Learning Probability Density Functions using Roll-Number-Parameterized Non-Linear Model

A Python implementation for learning probability density function (PDF) parameters from transformed air quality data using maximum likelihood estimation (MLE).

📌 Overview

This project demonstrates how a roll-number-parameterized non-linear transformation can be applied to real-world environmental data to learn the parameters of a probability density function.
The analysis uses NO₂ (Nitrogen Dioxide) concentration data from the India Air Quality Dataset to estimate the parameters of a Gaussian-like distribution.

🎯 Objectives

Data Transformation
Apply a roll-number-dependent non-linear transformation to NO₂ measurements.

Parameter Learning
Estimate the parameters (λ, μ, c) of a Gaussian-like probability density function.

Statistical Analysis
Use maximum likelihood estimation to fit the distribution to transformed data.

📊 Dataset

Source: India Air Quality Dataset

Feature Used: NO₂ (Nitrogen Dioxide) concentration levels (µg/m³)

🧠 Methodology
Step 1: Non-Linear Transformation

Each NO₂ value 
𝑥
x is transformed into 
𝑧
z using the roll-number-parameterized function:

𝑧
=
𝑇
𝑟
(
𝑥
)
=
𝑥
+
𝑎
𝑟
⋅
sin
⁡
(
𝑏
𝑟
⋅
𝑥
)
z=T
r
	​

(x)=x+a
r
	​

⋅sin(b
r
	​

⋅x)

Where:

𝑎
𝑟
=
0.05
×
(
𝑟
 
m
o
d
 
7
)
a
r
	​

=0.05×(rmod7)

𝑏
𝑟
=
0.3
×
(
𝑟
 
m
o
d
 
5
+
1
)
b
r
	​

=0.3×(rmod5+1)

𝑟
r = University Roll Number (102317146)

Calculated Parameters

𝑎
𝑟
=
0.20
a
r
	​

=0.20

𝑏
𝑟
=
0.60
b
r
	​

=0.60

Step 2: Probability Density Function

The transformed data is modeled using the following Gaussian-like PDF:

𝑝
^
(
𝑧
)
=
𝑐
⋅
𝑒
−
𝜆
(
𝑧
−
𝜇
)
2
p
^
	​

(z)=c⋅e
−λ(z−μ)
2

Where:

𝜇
μ : Mean of the transformed variable

𝜆
λ : Precision parameter (controls spread)

𝑐
c : Normalization constant

Estimated Parameters

Mean (μ): 32.89

Standard Deviation (σ): 20.58

λ: 0.00118  ( 
𝜆
=
1
2
𝜎
2
λ=
2σ
2
1
	​

 )

c: 0.01940  ( 
𝑐
=
1
𝜎
2
𝜋
c=
σ
2π
	​

1
	​

 )

Step 3: Visualization

The notebook includes:

Histogram of transformed NO₂ data

Overlaid fitted probability density function

Visual comparison of empirical and theoretical distributions

🛠 Technologies Used

Python 3.12.12

NumPy – Numerical computations

Pandas – Data manipulation and analysis

Matplotlib – Data visualization

Kaggle Environment – Dataset access and execution

✅ Results

Successful Transformation:
NO₂ data is transformed using a roll-number-parameterized non-linear model.

Parameter Estimation:
Distribution parameters are derived using sample statistics and MLE principles.

Distribution Fitting:
The fitted Gaussian-like distribution reasonably approximates the transformed data.

Visual Validation:
Histogram and PDF overlay confirm a good empirical-theoretical match.

📐 Mathematical Details

Standard Gaussian PDF:

𝑝
^
(
𝑧
)
=
1
𝜎
2
𝜋
⋅
𝑒
−
(
𝑧
−
𝜇
)
2
2
𝜎
2
p
^
	​

(z)=
σ
2π
	​

1
	​

⋅e
−
2σ
2
(z−μ)
2
	​


Reparameterized as:

𝑝
^
(
𝑧
)
=
𝑐
⋅
𝑒
−
𝜆
(
𝑧
−
𝜇
)
2
p
^
	​

(z)=c⋅e
−λ(z−μ)
2

Where:

𝜆
=
1
2
𝜎
2
λ=
2σ
2
1
	​


𝑐
=
1
𝜎
2
𝜋
c=
σ
2π
	​

1
	​


🔍 Key Findings

Transformed NO₂ data approximately follows a normal distribution

Mean: 32.89 µg/m³

Standard Deviation: 20.58 µg/m³

The non-linear transformation introduces slight skewness while preserving distribution shape

🎓 Educational Value

This project demonstrates:

Working with real-world environmental datasets

Applying roll-number-based mathematical transformations

Parameter estimation using maximum likelihood concepts

Probability density function fitting

Statistical visualization and interpretation
