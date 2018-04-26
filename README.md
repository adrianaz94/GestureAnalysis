# GestureAnalysis

****************************
Motion detection project
****************************
ver. 5.0

Authors:

Anna Grzywa
Agnieszka Tracz
Adriana Zlahoda
Andrzej Czechowski
Michal Kluska
Maciej Stanuch
Adam Szmatula


This project is a data analysis of an 8-channels recorded EMG signal of 6 specific hand movements.
The 6 movements of 7 volunteers were registered as follows:

1. finger snap
2. hand shaking
3. double click betweem the thumb and the middle finger
4. right swap
5. left swap
6. fist

For every channel were defined the following  features:

12 time parameters were measured:
	maximum
	minimum
	mean
	std
	median
	median absolute deviation
	signal magnitude area
	energy
	interquartile range
	duration time
	entropy
	autocorrelation

4 frequency parameters:
	leading frequency
	weighted frequency
	skewness
	curtosis

The Pan-Tompkins algorithm was used to detect the beginning and end of the motion in the signal.

After calculating the average feature for each gesture for 5 out of 7 persons, 
a pattern was created and normalised to the [0, 1] range.

A transfer function was defined thanks to which each following motion
is normalised according to the pattern.

The feature vectors for each gesture for each person were compared 
with each base vector (pattern) by a scalar product.

The threshold is set in order to determine the similarity between the movements 
and qualify the correct gesture.

A statystical analysis was processed to check were the algorithm is correct and were it is not
by determining the accuracy, sensitivity and specificity but also a ROC curve.

It appears that the scalar product is the most efficient measure of similarity between vectors.

A PCA analysis of the feature vectors was processed to determine which parameter best determine a gesture.
Applying different weights to those parameters improves the algorithm efficiency
by discriminating the least influent parameters.
