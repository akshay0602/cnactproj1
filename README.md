To prepare the data for training, i made a small code in OpenCV. It does following things:

a) It loads the image.

b) Selects the digits ( obviously by contour finding and applying constraints on area and height of letters to avoid false detections).

c) Draws the bounding rectangle around one letter and wait for key press manually. This time we press the digit key ourselves corresponding to the letter in box.

d) Once corresponding digit key is pressed, it resizes this box to 10x10 and saves 100 pixel values in an array (here, samples) and corresponding manually entered digit in another array(here, responses).

e) Then save both the arrays in separate txt files.

At the end of manual classification of digits, all the digits in the train data( train.png) are labeled manually by ourselves, image will look like below:

For training we do as follows:

a) Load the txt files we already saved earlier

b) create a instance of classifier we are using ( here, it is KNearest)

c) Then we use KNearest.train function to train the data

For testing purposes, we do as follows:

a) We load the image used for testing

b) process the image as earlier and extract each digit using contour methods

c) Draw bounding box for it, then resize to 10x10, and store its pixel values in an array as done earlier.

d) Then we use KNearest.find_nearest() function to find the nearest item to the one we gave. ( If lucky, it recognises the correct digit.)
