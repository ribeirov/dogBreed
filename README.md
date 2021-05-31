# dogBreed
Udacity Deep Learning - Dog Breed Classification Project

As part of the Udacity Deep Learning Nanodegree program built a convolutional neural network to classify photos of dogs into different breeds.
Dogs were classified into one of 133 breeds as per sample data of over 8,000 photos shared by the Udacity team
After much tinkering ended up with a CNN with 3 convolutional layers (interspersed by maxpooling layers). Also used relU activation functions and 2d batch normalization.
Finally classification was performed by means of one fully-connected layer (post application of drop-out).

Found that it was quite difficult to achieve the required 10% accuracy threshold and had to experiment with multiple model configurations together with different parameter values (e.g. learning rate and drop-out percentage). Also found that it was key for data loader method to be set to shuffle=True as otherwise model wasn't able to converge if photos were fed in classified by successive breeds. 

Next implemented a resnet50 using transfer learning and achieved much greater accuracy.

Notwithstanding all the work the classification of out-of-sample images (that I attach to this github submission) into human / dog categories (following the ImageNet classifications) were tough with 2 out of 6 incorrectly classified. Our jellicle cat was identified as a dog (Boston terrier) and our Nova Scotia duck tolling retriever was identified as a human (though the breed was later correctly identified). The remaining 4 images were correctly classified as dog / human. One possible improvement would be in the logic in run_app to positively enforce that humans are non dogs (and dogs are non humans). For both the man faces and the dog identifications we could ensure the photos are appropriately resized, cropped and normalized. For the man faces perhaps we could investigate other approaches besides the haar cascade. For the VGG16 (dog identification) we could investigate with other models (e.g. resnet).
