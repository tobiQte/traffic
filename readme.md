# AI50 Project Week 5 - Traffic
## Research links:
1. [Tensorflow research](https://www.tensorflow.org/guide/keras/sequential_model)
2. [OpenCV picture handling](https://docs.opencv.org/4.5.2/d2/d96/tutorial_py_table_of_contents_imgproc.html)
3. [OS python documentation][3]

[3]:(https://docs.python.org/3/library/os.html)

## Testing the neural network.
First i started with the convolutional network from the lesson and encountered an error in the input_shape.
"ValueError: Input 0 of layer "sequential" is incompatible with the layer: expected shape=(None, 28, 28, 1), 
found shape=(None, 30, 30, 3)"
After fixing i got an error for the output shape "ValueError: Shapes (None, 42) and (None, 10) are incompatible"
After fixing the output shape to 42 layers the neural network trains
the accuracy of the model finishes at 0.06 and does not seem to learn properly. Playing with the input filters i noticed
i could increase the accuracy to 0.9338 by applying 64 instead of 32 filters.  Increasing the epochs did not increase 
accuracy neither did a doubling of the nodes in the hidden layer. I noticed i could reduce epochs and still get a 
comfortable result of 0.9273 percent accuracy so i settled on 5 epochs. Next i tried changing the activation functions 
from the original settings with 32 filters in the input layer and sigmoid as activation.
i could achieve an even better result of 0.9906 accuracy and 0.0386 loss

## conclusion
It makes sense to experiment with the filter, activation functions and pool sizes in a neural network.
- the combination of different values can have different outcomes
- more nodes do not necessarily mean better results. Sometimes those are even much worse depending on the combination.
- There seems to be a sweet spot of hidden layers/nodes at 128 for this specific problem.
- Sigmoid with 32 input filters seems to be the optimal solution for this problem