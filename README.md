Download Link: https://assignmentchef.com/product/solved-comp9517-lab3-image-segmentation
<br>
<strong>Image Segmentation </strong>

<u>MeanShift</u> is a clustering algorithm that assigns pixels to clusters by iteratively shifting points towards the modes in the feature space, where a mode is a position with the locally highest number of data points (highest density). A visualisation can be seen <a href="https://informatics.sydney.edu.au/images/blog/ms_2d_bw_2.gif">here</a><a href="https://informatics.sydney.edu.au/images/blog/ms_2d_bw_2.gif">.</a>

<u>Watershed</u> is a transformation that aims to segment the regions of interest in a grayscale image. This method is particularly useful when two regions of interest are close to each other; that is, their edges touch. It treats the image as a topographic map, with the intensity of each pixel representing the height. For instance, dark areas are considered to be ‘lower’, and act as troughs. Bright areas are ‘higher’, acting as hills or as a mountain ridge.

Visualising the

Watershed: The left image can be topographically represented as the image on the right. Adopted from <a href="https://www.youtube.com/watch?v=K5P5rjDiZzk">Agarwal 2015</a><a href="https://www.youtube.com/watch?v=K5P5rjDiZzk">.</a>

<u>Image segmentation</u> can be thought of as labelling pixels in an image. It is an important research topic in computer vision and comes in many different flavours: interactive segmentation, semantic segmentation, instance segmentation, and many more. In this lab the MeanShift clustering algorithm and the Watershed algorithm will be used to solve unsupervised image segmentation.

<strong>Task 1 (1 mark):</strong> Use the MeanShift algorithm to segment images.

Images to be used for this task: <strong>shapes.png</strong> and <strong>strawberry.png</strong>

<strong>Hint:</strong> Use <a href="https://scikit-learn.org/stable/modules/generated/sklearn.cluster.MeanShift.html">MeanShift clustering</a> from scikit-learn.

<u>Step 1</u>. Once you have read the images into numpy arrays, extract each colour channel (R, G, B) so you can use each as a variable for classification. To do this you will need to convert the colour matrices into a flattened vector as depicted in the image below.

<u>Step 2</u>. Then you can use the new flattened colour sample matrix (10,000 x 3 if your original image was 100 x 100) as your variable for classification.

<u>Step 3</u>. Use the MeanShift <strong>fit_predict</strong> function to perform a clustering and save the cluster labels, which we want to observe.

Submit the segmented images.

<strong>Task 2 (1 mark):</strong> Use Watershed transformation to segment <u>grayscale</u> versions of the images.

Images to be used for this task: <strong>shapes.png</strong> and <strong>strawberry.png</strong>

<strong>Hint:</strong> Use <a href="https://scikit-image.org/docs/dev/auto_examples/segmentation/plot_watershed.html">Watershed segmentation</a> from scikit-learn.

<u>Step 1</u>. Convert the image to grayscale.

<u>Step 2</u>. Calculate the distance transform of the image. Note: this is a vital step of the Watershed algorithm. Visualising this step may help you understand how the algorithm works! Plot the result of the distance transform to see what is happening under the hood.

<u>Step 3</u>. Generate the Watershed markers as the ‘clusters’ furthest away from the background.

This can be syntactically confusing so make sure to check the example code in the link above.

<u>Step 4</u>. Perform Watershed on the image. This is the part where the image is ‘flooded’ and the water sinks to the ‘catchment basins’ based on the markers found in Step 3.

Submit the segmented images.

<strong> </strong>

<strong>Note:</strong> You might notice that MeanShift performs better for one image, while Watershed performs better for the other. A plotting template has been provided so you can compare the results of the two algorithms side by side. This will look something like this:

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>Task 3 (0.5 mark):</strong> Improve Watershed segmentation results.

Images to be used for this task: <strong>coins.png </strong>and<strong> kiwi.png</strong>

<u>Step 1</u>. Use the MeanShift and Watershed algorithms on these images as in the previous tasks.

<u>Step 2</u>. Notice that Watershed does not work very well for either image. Do some image manipulation to improve the Watershed segmentation.

Submit the final segmented images.

<strong> </strong>