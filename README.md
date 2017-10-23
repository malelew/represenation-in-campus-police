### Research Question

Do differences in racial demographics of campus police and student bodies significantly affect the police's activities and operations?

### Hypothesis

We predict that if there is a statistically significant difference in the racial demographics between the campus police and student body, then there will be an increase in police operating budget, police size, larceny on campus, and weapons per officer. Additionally, there will be an increase in the ratio of lethal to non-lethal weapons. However, we predict there will be a decrease in the amount of meetings held between the campus police and student body as well as in the number of police officers designated to fight hate crimes. 

### Dataset(s)

- Dataset Name: Survey of Police Departments across the Country
- Link to the dataset: http://www.icpsr.umich.edu/cgi-bin/bob/zipcart2?path=ICPSR&study=36217&bundle=delimited&ds=1&dups=yes
- Number of observations: 861

The dataset has entries describing the police departments of 4-year universities across the US.
It includes department demographics, budget, equipment, student contact, education level, department 
practices, and designated personnel.

- Dataset Name: College Scorecard Raw Data
- Link to dataset: https://catalog.data.gov/dataset/college-scorecard
- Number of observations: 7675

The dataset contains demographic data and accepted applicant statistics for 7675 universities.

- Dataset Name: Campus Security and Safety
- Link to dataset: https://ope.ed.gov/campussafety/#/datafile/list
- Number of observations: 10770

The dataset contains information on crime reported at universities and by university students.

We plan to utilize the two datasets to compare the racial demographics of campus police departments to the
university's student population. We also plan compare differences in crime between universities with more or less represenative police departments.

### Background & Prior Work

American police's treatment of minorities is at the forefront of contemporary civil rights discourse. Police are often under scrutiny for discrimination against minorities. Research shows that minority populations are often underrepresented in police forces and that police do not mirror community demographics. 

American higher education institutions have traditionally had predominantly white male student populations. Recently, universities have made a broad push to be more racially diverse and inclusive. 

As university students, we are primarily interested in analyzing the racial demographic distribution between campus police and student bodies.

References:
- 1) "Where Police Don't Mirror Communities and Why It Matters" by Mike Maciag
    http://www.governing.com/topics/public-justice-safety/gov-police-department-diversity.html
    This article discusses how police across the nation don't mirror the demographics of those they serve, along with the impacts of police diversity (or lack of), and how to potentially improve diversity.
- 2) An Empirical Analysis of Racial Differences in Police Use of Force by Roland G. Fryer, Jr 
    http://www.nber.org/papers/w22399
    This paper examines police use of force and how race plays into this, 
    
### Proposed Methods

*Data Cleaning*
From the first dataset on the campus police, columns such as education level and state can be dropped; colleges with small police forces should also be removed. There are some null data points (some colleges did not report on all topics) and non-relevant college characteristics (such as ZIP code, standardized test scores, financial aid standings, etc.) that need to be removed from the second dataset on college characteristics. Overall, for college student demographics dataset, we must remove the colleges for which we don't have entries in the police dataset since the college dataset size is larger.

*Data Analysis*
For the last dataset, the data is separated across multiple files so the datasets must be merged. In analyizing the datasets, we will first determine if racial demograhpics are similarly distributed across campus police and the student body that they are policing. In order to do so, we will be conducting a Chi-square test of homogeneity on each university's campus police/student body populations. The calculated chi-square statistic is a quantitative measure of how different the two populations are; the lower the chi-square statistic, the more similar the two populations are. 

Now that we have calculated this chi-squared statistic, we can use this as an indicator of how representative the police department demographics are of the university, and thus, can be used as the x-axis for graphic other characteristics about the police department. Since we want to determine if lack of homogeniety between the police and student demographics lead to a positive correlation with more money spent on police, lethal weapons, and arrests, among other factors, we want to develop a linear regression to observe the correlation. 


*What to report*
We plan to report data comparing the demographics of police departments and the students. We want to be able to display this data visually so we will develop a seperate graph with the chi-square statistic as the x-axis and other policing factors as the y-axis with each university as a data point. These visualizations will be able to successfully help us answer the question of if differences in racial demographics of campus police and student bodies significantly affect the police's activities and operations?

Packages we plan to use:
- pandas
- bokeh
- matplotlib
- seaborn
- scipy
- numpy

### Discussion

Our data might have a couple of pitfalls due to police departments and universities self-reporting the data, so there is a lack oversight to ensure the data's authenticity. A university may be underreporting incidents or have poor enforcement that is represented in the data.
Another potential issue is that campus police forces could either be all representative or all unrepresentative of their respective student bodies. If so, we will not be able to draw observations or make conclusions on whether or not representation has an effect on campus policing. 
Additionally, a confounding variable that could affect our results is differences in practices and protocol across departments, university systems, counties, and states. A large centralized system such as UCPD will likely differ in practices from a CSU's police department or a private institution's department, affecting what weapons they require or the budget they request.
