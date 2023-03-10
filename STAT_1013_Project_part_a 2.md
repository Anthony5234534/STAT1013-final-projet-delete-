---
jupyter:
  colab:
  kernelspec:
    display_name: Python 3
    name: python3
  language_info:
    name: python
  nbformat: 4
  nbformat_minor: 0
---

<div class="cell markdown" id="sLx0L25YZ64r">

# CUHK-STAT1013: Practical Assignment Part 1: Sharing Your Idea and Data

</div>

<div class="cell markdown" id="pwASQhRlaa8f">

## Intelligenzquotient test dataset background

**Description**:

The dataset is the results collected from a test which include `25`
qusetions. They can probably test a human Intelligenzquotient.

**Kaggle**:
<https://www.kaggle.com/datasets/yamqwe/training-ml-models-to-defeat-human-iq-tests>

**Sample size**: 400

**Feature documentation**:

| Feature Dtype | Dtype |
|---------------|-------|
| Q1            | int64 |
| Q2            | int64 |
| Q3            | int64 |
| Q4            | int64 |
| Q5            | int64 |
| Q6            | int64 |
| Q7            | int64 |
| Q8            | int64 |
| Q9            | int64 |
| Q10           | int64 |
| Q11           | int64 |
| Q12           | int64 |
| Q13           | int64 |
| Q14           | int64 |
| Q15           | int64 |
| Q16           | int64 |
| Q17           | int64 |
| Q18           | int64 |
| Q19           | int64 |
| Q20           | int64 |
| Q21           | int64 |
| Q22           | int64 |
| Q23           | int64 |
| Q24           | int64 |
| Q25           | int64 |
| score         | int64 |
| gender        | int64 |
| age           | int64 |

</div>

<div class="cell markdown" id="y-AGMeiW3fYb">

## Hypothesis

-   Tell us what your idea is and why you have chosen to pursue this
    idea.
    -   I am interested in "Do adult female has different
        Intelligenzquotient than that of male ?"
    -   As we can see, female always have a higer ability in study, for
        example, higher percentage of female students can get into
        university through HKDSE. However, most of the people believe
        that male are good at mathmetical in traditional Culture.
        Therefore, I want to investigate the difference of IQ including
        short-term memory, reasoning and verbal abaility between male
        and female.
-   What two groups you are comparing:
    -   **G1**: average score of male in the test; **G2**: average score
        of female in the test
-   What you will be measuring (i.e., what your response variable will
    be)
    -   `total score of the test`
-   Is your response variable quantitative rather than categorical?
    -   `score` are ratio data, which can be regarded as a quantitative
        variable.
-   Make a prediction about what kind of difference you expect to see
    between your samples and WHY.
    -   We'd expect that **G1** \> **G2** since [Males were found to
        have a larger overall brain volume than
        women.](https://www.nicswell.co.uk/health-news/mens-and-womens-brains-found-to-be-different-sizes).
-   Talk about how you will gather your data
    -   From Kaggle, Yam Peleg have already set a test to investigate Iq
        of respondents and the results are collected:
        <https://www.kaggle.com/datasets/yamqwe/training-ml-models-to-defeat-human-iq-tests>
-   If you had unlimited resources (time, money, staff, etc.) how would
    you collect your data?
    -   I will set the test by myself as well as read a great deal of
        research about Intelligenzquotient so that I can set some
        perfect questions to investigate human IQ accurately.
    -   I will send the test to the whole world so that everyone have
        the same chance to do the test. (by simple random sampling )

</div>

<div class="cell markdown" id="PXDb_qD3ziHZ">


</div>

<div class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:233}"
id="_Dziz3y-zq7G" outputId="37af0a5b-3541-4ead-f3e0-d28259dc7b05">

## First 5 row of the data set

<div class="output execute_result" execution_count="13">

       Q1  Q2  Q3  Q4  Q5  Q6  Q7  Q8  Q9  Q10  ...  Q19  Q20  Q21  Q22  Q23  Q24  \
    0  10  10  10   2   3   2   3  10  10   10  ...    3    0    0    3   10   10   
    1  10  10  10  10  10  10   3  10  10   10  ...    7    7    2    7    2   10   
    2  10  10  10   3  10  10   2   5  10    1  ...    2    4    6    3   10   10   
    3  10  10   7   3   2   7   3   6  10   10  ...    4    6    5    6    6   10   
    4  10  10  10   3   3  10   1  10  10    2  ...   10   10    6    1    3    7   

       Q25  score  gender  age  
    0    4     14       1   23  
    1   10     17       1   18  
    2    5      9       1   43  
    3    5      5       2   50  
    4   10     11       1   44  

    [5 rows x 28 columns]

</div>

</div>

<div class="cell markdown" id="48VxT8VMGsIh">

-   Tell us what groups you want to compare in the dataset
    -   **G1** (score \| gender = 1) vs. **G2** (score \| gender = 2)

    `gender where 1= male, 2=female`

</div>

<div class="cell markdown" id="KCW49fLGHy2n">

</div>

<div class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
id="ymMuyhJyHz1j" outputId="3ddd878e-08fe-4479-9b70-39dd14d90950">

## First 5 records of G1 (male)

<div class="output execute_result" execution_count="14">

    0    14
    1    17
    2     9
    4    11
    5     9
    Name: score, dtype: int64

</div>

</div>

<div class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;}"
id="IiqeiY26J--K" outputId="1513b482-bfc2-4cf6-b33c-e9c474c64195">

## First 5 records of G2 (female)


<div class="output execute_result" execution_count="15">

    3      5
    7      8
    25    15
    27     4
    29    13
    Name: score, dtype: int64

</div>

</div>

<div class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:645}"
id="RzS1rBmwOEuQ" outputId="c4426e16-4c91-4f2c-d33f-dfe322e9fc85">

## data description 
<div class="output stream stdout">

    number of male repondents=
    284
    number of female repondents=
    115
    average score of male respondents=
    12.714788732394366
    average score of female respondents=
    11.304347826086957
    average score of male respondents=
    12.714788732394366
    average score of female respondents=
    11.304347826086957
    sample std of score on male respondents=
    4.914066449674451
    sample std of score on female respondents=
    4.450850328856901

## Data visualization (score to gender)
</div>

<div class="output display_data">

![](data:image/png;base64,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)

</div>

</div>

<div class="cell markdown" id="H6F02842Qfvs">

## Using the hypothesis test to test can it be concluded at alpha =0.05
that the average score of male is higer than that of female ? u1=
population mean of score of male ; u2= population mean of score of
female

H0: u1=u2 H1: u1>u2

![formula](https://vitalflux.com/wp-content/uploads/2022/01/t-statistics-given-the-population-standard-deviations-are-unequal.jpg)

$$
t={{(12.7-11.3）-0} \\over\\sqrt{{{4.91^2}\\over284} + {{4.45^2}\\over 115}}}=2.76
$$

Since degree of freedom =114, alhpa = 0.05 and the test is one tailed
test so critical value is t ≈ 1.660 which is smaller than test value
=2.76.

Thus rejuct H0, and it can be concluded that the average score of male
is higer than that of female.

</div>
