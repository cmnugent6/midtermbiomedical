*************READ ME************

Michael Nugent
Biomedical Midterm 2023

------------------------------------------

The following files train an SRGAN model, based on a the provided (tiny) dataset:

https://drive.google.com/file/d/1zGFhniov8QbpKcdg0a8jZF-QIdrNVDN6/view?usp=sharing

This dataset contain DME and DRUSEN images.

--------------------------------------------------------------------------------------------------------------

Training the Classifier (Assignment1)

1. A classifier was trained based of this data set. See "classifier.ipbyn" for the results. 
The accuracy is shown in the confusion matrix as .99 for DME and .94 for DRUSEN on the Test partition of data.

------------------------------------------------------------------------------------------------------------------

Generating images using SRGAN

1. To utilize SRGAN, they must be resized to 128x128 and 32x32. To do this, use the resize
file and change the size as necessary. This will take in all the images (after they're removed from folders manually)
And add them to an output folder corresponding to the size 32 or 128.

2. Use the SRGAN file to train the SRGAN model. This splits the data first into a 70 30 train test set. Total,
this data set contains 3048 images. The output size is ~850 generated super resolution images.
See the IPBYN for the results and examples of Super Resolution vs. low and high quality.

3. My example was ran at a batch size of 5, since google colab sometimes gives issues with long
training times. This training took approximately 8 hours. A batch size of 1 would produce much 
higher quality image results. (see image results in "SRGAN.ipbyn"). It is also important to note
that more epochs would result in higher quality images, this example is set to 150.

4. The generated images are then stored into a folder of choice.

--------------------------------------------------------------------------------------------------------------

Comparing the Models

1. I used the generated images as a test data set for the "Training Classifier (Assignment1)".

2. Replace the test)_datagen directory to the directory of the generated images. 

3. See the results of the classification on my generated images in the "generated_input_classifier.ipbyn"


--------------------------------------------------------------------------------------------------------------
RESULTS:
Due to training difficulties leading to time constraints for my project, the results only show
DME images from the SRGAN. This is potentially due to the data split occuring before SRGAN training. 

I think splitting the images after into 70/30 as mentioned in the instructions wouldve been correct
and given DRUSEN images as well.

My data split should have incorporated the file structure, I lost track of which images were DME and DRUSEN, but that
was the plan for the classfier to tell me.

Overall, the accuracy was 78% for the DME generated images and nan for DRUSEN (since there mustve been none).
I think this accuracy is okay given the cirucmstances. I think if my SRGAN was properly split and trained off of both
DME and DRUSEN images, it wouldve generated both types of images.

What would have also made the results of the generated images better is more epochs. This could have been done,
but the training issues I had early in the 2 weeks to complete took many days to solve.

I think the code is very functional, but the training image input for the SRGAN should have been done
in a more sophisticated fashion. Luckily, the SRGAN does generate images that seem to resemble good quality
and are accurate images.

--------------------------------------------------------------------------------------------------------------

IMPORTANT NOTES:
One thing to note is when you use my method (putting the images 32x32 and 128x128 into folders), you should be sure 
to sort the input reading of these folders to ensure that LR and HR syncs up. It took me alot of time to find why my images werent the same for LR and HR.
Google drive sorts them when you view the folder automatically, but they are not actually sorted in the file structure.


