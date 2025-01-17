# CS70 Grade "Calculator"
This program predicts the grade you need to score on the final when inputted your midterm score. 

Percentiles may vary slightly from semester to semester, so you want to score a little bit above the lower bound to be safe. Ideally, try to hit the median between the lower and upper bound.

*Disclaimer: I'm not responsible if you fail to declare or if you cry about not getting the grade that the calculator said you would get. I made this for myself out of pure anxiety to give myself some semblance of certainty.*

## Requirements
1. Python 3
2. Scipy module
3. Numpy module

Note: you may have to use pip instead of pip3

### Installation for Linux/MacOS users:
```
# Note: may have to use pip instead of pip3
pip3 install python3
pip3 install scipy
pip3 install numpy
```

## Running the Program:

`cd` into the same folder as the .py file then run the following: 
```
python3 predict_70_final.py
```

**Rudimentary predictor factoring in Corr(MT, Final)**
```
python3 predict_70_corr.py
```

## How it works:
The predictor factors in the two-way 50%-clobbering policy and assumes everyone has 100% in all other categories besides exams, which according to course staff, buckets HW-Option students without homework i.e very similar to No-HW Option students. 
* For HW-Option students: the reason we can make this assumption is because this "extreme case" where everyone gets full points on HW "is actually the norm for almost all students getting above a B-.  With the new 73% is enough policy for homework, this is even more true; 90% of the students whose final score was above the B range received essentially full points on the homework" (according to TA). It's also quite difficult to account for actual deviations but the difference is nearly negligible. 

You have two options:
* Option A: You want to get an "[desired grade]" and want to find out the final std range that you need score within to get [desired grade].
    * Output: (lower bound std, upper bound std) for [desired grade]

* Option B: You want to get a very specific [desired overall std]. This option tells you exactly what std you need on the final to get that. 
    * Output: exact std for the final to get [desired std]

* Option C: All possible grade ranges. If I scored [__] on the midterm, what do I need for an A, A-, B+, ...
    * Output: [grade]: (lower bound std, upper bound std)

## Optional CLI Functionality:
You can additionally run
```
python3 predict.py score [-g desired grade] [-s desired std]
```

With either the `-g` or `-s` argument to see your desired grade or desired standard deviation.
