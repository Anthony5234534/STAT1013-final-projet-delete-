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

## Prepare your dataset

</div>

<div class="cell code"
colab="{&quot;base_uri&quot;:&quot;https://localhost:8080/&quot;,&quot;height&quot;:233}"
id="_Dziz3y-zq7G" outputId="37af0a5b-3541-4ead-f3e0-d28259dc7b05">

``` python
## load dataset 

import pandas as pd

df=pd.read_csv('https://storage.googleapis.com/kagglesdsdata/datasets/1647582/2762635/IQ1/data.csv?X-Goog-Algorithm=GOOG4-RSA-SHA256&X-Goog-Credential=gcp-kaggle-com%40kaggle-161607.iam.gserviceaccount.com%2F20230223%2Fauto%2Fstorage%2Fgoog4_request&X-Goog-Date=20230223T150349Z&X-Goog-Expires=259200&X-Goog-SignedHeaders=host&X-Goog-Signature=77f9a1426d9140dac44ab34f34e399119ce2a6370eaf3ce7e02bb6f71135e383c2100e7efb392a2e8eb23df0bd973bb4433cce0ffe210c89fbf3e240e455a026b8ce5e57209b3b3ed70a55a4a17a14fd13e502d966053ec6d40ebb2ba0a58b877af048a805cfca1677cd5561f041d772f094b0843f04cfe0cc372a76442d3e0e000672032f4189e275de930c31191d822e3936589f23b1ffe8b6c7076cf7aaa2d11cec57b6a43786948a8c150e9430d88dc2f4e28a5313a6414ad0ad8bd0da7dd84793acbb19cb8265d04209a84b4f859fd2b44b611bde75039010fa0c2b267b40eede82b6f95da65642a5408c6c06ae393efc647d6fb0c02d1ece53241c10e6')
df.head(5)
```

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

``` python
## First 5 records of G1 (male)
(df[df['gender'] == 1]['score']).head(5)
```

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

``` python
## First 5 records of G2 (female)
(df[df['gender'] == 2]['score']). head(5)
```

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

``` python
## Any other data description and visualization you want to add.
import matplotlib.pyplot as plt
import seaborn as sns
plt.rcParams['figure.figsize'] = [10, 5]
sns.set()

## data description 
print('number of male repondents=')
print(len(df[(df['gender']==1)]))
print('number of female repondents=')
print(len(df[(df['gender']==2)]))
print('average score of male respondents=')
print(df[df['gender']==1]['score'].mean())
print('average score of female respondents=')
print(df[df['gender']==2]['score'].mean())
print('average score of male respondents=')
print(df[df['gender']==1]['score'].mean())
print('average score of female respondents=')
print(df[df['gender']==2]['score'].mean())
print('sample std of score on male respondents=')
print(df[df['gender']==1]['score'].std())
print('sample std of score on female respondents=')
print(df[df['gender']==2]['score'].std())
print()
print('data description (score to gender)')
sns.histplot (data=df, x='score', y='gender')
plt.show()

## Open question, be flexible and no example can be provided.
## Using the hypothesis test to test can it be concluded at alpha =0.05 that the average score of male is higer than that of female ? 
```

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

    data description (score to gender)

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