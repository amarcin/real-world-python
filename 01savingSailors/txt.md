## Intro

Sometime around 1740, an English Presbyterian minister named Thomas Bayes decided to mathematically prove the existence of God. His ingenious solution, now known as Bayes' rule, would become one of the most successful statistical concepts of all time. But for 200 years it languished, largely ignored, because its tedious mathematics were impractical to do by hand. It took the invention of the modern computer for Bayes' rule to reach its full potential. Now, thanks to our fast processors, it forms a key component of data science and machine learning.

Because Bayes' rule shows us the mathematically correct way to incorporate new data and recalculate probability estimates, it penetrates almost all human endeavors, from cracking codes to picking presidential winners to demonstrating that high cholesterol causes heart attacks. A list of applications of Bayes' rule could easily fill this chapter. But since nothing is more important than saving lives, we'll focus on the use of Bayes' rule to help save sailors lost at sea.

## Bayes' Rule

Bayes' rule helps investigators determine the probability that something is true given new evidence. As the great French mathematician Laplace put it, "The probability of a cause—given an event—is proportional to the probability of the event—given its cause." The basic formula is:

P(A|B) = P(B|A) * P(A) / P(B)

where A is a hypothesis and B is data. P(A|B) means the probability of A given B. P(B|A) means the probability of B given A. 

For example, assume we know that a certain test for a certain cancer is not always accurate and can give false positives, indicating that you have cancer when you don't. The Bayes expression would be:

P(Cancer|Positive Test) = P(Positive Test|Cancer) * P(Cancer) / P(Positive Test)

The initial probabilities would be based on clinical studies. For example:
- 800 out of 1,000 people who have cancer may receive a positive test result
- 100 out of 1,000 may be misdiagnosed
- Based on disease rates, the overall chance of a given person having cancer may only be 50 out of 10,000

So, if the overall probability of having cancer is low and the overall probability of getting a positive test result is relatively high, the probability of having cancer given a positive test goes down. If studies have recorded the frequency of inaccurate test results, Bayes' rule can correct for measurement errors!

## Project #1: Search and Rescue

In this project, you'll write a Python program that uses Bayes' rule to find a solitary fisherman who has gone missing off Cape Python. As the director of the Coast Guard's search and rescue operations for the region, you've already interviewed his wife and determined his last known position, now more than six hours old. He radioed that he was abandoning ship, but no one knows if he is in a life raft or floating in the sea. The waters around the cape are warm, but if he's immersed, he'll experience hypothermia in 12 hours or so. If he's wearing a personal flotation device and lucky, he might last three days.

The ocean currents off Cape Python are complex (Figure 1-3), and the wind is currently blowing from the southwest. Visibility is good, but the waves are choppy, making a human head hard to spot.

Figure 1-3: Ocean currents off Cape Python

![Ocean currents off Cape Python](../sources/Clipboard%20Sep%2015,%202024%20at%2014.25.png)

In real life, your next course of action would be to plug all the information you have into the Coast Guard's Search and Rescue Optimal Planning System (SAROPS). This software considers factors such as winds, tides, currents, whether a body is in the water or in a boat, and so on. It then generates rectangular search areas, calculates the initial probabilities for finding the sailor in each area, and plots the most efficient flight patterns.

For this project, you'll assume that SAROPS has identified three search areas. All you need to do is write the program that applies Bayes' rule. You also have enough resources available to search two of the three areas in a day. You'll have to decide how to allocate those resources. It's a lot of pressure, but you have a powerful assistant to help you out: Bayes' rule.

## The Objective

Create a search and rescue game that uses Bayes' rule to inform player choices on how to conduct a search.