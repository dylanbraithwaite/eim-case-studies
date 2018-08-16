---
Title: COMPAS
Template: LeafPage
---

### COMPAS

COMPAS is a risk assessment tool originally created by Tim Brennan in 1988.$^1$ It takes data from both a questionnaire presented to an arrested individual and an interview performed with them$^2$ to output recidivism risk in deciles.$^1$
Originally intended to be used as a tool to help determine probation periods$^3$, COMPAS is now employed in several states to augment a judge's decision determining sentence lengths, notably in Wisconsin.$^4$

### ACCURACY

The Pr. Gu.$^1$ indicates that COMPAS gathers 5 main aggregate data points from its input and performs a weighted average of these scores, so that your risk $R$ is given by

$$R=\sum_{n=1}^N w_n x_n$$

The weights $w_i$ are created manually to try and optimise the accuracy of the program, although it is unclear if any statistical analysis or even machine learning is used here. A 2018 paper$^5$ found that even with only two variables, the authors' own algorithm can approximate the accuracy of COMPAS.

Furthermore, 400 humans from Amazon's Mechanical Turk were asked to perform the same task as COMPAS (guessing if a convict will (violently) commit an offence) using the same information that COMPAS had available, and managed to also have approximately the same accuracy as COMPAS.$^5$

### PROPUBLCIA ANALYSIS

ProPublica's analysis of COMPAS$^6$ makes use of datasets obtained from the Broward County sherrif's office in Florida detailing risk scores assigned to defendants prior to trail as well as sentencing statistics for the countf. It consists of two main tests.

The first test involved fitting a logistical regression model to the data and looking at how individual features are weighted in the model to study their correlation with high COMPAS scores, adjusting for controlling for variation among classes in the population. From this ProPublica were able to conclude that women are 19% more likely than men to be predicted high recidivism scores, black defendants are 45% more likely, and defendants younger than 25 are 250% more likely.

The same test was done looking at scores for violent recidivism. Black defendants were 77.3% more likely to receive a high score and young defendants were found 640% more likely.

The second statistical technique was a Cox proportional hazard model, the same test used by Northpointe in their analysis of COMPAS's effectiveness. On the whole ProPublica found less significant scores from the test, although Northpointe disputed the correctness of ProPublica's methods.$^7$

### WISCONSIN V LOOMIS

In 2013, Mr. Loomis was arrested and accused of driving a car that had been used in a shooting. The judge gave him a six-year prison term, stating that he arrived at his decision in part because of Loomis' score generated by COMPAS, which indicated that he was a "high risk" to the community. Loomis challenged his sentence, arguing that$^8$:

* The proprietary nature of the COMPAS software prevented him from assessing the accuracy of the score
* It violated his right to an individualised sentence as it relied on information about the characteristics of a larger group to make an inference about his personal likelihood to commit future crimes
* It used gender as a variable improperly in calculating the score

Ultimately, the court rejected Loomis's claims$^9$ and held that COMPAS could be used for sentencing, but prescribed key limitations for its use: The score can help a judge understand a defendant's situation but should not be used to determine a length or severity of punishment, and should definitely not be used as "an official aggravating factor"$^8$ in the sentencing decision. Judge Shirley Abrahamson noted that the lack of understanding about COMPAS and how it works was a "significant problem" in the case.

### BIBLIOGRAPHY

$^1$ “Practitioners Guide To COMPAS.” FieldGuide2_081412.pdf, August 17, 2012. http://www.northpointeinc.com/files/technical_documents/FieldGuide2_081412.pdf.

$^2$ Angwin (ProPublica), Julia. “Sample COMPAS Risk-Assessment Questions.” Accessed August 6, 2018. https://www.propublica.org/documents/item/2702103-Sample-Risk-Assessment-COMPAS-CORE.

$^3$ Brennan, Tim, William Dieterich, and Beate Ehret. “Evaluating the Predictive Validity of the Compas Risk and Needs Assessment System.” Criminal Justice and Behavior 36, no. 1 (January 2009): 21–40. https://doi.org/10.1177/0093854808326545.

$^4$ J, ANN WALSH BRADLEY. “STATE v. LOOMIS | 881 N.W.2d 749 (2016) | By ANN... | 20160713i48| Leagle.Com.” Leagle. Accessed August 6, 2018. https://www.leagle.com/decision/inwico20160713i48.

$^5$ Dressel, Julia & Farid, Hany. (2018). The accuracy, fairness, and limits of predicting recidivism. Science Advances. 4. eaao5580. 10.1126/sciadv.aao5580. 

$^6$ Julia Angwin, Jeff Larson. “Machine Bias.” Text/html. ProPublica, May 23, 2016. https://www.propublica.org/article/machine-bias-risk-assessments-in-criminal-sentencing.

$^7$ Dieterich, William, Christina Mendoza, and Tim Brennan. “COMPAS Risk Scales: Demonstrating Accuracy Equity and Predictive Parity,” July 8, 2016, 1–37.

$^8$ Kehl, Danielle, Priscilla Guo, and Samuel Kessler. “Algorithms in the Criminal Justice System: Assessing the Use of Risk Assessments in Sentencing,” n.d., 37.

$^9$ Center, Electronic Privacy Information. “EPIC - Algorithms in the Criminal Justice System.” Accessed August 7, 2018. https://epic.org/algorithmic-transparency/crim-justice/.