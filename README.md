# crimeanddeprivationuk
Analysis of violent crimes and deprivation in the UK using PySpark


1.1 Background of the task
Violent crimes are among the top concern of government, and policymakers and the pledge to reduce or ‘fight crime’ is among the top agenda of politicians. [1] remarked that the drive for the authorities to publish crime data publicly has increased in the last decade, prompting the UK to publish crime statistics on a public website called police.uk. This report will review existing literature to understand the relationship between violent crimes, firearm incidents and drug offences.

The types of criminal activities considered as violent crimes differ in different countries. In the UK, murder and manslaughter, assault, knife and gun crimes, attacks using corrosive substances, and robberies are considered violent crimes [2]. However, the US adds forcible rape and aggravated assault in addition to crimes considered in the UK (except acid attacks) as violent crimes [3].

In 2018, Birmingham was cited as the ‘gun and gang capital’ of the UK after reportedly witnessing more than twice the national average for firearm incidents [4] quoted in [5]. Homicide, which is a common result of violent crimes, is a leading cause of death worldwide and firearms are the leading means making up about 48% to 74% of homicides [6].

Similarly, substance/drug abuse and alcohol misuse at the individual, family or neighbourhood levels have been associated with increased incidence of adolescent firearm homicide [7]. Furthermore, stricter gun control especially handguns has been found to correlate with fewer suicide deaths ([8] quoted in [9]) while [10] concluded that a 35% increase in gun theft facilitated a 29% increase in firearm violent crime in the US in recent years.

1.2 Aims and objectives of this report
This report aims to analyze the UK crime data focusing on violent crime, firearm incidents and drug offences to determine if violent crime is increasing, and if there is a correlation between firearm incidents and drug offences. This report will also analyze the proportion of firearm incidents per head in the UK to understand if Birmingham’s has the highest. Due to the size of the full dataset, these analyses were tested on a subset of the dataset first before repeating the same steps on the whole dataset.

1.3 Technical Approach
To achieve the aims of this report, the following approach will be followed:
a. Import all relevant libraries to support both big data and cloud computing aspects of the assessment.
b. Import all datasets needed namely, all_crimes dataset, 1% sample of all_crimes dataset, and the postcode dataset. The all_crimes dataset alone is sufficient in analyzing whether violent crimes are increasing and whether firearm incidents are closely associated with drug offences. The sample dataset was first utilized to test the codes before using the full dataset.
c. Extract the column(s) relating to the relevant crime in claim 1 (“Violent crime”). This report is only interested in the ‘Violent crime’ and ‘Violence and sexual offences’ crime types. To view a time series of violent crime occurrences, the monthly count of violent crimes is visualized using sm.tsa.seasonal_decompose() function in pandas. The monthly counts and annual average counts of Violent crimes are also viewed as a line chart.
d. To investigate if there are more firearm incidents per head in Birmingham than anywhere else in the UK, the chosen approach is to analyze this annually instead of monthly. Firstly, the rows/columns relating to firearm incidents are extracted from the all_crimes dataset and this is joined with the postcode dataset. Then the annual count of all firearm incidents is gotten for all cities (saved as Districts) in the UK, and the top 5 districts annually are ranked. The ranking of Birmingham over the years was extracted.
e. To investigate if firearm-related crimes are correlated with drug offences, the rows/columns relating to firearm incidents are extracted from the crime dataset. Afterwards, the monthly counts of both crimes are obtained and are visualized using a scatterplot and the correlation coefficients are obtained.
