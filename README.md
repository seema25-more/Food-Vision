# Food-Vision
The Food 101 Mini contains 101 classes of food with 75 training images and 250 testing images.
The implementation is done in google colab for faster processing.  Used Mixed Precision training for training our model in with different precisions. The goal will be to see if we can beat the baseline from original Food101 paper (50.76% accuracy on 101 classes) with 10% of the training data and some model setup like:
1. A ModelCheckpoint callback to save our progress during training, this means we could experiment with further training later without having to train from scratch every time
2. Data augmentation built right into the model
3. A headless (no top layers) EfficientNetB0 architecture from tf.keras.applications as our base model
4. A Dense layer with 101 hidden neurons (same as number of food classes) and softmax activation as the output layer
5. Categorical crossentropy as the loss function since we're dealing with more than two classes
 6. The Adam optimizer with the default settings
7. Fitting for 5 full passes on the training data while evaluating on 15% of the test data
