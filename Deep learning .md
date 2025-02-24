# Deep learning

Deep learning is a sub field of machine learning

- Language Translation
- Self-Driving Cars
- Medical Diagnostics
- Chatbots

Used on multiple types of data such as images, text and audio. Discover features on their own and has a layered network structure.

Requires large amounts of data for training as compared to traditional machine learning models. There are several frameworks but `PyTorch` is one of most popular and maintained deep learning framework.

we can import `PyTorch` as

```python
import torch
```

Other than that it also supports

- image data with `torchvision`
- audio data with `torchaudio`
- text data with `torchtext`

The fundamental dataset in a `PyTorch` network is a Tensor which like building blocks of it. It is like an array which support many mathematical operations.

```python
import torch
lst = [[1,2,3], [4,5,6]]
tensor = torch.tensor(lst)

# tensor creation directly from numpy array
np_array = np.array(array)
np_tensor = torch.from_numpy(np_array)
# methods of tensor
tensor.shape # shows dimensions of the tensor
tensor.dtype # shows the data type of the tensor
tensor.device # shows where the tensor is loaded on i.e. cpu or gpu
```

like `numpy` arrays we can add or subtract tensor for compatible shape of tensor meaning the have the same shape. it also support element wise multiplication. it also supports following

- Transposition
- Matrix Multiplication
- Concatenation

## First Neural Network

```python
import torch.nn as nn
# input tensor with three layers
input_tensor = torch.tensor([[0.3471, 0.4547, -0.2356]])
# Define our first layer (input layer)
linear_layer = nn.Linear(in_features=3, out_features=2)
output = linear_layer(input_tensor)
print(output)
# methods of linear_layer
linear_layer.weights
linear_layer.bias

# matrix multiplication of the weights and input tensors followed by adding the
# bias
# Networks with only linear layers are known as fully connected.

# Stacking Linear layers so that input pass sequentially through each layer

model = nn.Sequential(
  nn.Linear(10,18),
  nn.Linear(18,20),
  nn.Linear(20,5)
)

# The output is not meaningful until each layer is tuned for weights and biases
```

## Discovering activation function

```python
# we can also add non-linearity to our models using activation functions
# such as sigmoid activation function which is widely used for binary 
# classification

import torch
import torch.nn as nn

input_tensor = torch.tensor([[6.0]])
sigmoid = nn.Sigmoid()
output = sigmoid(input_tensor )

# when performing a binary classification a sigmoid is used as the last function 
# of the neural network. a sigmoid at the last in a neural network of only linear
# layers is equal to tradational logistic regression. we use sigmoid for binary
# classification for multi-class classification we use softmax

probabilities = nn.Softmax(dim=-1) #apply to last layer
output_tensor = probabilities(input_tensor)
```

## Running a forward Pass

- Input data is passed forward or propagated through a network
- computations performed at each layer
- output of each layer passed to each subsequent layer
- output of the final layer : prediction
- used for both training and making new predictions
- final output can be binary classification, multi-class classification or regression.

Backward Pass

- It is used to update weights and biases during training.
- propagate forward
- compare output to true values
- back propagate to update weights and biases
- repeat until weights and biases are tuned to produce useful outputs.

## Using loss function

- Gives feedback to the model during training
- Takes in model prediction and ground truth (actual value)
- returns a float
- Goal is to minimize the loss

```python
import torch.nn.functional as F
F.one_hot(torch.tensor(0), num_classes = 3)
```

### Cross entropy loss function

- It is mainly used for classification problems
- For Regression problems we us MSEL

```python
from torch.nn import CrossEntropyLoss
scores = tensor([[-0.1211, 0.1509]])
one_hot_target = tensor([[1, 0]])

criterion = CrossEntropyLoss()
criterion(scores.double(), one_hot_target.double())
```

```python
criterion = nn.MSELoss()
loss = criterion(predictions, target)
```

## Using Derivatives to update model params

```python
model = nn.Sequnetial(
  nn.Linear(16, 8),
  nn.Linear(8, 4),
  nn.Linear(4, 2)
)
predictions = model(sample)

criterion = CrossEntropyLoss()
loss = criterion(predictions, target)
loss.backward()

# accessing each layers params
model[0].weight.grad
model[1].weight.grad
model[2].weight.grad
model[0].bias.grad
model[1].bias.grad
model[2].bias.grad

import torch.optim as optim
# Create the optimizer (stochastic gradient descent)
optimizer = optimizer.SGD(model.parameters(), lr=0.001)
optimizer.step()

weight0 = model[0].weight
weight1 = model[1].weight
weight2 = model[2].weight

# Access the gradients of the weight of each linear layer
grads0 = weight0.grad
grads1 = weight1.grad
grads2 = weight2.grad

# Update the weights using the learning rate and the gradients
weight0 = weight0 - lr * grads0
weight1 = weight1 - lr * grads1
weight2 = weight2 - lr * grads2
```

```python
dataset = TensorDataset(torch.tensor(features).float(), 
                       torch.tensor(target).float())
    dataloader = DataLoader(dataset, batch_size=4, shuffle=True)

model = nn.Sequential(nn.Linear(4, 2),
                     nn.Linear(2, 1))

criterion = nn.MSELoss()
optimizer = optim.SGD(model.parameters(), lr=0.001)

# The Training Loop
for epoch in range(num_epochs):
  for data in dataloader:
    # set the gradient to zero
    optimizer.zero_grad()
    feature, target =  data
    pred = model(feature)
    loss = criterion(pred, target)
    loss.backward()
    optimizer.step()
```

## ReLU

Sigmoid and SoftMax are two activation functions which are used as the last layer of the neural network here we'll look at two activation functions which are used between the layers of neural network.

The gradient of the sigmoid function approach zero at low and high values which results in vanishing gradient in back propagation hence make model training challenging Similarly the SoftMax also saturates as it is also bounded between 0 and 1. To adhere these issues we utilize Rectified Linear Unit or `ReLU`

`fx =  max(x, 0)`

```python
relu = nn.ReLU()
leaky_relu = nn.LeakyReLU(negative_slope = 0.05)
```

The Leaky `ReLU` works similarly for positive values but for negative values it multiply the input by a small coefficient defaulted at 0.01

## Calculating the number of Parameters

Multiply the output neurons to input neurons + 1. or we can use built-in function.

```python
total = 0
for parameters in model.parameters():
  total += parameters.numel()
print(total)
```

## Learning Rate and Momentum

```python
sgd = optim.SGD(model.parameters(), lr=0.01, momentum=0.95)
```

Learning rate is the step size taken by the optimizer. (10^-2 and 10^-4)

momentum controls the inertia of the optimizer. (0.85 and 0.99)

## Layer initialization, Transfer Learning and Fine Tuning

```python
# Layer Initialization
import pytorch.nn as nn
layer = nn.Linear(64, 128)
nn.init.uniform_(layer.weight)
print(custom_layer.fc.weight.min())

# Transfer Learning : Reusing a model trained on a first task
# for a second similar task to accelarate the training process
# we can save and load weights as
pytorch.save()
pytorch.load()

# Fine Tuning : A type of transfer learning
# Smaller learning rate
# not every layer is trained (we freeze some of them)
# a rule of thumb is to freeze the early layers of the model
# and train layers closer to the the output

# Freezing a layer
import torch.nn as nn
model = nn.Sequential(
    nn.Linear(64, 128),
    nn.Linear(128, 256)
)

for name, param in model.named_parameters():
  if name == '0.weight':
    param.requires_grad = False
```

## Loading Data:

```python
# Read the data from a csv file into a pandas dataframe and separate features
# and the target in separate dataframes.
import torch
from torch.utilis.data import TensorDataset
from torch.utilis.data import DataLoader

dataset = TensorDataset(torch.tensor(X).float(), torch.tensor(y).float())
# accessing individual samples
sample = dataset[0]
input_sample, label_sample = sample

dataloader = DataLoader(dataset, batch_size=4, shuffle= True)
```

## Evaluating Model Performance

Split the dataset into three subsets:

- Training: Adjust model parameters (80-90%)
- Validation: Used for hyperparameter tuning (10-20%)
- Testing: Used to calculate final metrics (50-10%)

```python
# training loss calulcation
training_loss = 0.0
for i, data in enumerate(trainloader, 0):
  # Run forward pass
  # Calculate loss
  loss = criterion(outputs, labels)
  # Calculate gradient
  training_loss += loss.item()

epoch_loss = training_loss / len(trainloader)

# validation loss calulcation
validation_loss = 0.0
model.eval() # put model in evaluation mode
with torch.no_grad() # speed up forward pass
for i, data in enumerate(trainloader, 0):
  # Run forward pass
  # Calculate loss
  loss = criterion(outputs, labels)
  # Calculate gradient
  validation_loss += loss.item()

epoch_loss = training_loss / len(trainloader)
model.train()
```

## Calculating accuracy with torchmetrics

```python
import torchmetrics

metrics = torchmetrics.Accuracy(task='multiclass', num_classes=3)

for i, data enumerate(dataloader, 0):
  features , label = data
  outputs = model(features)
  # Calculate accuracy over the batch
  acc = metric(outputs, labels.argmax(dim=-1))

# Calculate accuracy over whole epoch
acc =  metric.compute()
metric.reset()
```

## Fighting Overfitting

Overfitting happens when model doesn't generalize to unseen data.

Good performance on training dataset but poor performance on validation dataset.

- Small Dataset
- model has too much capacity
- weights are too large

Either we can dropout some layers or add a new layer known as dropout layer or add weight decay to force model to use small weights or we can use augmentation if data is small. Dropout is a regularization technique where a set or random neurons is set to zero at each update.

```python
# dropout layer
model = nn.Sequential(
    nn.Linear(8,4),
    nn.ReLU(),
    nn.Dropout(p=0.5)
)
features = torch.randn((1, 8))
model(i)

# weight decay
optimizer = optim.SGD(model.parameters(), lr=1e-3, weight_decay=1e-4)
```

## PyTorch with OOP

```python
# Writing a DataLoader using OOP

from torch.utils.Dataset import Dataset

class customDataSet(Dataset):
  def __init__(self, csv_path):
    super().__init__()
    df = pd.read_csv(csv_path)
    self.data = df.to_numpy()

  def __len__(self):
    return self.data.shape[0]

  def __getitem__(self, idx):
    features = self.data[idx, :-1]
    labels = self.data[idx, -1]
    return features, labels


dataset_train = customDataSet("path to csv")

from torch.utils.DataLoader

dataloader_train = DataLoader(
  dataset_train,
  batch_size = 2,
  shuffle = True
) 

features, labels = next(iter(data_loader_train))
```

## Neural Network with OOP

```python
import torch.nn as nn
import torch.nn.functional as F

class Net(nn.Module):
    def __init__(self):
        super(Net, self).__init__()
        self.fc1 = nn.Linear(9,16)
        self.fc2 = nn.Linear(16,8)
        self.fc3 = nn.Linear(8,1)
        
    def forward(self, x):
        x = nn.functional.relu(self.fc1(x))
        x = nn.functional.relu(self.fc2(x))
        x = nn.functional.sigmoid(self.fc3(x))
        return x
```

## Training Loop:

- Define Loss function and Optimizer know as criterion (`BCELoss` for Binary Classification)

```python
import torch.nn as nn
import torch.optim as optim

criterion = nn.BCELoss()
optimizer = optim.SGD(net.parameters(), lr=0.01)

for epoch in range(1000):
  for features, labels in dataloader_train:
    optimizer.zero_grad()
    outputs = net(features)
    loss = criterion(
      outputs,
      labels.view(-1, 1)
    )
    # compute gradient
    loss.backward()
    optimizer.step()
```

### Types of Optimizers

- SGD
- Adagrad
- RMSprop
- Adam

### Evaluation Loop

```python
from torch.metrics import Accuracy
acc = Accuracy(task='binary')

net.eval()
with torch.no_grad():
  for features, labels in dataloader_test:
      output = net(features)
      preds = (output >= 0.5).float()
      acc(preds, labels.view(-1, 1))

accuracy = acc.compute()
```

## Vanishing and Exploding Gradient

- Gradient gets smaller and smaller during backward pass

```python
from torch.nn.init as init
init.kaiming_uniform_(layer.weight)

init.kaiming_uniform_(self.fc1.weight)
init.kaiming_uniform_(self.fc2.weight)
init.kaiming_uniform_(self.fc3.weight,
                     nonlinearity="sigmoid")
```

## Activation Functions

```python
nn.functional.relu()
# suffers from dying neuron problem
nn.functional.elu()
# improve the functionality of ReLU
```

## Batch Normalization

```python
class Net(nn.Module):
  def __init(self):
    super(Net, self).__init__()
    self.fc1 = nn.Linear(9, 16)
    self.bn1 = nn.BatchNorm1d(16) # preceding layer's input size

  def forward(self, x):
    x = self.fc1(x)
    x = self.bn1(x)
    x = nn.functional.elu(x)
```

## Handling Image Data

what is an image? images are composed of pixels short of picture elements. it is the smallest unit of the image. Each pixel contains numerical information about its color.

- In a grayscale image each pixel represents a different shade of gray 0-255
- In color images each pixel is described by 3 integers one for each color channel RGB.

```python
# make two folder train and test
# each folder is a label for images which it contains
from torchvision.datasets import ImageFolder
from torchvision import transforms

train_transfrom = transform.Compose([
  transforms.ToTensor(),
  trnasforms.Resize((128, 128)), # ensure all images are of
  # same size
])

dataset_train = ImageFolder(
  "data/train",
  transform = train_transforms,
)

dataloader_train = DataLoader(
  dataset_train,
  shuffle=True,
  batch_size=1,
)

image, label = next(iter(dataloader_train))
print(image.shape)
# to display image, not needed for grayscale images
image = image.squeeze().permute(1, 2, 0)

# data augmentation
train_transforms = transforms.Compose([
  transforms.RandomHorizontalFlip(),
  transforms.RandomRotation(45),
  transfroms.ToTensor(),
  transforms.Resize()
])
```

## Convolutional Neural Networks

In grayscale image of 256x256 there will be result in over 65k model inputs and over 65 million params if we use a layer of 1000 neurons and similarly for color image the numbers goes significantly large which makes the model training very slow. Also the linear layer does not identify spatial patterns. so a better approach is to use convolutional layers

```python
nn.Conv2d(3, 32, kernal_size=3)
nn.Conv2d(3, 32, kernal_size=3, padding=1) #zero-padding

# Max Pooling
# Slide over non-overlapping window over input, at each 
# position ratain only maximum value. It is used after the
# convolutional layer to reduce the size of spatial dimension
nn.MaxPool2d(kernel_size=2)

class Net(nn.Module):
  def __init__(self, num_classes):
    super.__init__()
    self.feature_extractor = nn.Sequential(
      nn.Conv2d(3, 32, kernel_size=3, padding=1),
      nn.ELU(),
      nn.MaxPool2d(kernel_size=2), 
      #max pooling halfs the width and height
      nn.Conv2d(32, 64, kernel_size=3, padding=1),
      nn.ELU(),
      nn.MaxPool2d(kernel_size=2),
      nn.Flatten()
    )
    self.classifier = nn.Linear(64*64*16, num_classes)

  def forward(self, x):
    x = self.feature_extractor(x)
    x = self.classfier(x)
    return x


class Net(nn.Module):
    def __init__(self, num_classes):
        super().__init__()
        # Define feature extractor
        self.feature_extractor = nn.Sequential(
            nn.Conv2d(3, 32, kernel_size=3, padding=1),
            nn.ELU(),
            nn.MaxPool2d(kernel_size=2),
            nn.Conv2d(32, 64, kernel_size=3, padding=1),
            nn.ELU(),
            nn.MaxPool2d(kernel_size=2),
            nn.Flatten(),
        )
        # Define classifier
        self.classifier = nn.Linear(64*16*16, num_classes)
    
    def forward(self, x):  
        # Pass input through feature extractor and classifier
        x = self.feature_extractor(x)
        x = self.classifier(x)
        return x
```

### Training Loop for Images:

```python
net = Net(num_class=7)

criterion = nn.CrossEntropyLoss()
optimizer = optim.Adam(net.parameters(), lr=0.01)

for epoch in range(10):
  for images, labels in data_loader_tain:
    optimizer.zero_grad()
    outputs = net(images)
    loss = criterion(outputs, labels)
    loss.backward()
    optimizer.step()
```

### Evaluating Image Classifiers:

```python
# for Binary Classification:
  # precision: Fraction of correct positive predictions
  # recall: Fraction of all positive examples correctly predicted
# for multi-class Classification:
  # separate precision and recall for each class
  # suppose we have 7 classes then we'll have 7 precision and recall scores
  # either analyse seprately or aggregate them
    # micro average: global calculation
    #
```

?descriptionFromFileType=function+toLocaleUpperCase()+{+[native+code]+}+File&mimeType=application/octet-stream&fileName=Deep+learning+.md&fileType=undefined&fileExtension=md