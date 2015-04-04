---
title: Getting Started with R
layout: post
tags : [coding]
category: coding
date: 2012-06-28 16:53:23
---

### 1. Downloading and Installing R

+ R Studio
+ R Language  

<!--more-->

### 2. Getting Help on a Function

<pre>
<code class="r">
help(func)
?(func)
args(func)
example(func)
</code>
</pre>

### 3. Viewing the Supplied Documentation

<pre><code class="r">
help.start()

</code></pre>

### 4. Searching the Web for Help

+ RSiteSearch("key phrase")
+ <http://rseek.org>
+ <http://stackoverflow.com>
+ <http://stats.stackexchange.com>

### 5. Reading Tabular Datafiles

<pre>
<code class="r">
dfrm <- read.table("filename.txt", sep=":")    
print dftm    
</code>
</pre>

### 6. Reading from CSV Files

<pre>
<code class="r">
table <- read.csv("filename", header=FALSE)
</code>
</pre>

### 7. Creating a Vector

<pre><code class="r">
v1 <- c(1,2,3)
v2 <- c("A","B","C")
mode(c(3.1415, "foo"))

</code></pre>

### 8. Computing Basic Statistics

<pre><code class="r">
mean(x)
median(x)
sd(x)
var(x)
cor(x,y)
cov(x,y)

</code></pre>

### 9. Initializing a Data Frame form Column Data

<pre><code class="r">
dfrm <- data.frame(v1, v2, v3, f1, f2)
dfrm <- as.data.frame(list.of.vectors)
dfrm <- data.frame(pred1, pred2, pred3, resp)
dfrm <- data.frame(p1=pred1, p2=pred2, p3=pred3, r=resp)

</code></pre>

### 10. Selecting Data Frame Columns by Position

<pre><code class="r">
dfrm[[n]]
dfrm[n]
dfrm[c(n_1, n_2, ..., n_k)]
dfrm[, n]
dfrm[, c(n_1, n_2, ..., n_k)]
dfrm[, vec, drop=FALSE]

</code></pre>

### 11. Selecting Data Frame Columns by Name

<pre><code class="r">
dfrm[[anme]]
dfrm$name
dfrm["name"]
dfrm[c("name_1", "name_2", ..., "name_k")]
dfrm[, "name"]
dfrm[, c("name_1", "name_2", ..., "name_k")]

</code></pre>

### 12. Forming a Confidence Interval for a Mean

<pre><code class="r">
x <- rnorm(50, mean=100, sd=50)
t.test(x)
t.test(x, conf.level=0.99)

</code></pre>


### 13. Forming a Confidence Interval for a Proportion

<pre><code class="r">
prop.test(n, x)
prop.test(6, 9)
prop.test(n, x,,p, conf.level=0.99) # 99% confidence level

</code></pre>


### 14. Comparing the Means of Two Samples

<pre><code class="r">
t.test(x, y)
t.test(x, y, paired=TRUE)

</code></pre>

### 15. Testing a Correlation for Significance

<pre><code class="r">
cor.test(x, y)
cor.test(x, y, method="Spearman")

</code></pre>

### 16. Creating a Scatter Plot

<pre><code class="r">
plot(x, y)
plot(dfrm)

</code></pre>

### 17. Creating a Bar Chart 

<pre><code class="r">
barplot(c(height1, height2, height3))

barplot(heights,
        main="Mean Temp. by Month"
        names.arg=c("May", "Jun", "July", "Aug", "Sep"),
        ylab="Temp (deg. F)")

</code></pre>


### 18. Creating a Box Plot

<pre><code class="r">
boxplot(x)

</code></pre>

### 19. Creating a Histogram

<pre><code class="r">
data(Cars93, package="MASS")
hist(Cars93$MPG.city)
hist(Cars93$MPG.city, 20)
hist(Cars93$MPG.city, 20, main="City MPG (1993)", xlab="MPG")

</code></pre>

### 20. Performing Simple Linear Regression

<pre><code class="r">
lm(y ~ x)
lm(y ~ x, data=dfrm) # Take x and y from dfrm

</code></pre>


### 21. Performing Multiple Linear Regression

<pre><code class="r">
y=c(6.584519, 6.425215, 7.830578, 2.757777, 5.794566, 7.314611, 2.533638, 8.696910, 6.304464, 8.095094)
u=c(0.79939065, -2.31338537, 1.71736899, 1.27652888, 0.39643488, 1.82247760, -1.34186107, 0.75946803, 0.92000133, 1.02341093)
v=c(2.7971413, 2.7836201, 2.7570401, 0.4191765, 2.3785468, 1.8291302, 2.3472593, 3.4028180, 2.0654513, 2.6729252)
w=c(4.366557, 4.515084, 3.865557, 2.547935, 3.265971, 4.518522, 2.570884, 4.442560, 2.835248, 3.868573)
lm(y ~ u + v + w)
lm(y ~ u + v + w, data=dfrm)

</code></pre>


### 22. Getting Regression Statistics

<pre><code class="r">
y=c(6.584519, 6.425215, 7.830578, 2.757777, 5.794566, 7.314611, 2.533638, 8.696910, 6.304464, 8.095094)
u=c(0.79939065, -2.31338537, 1.71736899, 1.27652888, 0.39643488, 1.82247760, -1.34186107, 0.75946803, 0.92000133, 1.02341093)
v=c(2.7971413, 2.7836201, 2.7570401, 0.4191765, 2.3785468, 1.8291302, 2.3472593, 3.4028180, 2.0654513, 2.6729252)
w=c(4.366557, 4.515084, 3.865557, 2.547935, 3.265971, 4.518522, 2.570884, 4.442560, 2.835248, 3.868573)
m <- lm(y ~ u + v + w)
summary(m)
anova(m)
coefficients(m)
coef(m)
confint(m)
deviance(m)
effects(m)
fitted(m)
residuals(m)
resid(m)
vcov(m)

</code></pre>

### 23. Diagnosing a Linear Regression

<pre><code class="r">
m <- lm(y ~ x)
plot(m)

library(car)
outlier.test(m)

</code></pre>

### 24. Predicting New Values

<pre><code class="r">
m <- lm(y ~ u + v + w)
preds <- data.frame(u=3.1, v=4.0, w=5.5)
predict(m, newdata=preds)
preds <- data.frame(
        u=c(3.0, 3.1, 3.2, 3.3),
        v=c(3.9, 4.0, 4.1, 4.2),
        w=c(5.3, 5.5, 5,7, 5.9) )
predict(m, newdata=preds)

</code></pre>

### 25. Accessing the Functions in a Package

<pre><code class="r">
library(packagename)
library(MASS)
lda(f ~ x + y)
detach(package:MASS)

</code></pre>

### Chinese Translation

+ Chen Gang has translated [some sections](http://gossipcoder.com/?tag=r%E5%85%A5%E9%97%A825%E6%8B%9B) of this book.
+ Yu Guangchuang has recreated [the figures](http://ygc.name/2011/08/17/ggplot2-version-figures-25-recipes-started-r/) of this book
