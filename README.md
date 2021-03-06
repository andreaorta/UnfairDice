# Project: Unfair dice

I want to consider the problem of deciding whether a dice that rolled a certain number <img src="https://render.githubusercontent.com/render/math?math=(C_1, C_2, \dots, C_6)"> of 1s, 2s, ..., 6s is fair or not.

The notebook makes extensive use of the *numpy* and *matplotlib*/*seaborn* libraries, as well as *scikit-learn* for the machine learning part.

## Summary of the notebook

#### Simulating loaded dice
* Generating the weights <img src="https://render.githubusercontent.com/render/math?math=w_1, w_2, \dots, w_6">, sampling from a uniform distribution 
* Tossing the loaded dice (different functions + performance analysis)

#### Plotting basic histograms displaying the outcome of rolling the dice

#### Statistical analysis of the fairness of a dice
##### Classical <img src="https://render.githubusercontent.com/render/math?math=\chi^2"> analysis
* We introduce the statistic <img src="https://render.githubusercontent.com/render/math?math=\displaystyle \chi^2 = \sum_{i=1}^6 \frac{(C_i - E[C_i])^2}{E[C_i]}">, which is known to follow a <img src="https://render.githubusercontent.com/render/math?math=\chi^2"> distribution (with 5 degrees of freedom in our case).
* We decide on the fairness of a dice based on how likely it is to achieve a value of <img src="https://render.githubusercontent.com/render/math?math=\chi^2"> at least as extreme when tossing a fair dice.
* A commented example is presented.

##### Bootstrap analysis
* Given the counts <img src="https://render.githubusercontent.com/render/math?math=(C_1, C_2, \dots, C_6)"> sampled from a multinomial distribution corresponding to a loaded dice with weights <img src="https://render.githubusercontent.com/render/math?math=w_1, w_2, \dots, w_6">, we resample (with replacement) the <img src="https://render.githubusercontent.com/render/math?math=\sum_i C_i"> observations and for each resampling we compute the value of the <img src="https://render.githubusercontent.com/render/math?math=\chi^2"> statistic (bootstrap replicate).
* We do the same with the counts generated by tossing a perfectly fair dice and compare the two distributions of <img src="https://render.githubusercontent.com/render/math?math=\chi^2"> values by means of boxplots.
* We label the dice under analysis as fair/suspicious/unfair based on the comparison between the distributions of bootstrap replicates for it and the reference fair dice. 
* A commented example is presented.

#### Constructing a DataFrame of observations
We simulate tossing a number of dice with varying degree of (un)fairness. They are categorised as fair/suspicious/unfair based on how much their weights differ from the ideal ones.

#### Implementing a supervised learning model to classify dice as fair/suspicious/unfair.
Starting from a large DataFrame of 10000 dice, we implement a <img src="https://render.githubusercontent.com/render/math?math=k">-NearestNeighbours algorithm in different conditions:
* working with all the features of the DataFrame 
* retaining only some features of the DataFrame
* working with all *rescaled* features of the DataFrame
* working with only some *rescaled* features of the DataFrame


## Tricks and takeaways

* %timeit 

Magic command of Jupyter notebooks to easily time performance.
I used it on various functions written to simulate rolling a dice many times.

* *numpy*'s np.isclose() and np.around() functions

Useful when rounding is involved.

* *pandas*'s pd.plotting.scatter_matrix() and *seaborn*'s sns.pairplot() functions

Not very useful for this project, but interesting for EDA.

* Including <img src="https://render.githubusercontent.com/render/math?math=\LaTeX"> in markdown Readme files on GitHub!

Thanks to Alexander Rodin: [link](https://gist.github.com/a-rodin/fef3f543412d6e1ec5b6cf55bf197d7b)
