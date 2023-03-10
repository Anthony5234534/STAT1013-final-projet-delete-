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

## First 5 row of data set 

</div>

<div class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:233}"
id="_Dziz3y-zq7G" outputId="37af0a5b-3541-4ead-f3e0-d28259dc7b05">



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

-   Print first 5 records of each group, respectively.

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

<div class="output stream stdout">

 ## data description 
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

 ## data visualization (score to gender)

</div>

<div class="output display_data">

![](8442b32489b5a41f7b6f0278fe5333f800150b64.png)

</div>

</div>

<div class="cell markdown" id="H6F02842Qfvs">
  
##Using the hypothesis test to test can it be concluded at alpha =0.05
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
