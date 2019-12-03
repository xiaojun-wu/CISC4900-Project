# CISC 4900 Project
### Author Xiaojun Wu

This is a github for CISC 4900 Project. It store the project excel files and program files.

#### V0.3.1(12/03/2019)
This update is the report of trial background subtraction of images. I choose 63 photos as the dataset, these photos have similar background.
First, I chose MOG2 algorithm(Gaussian Mixture-based Background/Foreground Segmentation Algorithm) to do the background subtraction, but the result doesn't looks good because the lighting changes affect the resuls. Then I tried to used histogram equalization and CLAHE(Contrast Limited Adaptive Histogram Equalization) methodS to eliminate the lighting changes effect, the result still not be satisfied. I let google vision API to detect the MOG2's ouput images(foreground imamges). The result even worse than the original image's result.
```
Original images F1 measure result of Google cloudVision Label detect API:
TP is:  1.2000000000000002
FN is:  7.799999999999999
FP is:  0
TN is:  53
precision is:  1.0
reall is:  0.13333333333333336
f1_score is:  0.23529411764705888


Original images F1 measure result of Google cloudVision Object detection API:
TP is:  3.0
FN is:  6.0
FP is:  1.6
TN is:  51.400000000000006
precision is:  0.6521739130434783
reall is:  0.3333333333333333
f1_score is:  0.44117647058823534


foreground images F1 measure result of Google cloudVision Label detect API:
TP is:  0.4
FN is:  8.6
FP is:  0
TN is:  53
precision is:  1.0
reall is:  0.044444444444444446
f1_score is:  0.0851063829787234


foreground images F1 measure result of Google cloudVision Object detection API:
TP is:  2.8
FN is:  6.199999999999999
FP is:  8.400000000000002
TN is:  44.60000000000002
precision is:  0.24999999999999992
reall is:  0.3111111111111111
f1_score is:  0.2772277227722772
```


#### V0.1(10/14/2019)
This is the first submission, I submit the program files and excel files. The program files connect the APIs, submit the images and get the labels. The progrom  also save the labels in the corresponding excel file.

#### V0.2.0(10/27/2019)
This is the second submission. I submit the program that calculate the F1-score for each API's performence. The program will read the data from excel files, and general the indicator arrays. using these array to make the confusion matrix and than the F1-score.

#### V0.2.1(10/28/2019)
This is the third submission. I fix a problem in previous program and add the new feature that sort the TN, FN, FP, TN, precision, recall, and f1-score in dictionary. It will be help to see what differet of each API's performence.

#### Output of the measureProgram.py:

F1 measure result of IBM vision API:</br>
TP is:  2.0</br>
FN is:  38.0</br>
FP is:  1.6</br>
TN is:  248.39999999999998</br>
precision is:  0.5555555555555556</br>
reall is:  0.05</br>
f1_score is:  0.09174311926605504</br>


F1 measure result of Clarifai vision API:</br>
TP is:  0.4</br>
FN is:  39.6</br>
FP is:  3.1999999999999997</br>
TN is:  246.79999999999998</br>
precision is:  0.11111111111111113</br>
reall is:  0.01</br>
f1_score is:  0.01834862385321101</br>


F1 measure result of AWS vision API:</br>
TP is:  5.6</br>
FN is:  34.39999999999999</br>
FP is:  36.399999999999956</br>
TN is:  213.60000000000008</br>
precision is:  0.13333333333333347</br>
reall is:  0.14</br>
f1_score is:  0.13658536585365863</br>


F1 measure result of Google cloudVision API without object detection:</br>
TP is:  2.4</br>
FN is:  37.6</br>
FP is:  2.4</br>
TN is:  247.59999999999997</br>
precision is:  0.5</br>
reall is:  0.06</br>
f1_score is:  0.10714285714285712</br>


F1 measure result of Google cloudVision API with only object detection:</br>
TP is:  7.200000000000002</br>
FN is:  32.8</br>
FP is:  4.8</br>
TN is:  245.2</br>
precision is:  0.6000000000000001</br>
reall is:  0.18000000000000005</br>
f1_score is:  0.276923076923077</br>


F1 measure result of Google cloudVision API with object detection:</br>
TP is:  7.200000000000002</br>
FN is:  32.8</br>
FP is:  6.400000000000001</br>
TN is:  243.59999999999997</br>
precision is:  0.5294117647058824</br>
reall is:  0.18000000000000005</br>
f1_score is:  0.2686567164179105</br>


After sorted, the descending order of TN, FN, FP, TN, precision, recall, and f1-score are:</br>

The TP result of APIs are:</br>
[('GoolgeWithOnlyObj', 7.200000000000002), ('GoolgeWithBothDetector', 7.200000000000002), ('AWS', 5.6), ('GoolgeWithoutObj', 2.4), ('IBM', 2.0), ('Clarifai', 0.4)]</br>

The FN result of APIs are:</br>
[('Clarifai', 39.6), ('IBM', 38.0), ('GoolgeWithoutObj', 37.6), ('AWS', 34.39999999999999), ('GoolgeWithOnlyObj', 32.8), ('GoolgeWithBothDetector', 32.8)]</br>

The FP result of APIs are:</br>
[('AWS', 36.399999999999956), ('GoolgeWithBothDetector', 6.400000000000001), ('GoolgeWithOnlyObj', 4.8), ('Clarifai', 3.1999999999999997), ('GoolgeWithoutObj', 2.4), ('IBM', 1.6)]</br>

The TN result of APIs are:</br>
[('IBM', 248.39999999999998), ('GoolgeWithoutObj', 247.59999999999997), ('Clarifai', 246.79999999999998), ('GoolgeWithOnlyObj', 245.2), ('GoolgeWithBothDetector', 243.59999999999997), ('AWS', 213.60000000000008)]</br>

The precision result of APIs are:</br>
[('GoolgeWithOnlyObj', 0.6000000000000001), ('IBM', 0.5555555555555556), ('GoolgeWithBothDetector', 0.5294117647058824), ('GoolgeWithoutObj', 0.5), ('AWS', 0.13333333333333347), ('Clarifai', 0.11111111111111113)]</br>

The recall result of APIs are:</br>
[('GoolgeWithOnlyObj', 0.18000000000000005), ('GoolgeWithBothDetector', 0.18000000000000005), ('AWS', 0.14), ('GoolgeWithoutObj', 0.06), ('IBM', 0.05), ('Clarifai', 0.01)]</br>

The f1-score result of APIs are:</br>
[('GoolgeWithOnlyObj', 0.276923076923077), ('GoolgeWithBothDetector', 0.2686567164179105), ('AWS', 0.13658536585365863), ('GoolgeWithoutObj', 0.10714285714285712), ('IBM', 0.09174311926605504), ('Clarifai', 0.01834862385321101)]

#### V0.2.2(11/02/2019)
According to the previous step' result, the F1-score of these APIs are pretty low, after the analysis, the spreadsheet link below:
`<link>` : <https://docs.google.com/spreadsheets/d/1V1FE0DpVsn5CgApdd4Q7S8IDfIBaNoQU/edit#gid=1490159956>

<p align="center">Pattern Report</P><br>
This short report is a small conclusion of how the image’s pattern influence the Vision Recognition APIs performance. After submit a bunch of images to these APIs and record the return labels from them, I sorted the labels by relative to word of caribou, and split the labels into four groups, than gives the score to the labels of API’s prediction. I used the f1-score measurement to evaluate the API’s performance, I found the score the pretty low and now I am going to analyze what influence the API’s prediction.<br>
I write a program that extract all the API’s return labels are FN and store them in a new excel file.<br>
I looked up the false negative labels and found most API’s number of FN are actually the number of images have caribou, that means if the evaluation is strict, these API’s predicted label will not get any TP. So I scan the images that have caribou and extract the pattern from them, the most influence factors are distance from caribou to camera, caribou’s body in image is full or partial, and the ambient lighting. I evaluated the images by these three standards and save them in the excel file.<br>
I used the data to make the three chart per API, each chart shows the proportion of different values in one dimension (Distance, body part, and ambient lighting). The most relative factor is the distance from caribou to camera, most of the labels that get partial score are in the distance between very close to near. Only one API can recognize an image that the caribou is far away from the camera. The second relative factor is caribou’s body in images, the chart shows if caribou in an image isn’t partial but whole, the API can recognize it better. The most not relative factor is ambient lighting, most API’s result show the weak ambient lighting and strong ambient lighting are has no difference.<br>
The conclusion is the caribou is closer to camera, the image will be recognize has caribou by API is more possible.



