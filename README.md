# lottery-randomness-analysis
**ENGR 315: Computational Methods in Engineering | Fall 2026**  
**Team:** 404 Luck Not Found Team (Dylan Hartman, Evan Foresman, Diego Arias)


## 1. Objective and Motivation

Many people use "strategies" to play the lottery like picking "hot" numbers that appear frequently or numbers that feel "due" because they haven't been drawn lately. In this project, we use Python to analyze historical drawing data from the **Powerball** and **Mega Millions** games in New York State. Our goal is to determine whether these strategies actually work or if the drawings are truly random and winners just rely on pure luck.

### Dataset Overview
* **Sources:** New York State Gaming Commission via Data.gov ([Powerball dataset](https://catalog.data.gov/dataset/lottery-powerball-winning-numbers-beginning-2010), [Mega Millions dataset](https://catalog.data.gov/dataset/lottery-mega-millions-winning-numbers-beginning-2002)).
* **Filtered Date Ranges & Sample Sizes:** 
  * **Powerball (1–69):** Drawings since October 7, 2015.
  * **Mega Millions (1–70):** Drawings since October 31, 2017.
* **Key Columns Used:** `Draw Date` and `Winning Numbers` (specifically the first five white balls).


## 2. Selected Questions & Expected Answers

We are investigating three primary questions:

### Question 1: Are there real "hot" or "cold" numbers?
* **Description:** We count how many times each white ball has been drawn and compare it to expected uniform probabilities using a chi-square test.
* **Expected Answer:** The chi-square test will show that variations are due to random chance, confirming no numbers are truly "hot" or "cold."

### Question 2: Is there a significant difference in the average sum of winning numbers between Powerball and Mega Millions?
* **Description:** We sum the five white balls for every drawing and compare the distributions using a two-sample t-test.
* **Expected Answer:** Both games will show a bell-curve distribution centered around their expected means.

### Question 4: Do appearance gaps follow a geometric distribution, proving numbers are never "due"?
* **Description:** We calculate the number of drawings between consecutive appearances for every ball and fit those gaps to a geometric distribution.
* **Expected Answer:** The gaps will closely follow the geometric curve, showing that past drawings have no bearing on future outcomes and no number is ever "due."


## 3. Implementation Details & Methods

### Python Tools & Packages
* **"pandas" & "numpy"**: Data loading, filtering, vector math, binning, and gap calculations.
* **`scipy.stats`**: Statistical testing ("chisquare", "t-test_ind") and distribution fitting ("geom").   
* **`matplotlib`**: Generating clearly labeled plots, histograms, and frequency graphs.

### Question-by-Method Plan

| Question | Analysis Method | Key Metrics | Planned Visualizations |
| :--- | :--- | :--- | :--- |
| **Q1: Frequency** | Chi-Square Goodness-of-Fit Test | Observed vs. expected counts | Bar chart of ball frequencies with a horizontal expected line |
| **Q2: Sums** | Two-Sample t-test | Mean sum, standard deviation, t-statistic, p-value | Overlaid histograms of the sum distributions |
| **Q4: Gaps** | Geometric Distribution Fit | Consecutive gap lengths, mean gap, goodness-of-fit p-value | Histogram of gaps with fitted geometric PMF curve |


## 4. Results

*TBD in Phase-2 and Phase-3.*


## 5. Conclusions
	
*TBD in Phase-3.*


## 6. Action Items

- [X] Phase-0: Form team, select dataset, and submit proposal
- [X] Phase-1: Define methods, metrics, tools, and create GitHub repository
- [ ] Download data files and build `data_prep.py` script
- [ ] Implement and run Q1 analysis (frequency & chi-square test)
- [ ] Implement and run Q2 analysis (sum distributions & t-test)
- [ ] Implement and run Q4 analysis (gap tracking & geometric fit)
- [ ] Draft final results, conclusions, and individual reflections (Phase-3)
- [ ] Record video demo and compile final presentation PDF (Phase-3)


## 7. References

** [1] New York State Gaming Commission, “Lottery Mega Millions winning numbers: Beginning 2002,” Data.gov. [Dataset]. Available: https://catalog.data.gov/dataset/lottery-mega-millions-winning-numbers-beginning-2002. Accessed: Oct. 21, 2026.

** [2] New York State Gaming Commission, “Lottery Powerball winning numbers: Beginning 2010,” Data.gov. [Dataset]. Available: https://catalog.data.gov/dataset/lottery-powerball-winning-numbers-beginning-2010. Accessed: Oct. 21, 2026.
