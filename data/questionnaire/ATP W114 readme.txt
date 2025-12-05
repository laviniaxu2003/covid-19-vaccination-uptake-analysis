PEW RESEARCH CENTER
Wave 114 American Trends Panel 
Dates: Sept. 13 - 18, 2022
Mode: Web 
Sample: Subsample
Language: English and Spanish
N=10,588

***************************************************************************************************************************
NOTES

For a small number of respondents with high risk of identification, certain values have been randomly swapped with those of lower risk cases with similar characteristics.

COVID_VAXDMOD and COVID_BOOST 
COVID_VAXDMOD and COVID_BOOST were asked to all respondents to get a measurement on vaccination and booster status. 
There were 77 respondents that indicated they had either 1) received one vaccine shot and needed another (COVID_VAXDMOD=2) or 2) that they had not received a vaccine (COVID_VAXDMOD=3); but had also received a booster (COVID_BOOST=1). 
Those 77 respondents were coded as COVID_BOOST=98 Invalid response.

NATCHROE/CHRNAT1OE
The W114 dataset contains the following coded open-end responses to NATCHROE and CHRNAT1OE. Up to three mentions were coded for each open-end. 
NATCHROE1_W114
NATCHROE2_W114
NATCHROE3_W114
CHRNAT1OE1_W114
CHRNAT1OE2_W114
CHRNAT1OE3_W114

MHEALTH3
The W114 dataset contains the created variable MHEALTH3, an additive index of 5 mental health measures:MH_TRACK_a, MH_TRACK_b, MH_TRACK_c, MH_TRACK_d, MH_TRACK_e. Please see the syntax below. 
In addition to the index created from W114 data (MHEALTH3_W114), the W114 dataset also includes the MHEALTH3 index from waves 64, W66, and W83. 

CHRNATa-c
The W114 dataset contains three appended variables from Wave 84 (CHRNATa, CHRNATb, CHRNATc) on the role of the U.S government and religion.

The variable containing respondents' sexual orientation has been removed from this dataset due to the sensitive nature of these questions and the high risk of identification. 
If you are interested in replicating the analysis from monkeypox publication or any other analysis using this variable, please contact us. 


***************************************************************************************************************************
WEIGHTS 


WEIGHT_W114 is the weight for the sample. Data for most Pew Research Center reports are analyzed using this weight.

WEIGHT_W84_W114 is a longitudinal weight used for analysis of W84 data. 

WEIGHT_W64_W66_W83_W114 is a longitudinal weight used for analysis of MHEALTH3 to estimate the share of Americans who had experienced high levels of psychological distress at least once across the four surveys that we conducted. 


***************************************************************************************************************************
Releases from this survey:


September 22, 2022 "Gay or bisexual men express concern about monkeypox, are critical of government’s response"
https://www.pewresearch.org/short-reads/2022/09/22/gay-or-bisexual-men-express-concern-about-monkeypox-are-critical-of-governments-response/

October 3, 2022 "Growing share of Americans say their side in politics has been losing more often than winning"
https://www.pewresearch.org/short-reads/2022/10/03/growing-share-of-americans-say-their-side-in-politics-has-been-losing-more-often-than-winning/

October 5, 2022 "Lack of Preparedness Among Top Reactions Americans Have to Public Health Officials’ COVID-19 Response"
https://www.pewresearch.org/science/2022/10/05/lack-of-preparedness-among-top-reactions-americans-have-to-public-health-officials-covid-19-response/

October 25, 2022 "Americans Value U.S. Role as Scientific Leader, but 38% Say Country Is Losing Ground Globally"
https://www.pewresearch.org/science/2022/10/25/americans-value-u-s-role-as-scientific-leader-but-38-say-country-is-losing-ground-globally/

October 27, 2022 "A closer look at Americans who believe the U.S. should be a Christian nation"
https://www.pewresearch.org/short-reads/2022/10/27/a-closer-look-at-americans-who-believe-the-u-s-should-be-a-christian-nation/

October 27, 2022 "In their own words: How Americans describe ‘Christian nationalism’" 
https://www.pewresearch.org/religion/2022/10/27/in-their-own-words-how-americans-describe-christian-nationalism/

October 27, 2022 "45% of Americans Say U.S. Should Be a ‘Christian Nation’" 
https://www.pewresearch.org/religion/2022/10/27/45-of-americans-say-u-s-should-be-a-christian-nation/

November 30, 2022 "Growing share of Americans see the Supreme Court as ‘friendly’ toward religion"
https://www.pewresearch.org/short-reads/2022/11/30/growing-share-of-americans-see-the-supreme-court-as-friendly-toward-religion/

December 12, 2022 "At least four-in-ten U.S. adults have faced high levels of psychological distress during COVID-19 pandemic"
https://www.pewresearch.org/short-reads/2022/12/12/at-least-four-in-ten-u-s-adults-have-faced-high-levels-of-psychological-distress-during-covid-19-pandemic/

March 2, 2023 "Mental health and the pandemic: What U.S. surveys have found"
https://www.pewresearch.org/short-reads/2023/03/02/mental-health-and-the-pandemic-what-u-s-surveys-have-found/

March 15, 2023 "Americans Feel More Positive Than Negative About Jews, Mainline Protestants, Catholics"
https://www.pewresearch.org/religion/2023/03/15/americans-feel-more-positive-than-negative-about-jews-mainline-protestants-catholics/

July 24, 2023 "8 facts about Americans with disabilities"
https://www.pewresearch.org/short-reads/2023/07/24/8-facts-about-americans-with-disabilities/


***************************************************************************************************************************
SYNTAX

The Wave 114 dataset contains three coded variables:MHEALTH_W114, MHEALTH3_W114 and MFLAG_W114. SPSS syntax to compute these variables is included below.

*setting all mental health measures to missing if refused or skipped.
missing values 
MH_TRACK_a_W114
MH_TRACK_b_W114
MH_TRACK_c_W114
MH_TRACK_d_W114
MH_TRACK_e_W114 
MH_TRACK_CV_W114 (99).

*computing additive index of mental health measures, excluding hopeful measure.
compute MHEALTH_W114 =  MH_TRACK_a_W114 +
MH_TRACK_b_W114 +
MH_TRACK_c_W114 +
MH_TRACK_e_W114 + MH_TRACK_CV_W114.
Execute.
var labels MHEALTH_W114 'Simple additive index of 5 mental health measures'.
freq MHEALTH_W114.

*creating three category index.
recode MHEALTH_W114 (5 thru 8=1)(9 thru 11=2)(12 thru 20=3) into MHEALTH3_W114.
value labels MHEALTH3_W114 1 'low - bottom 50%' 2 'medium - next quarter' 3 'high - top quarter'.
var labels MHEALTH3_W114 'Responses to five mental health questions chunked into three groups'.
freq MHEALTH3_W114.



