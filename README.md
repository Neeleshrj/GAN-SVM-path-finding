# Path Planning using Machine Learning

This project was made as a POC to find if GAN (Generative Adversarial Network) and SVM (Support Vector Machines) can be used for Path Planning.

## GAN

<ol>
    <li>We create a dataset of 5000 images with each 32 x 32 pixel images with randomly placed obstacles and start and end position. These are our Map Images.</li>
    <li>Path Finding is done between the start and endpoint of the Map Image using A* Algorithm to create Path Image which contains the obstacles as well as a path between the points A and B.</li>
    <li>We then carry out some pre-processing on the images produced in tha dataset</li>
    <li>We create a Generator and Discriminator using Tensorflow and train them for 20 epochs.</li>
    <li>The results are then analysed.</li>
</ol>

The neural network took 4 hours (20 mins on GPU, 5000 images dataset). The outputs are as follows:

### Output
![gan original map](https://github.com/Neeleshrj/store-your-meds/assets/57111920/c535ec3b-8b3e-4d97-909e-63a8b155a57f)
<br/>
Unsolved Map
<br/>

![gan solved map](https://github.com/Neeleshrj/store-your-meds/assets/57111920/55897cad-da3e-4caa-ab69-2171e8f8a107)
<br/>
Map after pathfinding using A*

![gan result](https://github.com/Neeleshrj/store-your-meds/assets/57111920/53fea4a5-6efe-435f-a575-a789e02ffc81)
<br/>
Resultant Image generated

The other approach taken was find the path using SVM to give all possible traversable points which can then be fed into an A* algorithm for better heuristic path finding.

## SVM
<ol>
    <li>We create a dataset of 5000 images with each 32 x 32 pixel images with randomly placed obstacles and start and end position. These are our Map Images.</li>
    <li>Path Finding is done between the start and endpoint of the Map Image using A* Algorithm to create Path Image which contains the path between the points A and B.</li>
    <li>We then carry out some pre-processing on the images produced in tha dataset</li>
    <li>We create a SVM model using SVR of scikitlearn and train it.</li>
    <li>The results are then analysed.</li>
</ol>

The model took 10 hours. The outputs are as follows:

### Output
![gan original map](https://github.com/Neeleshrj/store-your-meds/assets/57111920/06f093a8-ca7b-4cf0-ad4f-0d3738faaafc)
<br/>
Unsolved Map
<br/>

![gan solved map](https://github.com/Neeleshrj/store-your-meds/assets/57111920/f3bc8cff-2bbb-48e9-a048-43f752d969e8)
<br/>
Path Image after pathfinding using A*
<br/>
<br/>
The final output is 81.25% accurate mapping of all traversable points on the orignal map which can later be used for path finding.

## Future Work
The POC can be worked further on to improve the path finding abilites of UAVs especially in a obstacle ridden dynamic enviornment with low threat count.
