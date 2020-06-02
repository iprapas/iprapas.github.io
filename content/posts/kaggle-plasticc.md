+++
date = "2019-01-10"
draft = false
title = "How I reached top 2% in my first kaggle competition"
toc = true
tags = ["kaggle", "astronomy", "competition", "python"]
categories = ["Data Science", "Kaggle Competitions", "Story"]
+++

Just before the competition, my experience with data science was:

* From online courses, with most notable one the Coursera course on [Machine Learning with Andrew NG](https://www.coursera.org/learn/machine-learning). Some others included [Scalable Machine Learning with Spark](https://courses.edx.org/courses/BerkeleyX/CS190.1x/1T2015/course/), and [Computational Thinking and Data Science with Python](https://courses.edx.org/courses/course-v1:MITx+6.00.2x_3+1T2015).
* From my [thesis](https://dl.acm.org/doi/pdf/10.1145/3200947.3201051), which had a limited focus on deep learning.

I lacked, however, any practical experience and although I wanted to join kaggle competitions in the past, I did not really know how to start.

## Competition

I found the opportunity to join a competition with the [Plasticc chalenge](https://www.kaggle.com/c/PLAsTiCC-2018) that involved classifying stars based on their light-curves (light curves are the time-series of the observed luminosities of a star).

Here we see two examples of the classes of stars we needed to classify:

![class90](/blog/kaggle-plasticc/class90.png)

Class 90 is some kind of a supernova that has a burst luminosity for some time and then almost none.

![class80](/blog/kaggle-plasticc/class88.png)

Class 88 presents a more periodic luminosity.

The subject seemed very interesting to me and I saw it as an opportunity hit two barrels with one shot: a) learn data science, b) learn about astronomy.

## Method

I started with a [public kernel](https://www.kaggle.com/ogrellier/plasticc-in-a-kernel-meta-and-data) and built my solution on top of it using private kernels in kaggle. Since my pc configuration was not very strong, I found it amazing that I can use free computing resources in kaggle (4 virtual CPUs and 16gb RAM).

I focused mainly on feature engineering and used [LighGBM](https://lightgbm.readthedocs.io/en/latest/) for the classification.

The feature engineering has been guided by:
* looking at the data for interesting patterns,
* searching through the web for useful features for time-series,
* searching through the web for useful features for light-curves,
* kernels and discussions in the Kaggle platform,
* the cross-validation score 

**NOTE:** I cannot stress enough how important it is to set up a reliable validation strategy.

## Results

![leaderboard](/blog/kaggle-plasticc/leaderboard.png)

### Team merge
At a certain point near the end I was out of time and ideas, so I decided to accept the offer of
a fellow Kaggler (Max Halford) with similar score to form a team. We also added Adityasinha who had a similar score. The good thing is that since we had different approaches, just by averaging the predictions of our best models we got a score, which brought as
from the 50th to the 16th position in the leaderboard. 

This was just one week before the competition ending and we finished at the 22nd position with the same score as none of us
had time to implement more ideas. We didn’t experience any significant shake-up moving
from position 21 st on the public leaderboard to position 22nd in the private one. This
performance earned us a Kaggle silver medal.

### Learning & Contribution

In general, this competition has been a huge learning experience for me. More specifically:
* I learned to use the powerful LGBM, a true hammer for data science.
* I learned different techniques to deal with imbalanced data.
* It was my first time dealing with astronomical or time-series data. Researching about
the extraordinary stuff that comprise the universe has been truly interesting.
* It was my first Kaggle competition ever and I competed head-to-head with some of
the best data scientists.

In the end though, I did not only learn, but I also contributed to the Kaggle community, by
actively participating in the forum discussions and publishing my code. These contributions
earned me:

1. A silver medal for my ranking in the competition
2. A gold medal for a [kernel](https://www.kaggle.com/iprapas/ideas-from-kernels-and-discussion-lb-1-135) I published which at the time of writing this
report has received 100 upvotes and at has been forked almost 400 times.
3. 3 silver and 24 bronze medals for my contributions in the discussions.

It is funny how this medals mean nothing to anyone, but I was happy to get them :)

## Suggestions

If you want to enter a kaggle competition, I suggest the following:

* Do a machine learning tutorial.
* Start from a public kernel. (Some grandmasters in kaggle suggest to not do this at the beginning, but I think this is an advanced suggestion)
* Set up a reliable validation scheme to validate your methods fast. (Important)
* Do not team up early.
* Read the discussions for any valuable hint and participate in them.
* I hate to say this and end with a marketing message, but *just do it*. It is as simple as that.

## Technical details

If you want to read technical details about my methods for this competition, you could read my [report](/blog/kaggle-plasticc/report.pdf) and [slides](/blog/kaggle-plasticc/slides.pdf).
