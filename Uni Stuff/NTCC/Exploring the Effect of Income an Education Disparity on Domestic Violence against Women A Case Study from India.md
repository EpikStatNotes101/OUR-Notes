


### $$\text{Safalya Pal - A90555919003  Sem-5}$$
### $$\text{Guide - Dr. Banhi Guha }$$
### $$\text{ }$$

---
## Abstract 
Consistently throughout the days, Domestic Violence (DV) has been linked to degrading physical and mental health and unpleasant social outcomes. Past studies have shown significant empirical evidence on the determinants of the chances of experiencing DV, but very little importance has been given to the effect of income and education disparity. This study aims to investigate the relationship between income and education disparity and DV in context of India. We use a sample of 64,582 women from the 4th National Family Health Survey (NFHS-4) for India, conducted between 2014-2015. This study uses a standard logistic regression and decision tree to assess the effect of income and education disparity levels measured by the Gini-index, on the different forms of DV: emotional, physical, and sexual. Along with income and education disparity, the analyses also have control variables for other determinants for DV that are vastly used in literature. Results show a statistically significant positive association between income and education disparity and DV in India. For the other covariates, findings show that respondent's education level, respondent's employment status, husband's education level, husband's occupation, the type of religion and caste / tribe to influence the likelihood of being a victim of DV. Policies decreasing income and education disparity would in turn decrease the level of DV against women.

Keywords : Education disparity, Income disparity, Domestic Violence, India, Women

## Introduction 
Domestic Violence is a major problem in the modern society. More than a third of women worldride have experienced some form of physical or sexual violence at least once in their lifetime. Studies show that violence against women has severe mental and physical health consequences. Domestic Violence could lead to a lot of psychological disorders such as depression, sleeping disorders and eating disorders. It also increases the risk of committing homocide or suicide. Domestic Violence also correlates with an increased rate of infant and child mortality and morbidity. 

Though there is substantial emperical evidence on the factors which determine the likelihood of a woman experiencing Domestic Violence, very little attention has been paid to the role of household income as determinant. The objective of this study is to investigate the relationship between economic status of the household of a woman and the risk of being a victim of Domestic Violence. 

## Research Methodology 
### Dataset Description 
The data used in this study has been taken from the 4th National Family Health Survey (NFHS-4) for India, conducted in 2014-2015. The NFHS, sponsored by the U.S Agency for international development. The NFHS provides data on a variety of health indicators. In this study, a representative sample of 64,582 women between age 15 to 49 (reproductive age) was used. The NFHS has a complex design which involves stratification based on the level of urbanization and region.  The complex survey design has been accounted for in the regression analysis. 

The NFHS dataset contains information of various forms of partner violence experienced by the interviewed women. Due to the sensitivity of the topic and the safety concerns of the interviewed women, NFHS-4 took a few safety precautions. This includes using a varity of questions to to increase the validity of the Domestic Violence data and providing training to the interviewers along with some other measures. 

To determine the degree of Domestic Violence, the following questions were used:

*"Does/Did your last husband ever do any of the following things: slap you? Twist your arm or pull your hair? Push you, shake you, or throw something at you? Punch you with his fist or with something that could hurt you? Kick you, drag you or beat you up? Try to choke you or burn you on purpose? Threaten or attack you with a knife, gun, or any other weapons? Physically force you to have sexual intercourse with him even when you did not want to? Force you to perform any sexual acts you did not want to?"*

Due to safety precautions and privacy, only one woman in each household was selected for the Domestic Violence module to keep information confidential.  In this study, we use 4 binary outcome variables to measure Domestic Violence. The first measure is a binary variable which indicates if a woman has experienced any emotional violence. The second measure is a binary variable which indicates if a woman has experienced less severe form of spousal violence. The third outcome variable is an indicator for whether a woman has experienced any severe form of spousal violence. The third outcome variable is a binary variable of whether a woman has experienced sexual violence. 

The NFHS dataset does not contain data on household income or expenditure.The NFHS team developed a measure of economic status of household based on ownership of assets. The wealth index  score is generated through principal components analysis, which acts as an indicator for household economic status.

### Model Description 
To determine the effect of household economic status, we used the following logistic regression model :

$$Y=\frac{1}{1+e^{-\sum_i \beta_i \; X_i}}$$

Where the dependent variable $Y$ indicates the probability of a woman experiencing a form of domestic violence and $X$ is a vector containing the independent covariates. 

We develop four dependent variables, the emotional violence, less severe physical violence, severe physical violence and sexual violence separately. 

### Analysis
An exploratory analysis showing the sample proportions and odds ratio of the output variables has been given in the tables and figures below. 

#### Table 1 : Sample proportion of Women (% of women) experiencing domestic violence

| Income Group | $\begin{align}&\text{Emotional } \\ &\text{Violence}\end{align}$ | $\begin{align}&\text{Less } \\ &\text{Severe } \\ &\text{Physical } \\ &\text{Violence}\end{align}$ | $\begin{align}&\text{Severe } \\ &\text{Physical } \\ &\text{Violence}\end{align}$ | Sexual Violence |
| ------------ | ------------------ | ----------------------------- | ------------------------ | --------------- |
| poorer       | 51.4874                   | 35.9817                       | 12.5235                         | 8.9827          |
| poor         | 49.9817                   | 31.9929                       | 10.2824                         | 7.7939          |
| middle       | 48.1026                   | 28.0817                       | 7.7164                         | 6.4516          |
| rich         | 45.8820                   | 24.6922                       | 5.7582                         | 5.5746          |
| richer       | 41.9851                   | 17.4524                       | 3.8626                         | 3.9288          |

$$\text{  }$$
$$\text{  }$$
**Figure 1 : Sample proportion of Women (% of women) experiencing emotional violence**

![[Uni Stuff/NTCC/Imgs/Pasted image 20211218202430.png|500]]

**Figure 2 : Sample proportion of Women (% of women) experiencing less severe physical violence**

![[Uni Stuff/NTCC/Imgs/Pasted image 20211218201955.png|500]]

$$\text{  }$$
$$\text{  }$$
$$\text{  }$$
$$\text{  }$$
**Figure 3 : Sample proportion of Women (% of women) experiencing severe physical violence**

![[Uni Stuff/NTCC/Imgs/Pasted image 20211218200154.png|500]]

**Figure 4 : Sample proportion of Women (% of women) experiencing sexual violence **

![[Uni Stuff/NTCC/Imgs/Pasted image 20211218195818.png|500]]

$$\text{  }$$
$$\text{  }$$
$$\text{  }$$
$$\text{  }$$
## Results
The table below represents the estimated cofficents of the logistic regression models. 

#### Table 2:

| Income Group | $\begin{align}&\text{Emotional } \\ &\text{Violence}\end{align}$ | $\begin{align}&\text{Less } \\ &\text{Severe } \\ &\text{Physical } \\ &\text{Violence}\end{align}$ | $\begin{align}&\text{Severe } \\ &\text{Physical } \\ &\text{Violence}\end{align}$ | Sexual Violence |
| ------------ | ---------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- | --------------- |
| intercept    |  0.01600958                                                      | -0.73631207                                                                                         | -2.3593667                                                                         | -2.61832845     |
| ------------ |                                                                  |                                                                                                     |                                                                                    |                 |
| poorer       |  0.20997016                                                      | 0.3296544                                                                                           | 0.6054943                                                                          | 0.39381171          |
| poor         |  0.10024693                                                      | 0.1197478                                                                                           | 0.3942434                                                                          | 0.29163483          |
| middle       |  0.02145629                                                      | -0.10179977                                                                                         | 0.07979413                                                                         | 0.07049222         |
| rich         |  -0.07635158                                                     | -0.30957698                                                                                         | -0.32807604                                                                        | -0.24908303          |
| richer       |  -0.23933021                                                     | -0.77272104                                                                                         | -0.75080525                                                                        | -0.5055281          |

Using the fitted logistic regression model, we get an estimate of the probability a woman experiencing the various forms of domestic violence, given the economic status of the household she belongs to. 

#### Table 3: Probability of experiencing domestic violence given the economic status of the woman's household (from the fitted model)

| Income Group | $\begin{align}&\text{Emotional } \\ &\text{Violence}\end{align}$ | $\begin{align}&\text{Less } \\ &\text{Severe } \\ &\text{Physical } \\ &\text{Violence}\end{align}$ | $\begin{align}&\text{Severe } \\ &\text{Physical } \\ &\text{Violence}\end{align}$ | Sexual Violence |
| ------------ | ------------------ | ----------------------------- | ------------------------ | --------------- |
| poorer       | 0.5562                   | 0.3997                       | 0.1475                         | 0.0975          |
| poor         | 0.5290                   | 0.3505                       | 0.1229                         | 0.0889          |
| middle       | 0.5093                   | 0.3019                       | 0.0928                         | 0.0725          |
| rich         | 0.4849                   | 0.2600                       | 0.0637                         | 0.0537          |
| richer       | 0.4444                   | 0.1810                       | 0.0426                         | 0.0421          |

## Conclusion 
In summary, this study finds that the prevalance of all forms of domestic violence (emotional, sexual and physical) is more among households with lower economic status than the ones with high income **(table 2)**. 

As apparent from **table 1** above, for all forms of domestic violence, the coefficients of the logistic regression models are lesser for households with higher economic status. This implies that the increase in probability of domestic violence of all forms decreases with increase in household income.  

On the downside, this study does not account for a lot of other independent factors for determining Domestic Violence such as education level and occupation of the woman and partner, religion and caste. Future studies would take that into account and control for such aspects. 

## References 
- Rashada, Ahmed Shoukry; Sharaf, Mesbah Fathy (2016) : *Income inequality and intimate partner violence against women: Evidence from India, Frankfurt School - Working Paper Series, No. 222, Frankfurt School of Finance & Management, Frankfurt a. M.**
- Kramer, A., Lorenzon, D., & Mueller, G. (2004). *Prevalence of intimate partner violence and health implications for women using emergency departments and primary care clinics. Women's Health Issues, 14(1), 19-29.*
- Sutherland, C., Bybee, D., & Sullivan, C. (1997). *The long-term effects of battering on women's health. Women's health (Hillsdale, NJ), 4(1), 41-70.*
- Eldin Fahmy, Emma Williamson and Christina Pantazis, University of Bristol School for Policy Studies. *Evidence and policy review: Domestic violence and poverty A Research Report for the Joseph Rowntree Foundation*
- Bell H (2003) *Cycles within Cycles: Domestic violence, welfare and low-wage work. Violence against Women, 9(10): 1245-1262*
- Tanya Abramsky, Shelley Lees, Heidi Stöckl, Sheila Harvey, Imma Kapinga, Meghna Ranganathan, Gerry Mshana and Saidi Kapiga. *Women’s income and risk of intimate partner violence: secondary findings from the MAISHA cluster randomised trial in North-Western Tanzania*
- Anna Aizer. *Women’s income and risk of intimate partner violence: secondary findings from the MAISHA cluster randomised trial in North-Western Tanzania*