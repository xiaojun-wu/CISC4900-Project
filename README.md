# CISC 4900 Project
### Author Xiaojun Wu

This is a github for CISC 4900 Project. It store the project excel files and program files.

#### V0.1(10/14/2019)
This is the first submission, I submit the program files and excel files. The program files connect the APIs, submit the images and get the labels. The progrom  also save the labels in the corresponding excel file.

#### V0.2.0(10/27/2019)
This is the second submission. I submit the program that calculate the F1-score for each API's performence. The program will read the data from excel files, and general the indicator arrays. using these array to make the confusion matrix and than the F1-score.

#### V0.2.1(10/28/2019)
This is the third submission. I fix a problem in previous program and add the new feature that sort the TN, FN, FP, TN, precision, recall, and f1-score in dictionary. It will be help to see what differet of each API's performence.

#### Output of the measureProgram.py:

F1 measure result of IBM vision API:
TP is:  2.0
FN is:  38.0
FP is:  1.6
TN is:  248.39999999999998
precision is:  0.5555555555555556
reall is:  0.05
f1_score is:  0.09174311926605504


F1 measure result of Clarifai vision API:
TP is:  0.4
FN is:  39.6
FP is:  3.1999999999999997
TN is:  246.79999999999998
precision is:  0.11111111111111113
reall is:  0.01
f1_score is:  0.01834862385321101


F1 measure result of AWS vision API:
TP is:  5.6
FN is:  34.39999999999999
FP is:  36.399999999999956
TN is:  213.60000000000008
precision is:  0.13333333333333347
reall is:  0.14
f1_score is:  0.13658536585365863


F1 measure result of Google cloudVision API without object detection:
TP is:  2.4
FN is:  37.6
FP is:  2.4
TN is:  247.59999999999997
precision is:  0.5
reall is:  0.06
f1_score is:  0.10714285714285712


F1 measure result of Google cloudVision API with only object detection:
TP is:  7.200000000000002
FN is:  32.8
FP is:  4.8
TN is:  245.2
precision is:  0.6000000000000001
reall is:  0.18000000000000005
f1_score is:  0.276923076923077


F1 measure result of Google cloudVision API with object detection:
TP is:  7.200000000000002
FN is:  32.8
FP is:  6.400000000000001
TN is:  243.59999999999997
precision is:  0.5294117647058824
reall is:  0.18000000000000005
f1_score is:  0.2686567164179105


After sorted, the descending order of TN, FN, FP, TN, precision, recall, and f1-score are:

The TP result of APIs are:
[('GoolgeWithOnlyObj', 7.200000000000002), ('GoolgeWithBothDetector', 7.200000000000002), ('AWS', 5.6), ('GoolgeWithoutObj', 2.4), ('IBM', 2.0), ('Clarifai', 0.4)]

The FN result of APIs are:
[('Clarifai', 39.6), ('IBM', 38.0), ('GoolgeWithoutObj', 37.6), ('AWS', 34.39999999999999), ('GoolgeWithOnlyObj', 32.8), ('GoolgeWithBothDetector', 32.8)]

The FP result of APIs are:
[('AWS', 36.399999999999956), ('GoolgeWithBothDetector', 6.400000000000001), ('GoolgeWithOnlyObj', 4.8), ('Clarifai', 3.1999999999999997), ('GoolgeWithoutObj', 2.4), ('IBM', 1.6)]

The TN result of APIs are:
[('IBM', 248.39999999999998), ('GoolgeWithoutObj', 247.59999999999997), ('Clarifai', 246.79999999999998), ('GoolgeWithOnlyObj', 245.2), ('GoolgeWithBothDetector', 243.59999999999997), ('AWS', 213.60000000000008)]

The precision result of APIs are:
[('GoolgeWithOnlyObj', 0.6000000000000001), ('IBM', 0.5555555555555556), ('GoolgeWithBothDetector', 0.5294117647058824), ('GoolgeWithoutObj', 0.5), ('AWS', 0.13333333333333347), ('Clarifai', 0.11111111111111113)]

The recall result of APIs are:
[('GoolgeWithOnlyObj', 0.18000000000000005), ('GoolgeWithBothDetector', 0.18000000000000005), ('AWS', 0.14), ('GoolgeWithoutObj', 0.06), ('IBM', 0.05), ('Clarifai', 0.01)]

The f1-score result of APIs are:
[('GoolgeWithOnlyObj', 0.276923076923077), ('GoolgeWithBothDetector', 0.2686567164179105), ('AWS', 0.13658536585365863), ('GoolgeWithoutObj', 0.10714285714285712), ('IBM', 0.09174311926605504), ('Clarifai', 0.01834862385321101)]
