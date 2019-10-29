![alt text](https://raw.githubusercontent.com/RoarData/stanford-faq/master/media/roar-logo.png "ROAR")

# Frequently Asked Questions

**Q: Why do you choose log-likelihood as the metric to maximize?**

A: The log-likelihood is both intuitive and flexible, and an efficient means of statistical inference. Considering that it includes both the mean and variance, it is always used in finance to evaluate how accurate your prediction is from the ground-truth we are interested in. More details can be found here [https://en.wikipedia.org/wiki/Maximum_likelihood_estimation](https://en.wikipedia.org/wiki/Maximum_likelihood_estimation).

**Q: What is the precision?**

A: It is the standard deviation of your prediction error, also referred to as sigma in a statistical context.

**Q: Is the precision important for obtaining a good score?**

A: Yes.

**Q: What is the difference between score and performance of my Bot?**

A: The score is computed when the true value is revealed and compared to your prediction: a low score is better, exactly like golf! Performance is a weighted average of your scores so we look at an aggregate of your scores to reflect your overall Bot quality.
