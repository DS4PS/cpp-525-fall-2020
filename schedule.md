---
layout: default
title: Schedule

canvas: 
  assignment_url: 'https://canvas.asu.edu/courses/57030/assignments'
  
---

<!--- 
Submit Button - <a class="uk-button uk-button-primary" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>
-->


<div class = "uk-container uk-container-small">
  
<br><br>
<br><br>


## Week 1 - Interrupted Time Series 

* [LECTURE](https://ds4ps.org/pe4ps-textbook/docs/p-020-time-series.html)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/time-series-lab.html)

**DUE: THURS July 9th**

<a class="uk-button uk-button-default" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br> 

**Resources:**

Bernal, J. L., Cummins, S., & Gasparrini, A. (2017). Interrupted time series regression for the evaluation of public health interventions: a tutorial. International journal of epidemiology, 46(1), 348-355. [[PDF](http://www.ag-myresearch.com/uploads/1/3/8/6/13864925/2016_lopezbernal_ije.pdf)]

Chapter on Interrrupted Time Series [[PDF](https://github.com/DS4PS/cpp-525-spr-2020/raw/master/pubs/cook-campbell-shadish-interrupted-time-series.pdf)]:  From Shadish, W. R., Cook, T. D., & Campbell, D. T. (2002). *Experimental and quasi-experimental designs for generalized causal inference.* Boston: Houghton Mifflin.


<br>
<br>
![](https://ds4ps.org/pe4ps-textbook/docs/FIGURE/TimeSeries/Picture3.4.png){:width="50%"}

```r
Y = b0 + (b1)(T) + (b2)(D) + (b3)(P) + e

# Interrupted Time Series Model 
# b1 = pre-intervention trend 
# b2 = discrete change after intervention 
# b3 = sustained change to the slope after intervention

# Where:
# T = time count variable 
# D = treatment dummy, 0 before , 1 after 
# P = time since intervention count
```

<br>

![](https://ds4ps.org/pe4ps-textbook/docs/FIGURE/TimeSeries/Picture5.png){:width="50%"}


<br>

----

<br>




## Week 2 - Difference-in-Difference Models 

* [LECTURE](https://ds4ps.org/pe4ps-textbook/docs/p-030-diff-in-diff.html)
* [overview video](https://asu.zoom.us/rec/play/tMIrd7yvqDo3TNfD4gSDV_V5W425e_6s2yBNrqBcxUixASFRY1GmN7VDNuqKJy2LLzjKb6H4yI5HWMZw?continueMode=true&_x_zm_rtaid=a3eEFLG8Qtiy1qBhz5Gnyg.1586645508130.02d1fbabc21b564365fde85fb34937b4&_x_zm_rhtaid=598)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/diff-in-diff-lab.html)

**Due THURS July 16th**

<a class="uk-button uk-button-default" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>

**Review:** 

Hypothesis testing with dummy variables: [lecture notes](https://github.com/DS4PS/cpp-523-spr-2020/raw/master/lectures/hypotheses-tests-with-dummy-variables.pdf)   

Varieties of the counterfactual: [lecture notes](https://github.com/DS4PS/cpp-524-spr-2020/raw/master/lectures/p-03-varieties-of-counterfactuals.pdf)   

**Reference:**

Gertler, P. J., Martinez, S., Premand, P., Rawlings, L. B., & Vermeersch, C. M. (2016). Impact evaluation in practice. The World Bank. CH-07 Difference-in-Differences [[link](https://openknowledge.worldbank.org/handle/10986/25030)]

Wing, C., Simon, K., & Bello-Gomez, R. A. (2018). Designing difference in difference studies: best practices for public health policy research. Annual review of public health, 39. [[pdf](https://www.annualreviews.org/doi/pdf/10.1146/annurev-publhealth-040617-013507)] 

<br>

----

<br>





## Week 3 - Panel Data with Fixed Effects 

* [LECTURE NOTES](https://github.com/DS4PS/cpp-525-spr-2020/raw/master/lectures/p-23-fixed-effects.pdf)
* [LECTURE CHAPTER](https://ds4ps.org/pe4ps-textbook/docs/p-040-fixed-effects.html)
* [overview video](https://asu.zoom.us/rec/play/vZQrcbj9qTo3T9aSuQSDC6dxW9S7Kais0SVP-qUKykm9B3QGMFahYeMVZLENnE0QqLfC7HHfx_JInrRR?continueMode=true&_x_zm_rtaid=a3eEFLG8Qtiy1qBhz5Gnyg.1586645508130.02d1fbabc21b564365fde85fb34937b4&_x_zm_rhtaid=598)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/fixed-effects-lab.html)

**Due THURS July 23** 

<a class="uk-button uk-button-default" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

**Reference:**

[useful notes on interpretting output](https://www.princeton.edu/~otorres/Panel101.pdf)


<br>

----
Panel models are necessary when group structure (farms A, B and C in this example) is correlated both with the level of treatment (amount of fertilizer used each season) and the outcome (some farms are more efficient). 

If it is the land causing the productivity difference and land quality varies by farm, omitting the group ID (farm fixed effect) in the model would not bias the result. But it would make the model a lot less efficient (larger standard errors).

If the management practices of the farm are driving outcomes then better managers use fertilizer more intensely, but they also do a dozen other things not captured by the model that will improve productivity. In this case the farm ID is a proxy for management, and omitting it would result in bias. 

So although group ID is measured differently than variables you have used before (it is a factor or a set of dummy variables) it operates similarly to other controls. If it is uncorrelated with the treatment then adding it will not change the policy slope, but it will make the model more efficient (explain more of the residual). If the group ID is correlated with the treatment then adding it to the model will fix bias. 

![](https://ds4ps.org/pe4ps-textbook/docs/p-041-panel-model-specification_files/figure-html/unnamed-chunk-4-1.png)
![](https://ds4ps.org/pe4ps-textbook/docs/p-041-panel-model-specification_files/figure-html/unnamed-chunk-5-1.png)


----

[random effects example](https://raw.githubusercontent.com/DS4PS/cpp-525-spr-2020/master/lectures/random-effects.R)

This example explores the relationship between mileage and used-car price. Car models (e.g. lexus, ford, and honda) are correlated with price (a lexus is more expensive on average), but they are uncorrelatd with mileage (lexus owners and honda owners are driving similar amounts each year). Car values are very different when new, but each 10,000 miles driven reduces the value by the same amount.

```r
# pooled model - all cars share same intercept
price = b0 + b1 × mileage + e

# random effects model 
price[j] = a[j] + b1 × mileage + e
```

![](https://raw.githubusercontent.com/DS4PS/cpp-525-spr-2020/master/assets/img/random-effects.png)

Where the data would be structured as follows:

```r
# intercept in pooled model:
# all cars share one intercept 

      lexus |  y  1  x  | 
b0 =   ford |  y  1  x  |
      honda |  y  1  x  |

# intercept in grouped model:
# each j (car company) has its own

        lexus |  y  1  0  0  x  | 
a[j] =   ford |  y  0  1  0  x  |
        honda |  y  0  0  1  x  |
```

Group-level variable is correlated with the outcome, but uncorrelated with the policy variable. Thus omission does not cause bias, but inclusion increases efficiency allowing the model to use a separate intercept for each group and thus moving regression lines closer to the data, reducing the model error. 

*Note that this is an over-simplified presentation of the topic. The terms fixed and random effects are used differently depending on discipline (see [Gelman's insightful discussion](https://statmodeling.stat.columbia.edu/2005/01/25/why_i_dont_use/)) and the model are estimated using different technique (see [Stoudt blog, 2017](https://rlbarter.github.io/Practical-Statistics/2017/03/03/fixed-mixed-and-random-effects/)).*

---

Recall the [taxonomy of control variables](https://github.com/DS4PS/cpp-523-spr-2020/raw/master/lectures/taxonomy-of-control-variables.pdf).

Random effects are like Type A controls. Fixed effects are like Type B controls:

![](https://raw.githubusercontent.com/DS4PS/cpp-525-spr-2020/master/assets/img/taxonomy-of-controls2.png)

<br>
<hr>
<br>

![](https://raw.githubusercontent.com/DS4PS/cpp-525-spr-2020/master/assets/img/taxonomy-of-controls.png)

<br>
<br>

<hr>

<br>
<br>









## Week 4 - Instrumental Variables 

* [LECTURE NOTES](https://github.com/DS4PS/cpp-525-spr-2020/raw/master/lectures/p-24-instrumental-variables.pdf)
* [LECTURE CHAPTER](https://ds4ps.org/pe4ps-textbook/docs/p-050-instrumental-variables.html)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/instrumental-variables.html)
<br>

* [iv regression example](https://ds4ps.org/cpp-525-spr-2020/lectures/p-25-iv-example.html)
* [overview of iv regression (video)](https://asu.zoom.us/rec/play/u5x-I7r9-Dw3GYLH4gSDB_5xW9TpK6qs0HQY-qIJmEazVHQBNwCvNLETM-KIqBwzOPr2gZymGDn8qDSn?continueMode=true&_x_zm_rtaid=a3eEFLG8Qtiy1qBhz5Gnyg.1586645508130.02d1fbabc21b564365fde85fb34937b4&_x_zm_rhtaid=598)


**Due THURS July 30th** 

<a class="uk-button uk-button-default" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>
<br>

<hr>

<br>
<br>









## Week 5 - Regression Discontinuity Design 

* [LECTURE](https://ds4ps.org/pe4ps-textbook/docs/p-060-reg-discontinuity.html)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/regression-discontinuity-lab.html)

**Due THURS Aug 6th**

<a class="uk-button uk-button-default" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>

<br>

----

<br>

![](assets/img/reg-discontinuity.png)
<br>
<br>

----

<br>




## Week 6 

### Logistic Regression 

* [LECTURE](https://ds4ps.org/pe4ps-textbook/docs/p-070-logistic-regression.html)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/logit-lab.html)

* [example script](examples/logistic-regression-example.R)  
* [video](https://asu.zoom.us/rec/share/xfMlBJHy_E5IZ7fGsnvxB5UzGKTreaa8hiAWqfIPnhtzDDh-1wytiZ5OYSgLp0WQ)  


### Propensity Score Matching 

* [LECTURE](https://ds4ps.org/pe4ps-textbook/docs/p-080-matching.html)
* [LAB](https://ds4ps.org/pe4ps-textbook/labs/matching-lab.html)

[video overview](https://asu.zoom.us/rec/share/4MpkE7Xr2VhOZdbI4mOFR7caHY_6eaa8gSdKq_cFn0ecqyECXG2G3ve0yarS9z00?startTime=1588373097000)


**Both labs due TUES Aug 11th**

<a class="uk-button uk-button-default" href="{{page.canvas.assignment_url}}">SUBMIT LAB</a>













<br>
<br>

-----

<br>
<br>


</div>


<br>
<br>

<style>
em {
    color: black;
}
</style>
