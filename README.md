# Training and Prediction Guide

This document provides step-by-step instructions for setting up the environment, training the model, and generating predictions.

## Environment Setup

1. **Create a Conda Environment**
   ```sh
   conda create -p venv python=3.12.8 -y
   ```
   **Note:** Ensure that Python 3.12.8 was the version i had in my case,but u can replace with your version.

2. **Activate the Environment**
   ```sh
   conda activate <path_to_venv>
   ```

3. **Install Required Packages**
   ```sh
   pip install -r requirements.txt
   ```

## Loading MovingMnist Data

To load the MovingMNIST dataset from the gzip file, use the following command:
   ```sh
   python mm.py
   ```

## Training the Model

To start training, run:
   ```sh
   python main.py
   ```
You can customize the number of epochs and batch size as per your requirements by modifying the respective parameters in `main.py`.

### Model Checkpoints

- The trained model is saved in the current directory in the following format:
  
  *checkpoint_<epoch>_<loss>.pth.tar*
  
- It is recommended to use a checkpoint with the lowest validation loss for better predictions.

## Generating Predictions

To generate predictions, load the desired checkpoint and run:
   ```sh
   python prediction.py
   ```
![](https://github.com/Yashas-naidu/ConvLSTM/blob/main/images/movingmnist.png)
## Viewing Logs in TensorBoard

Logs for **Epoch vs Loss** are stored inside the `runs` directory. To visualize them using TensorBoard, execute:
   ```sh
   tensorboard --logdir=./runs
   ```

This will launch TensorBoard, where you can analyze the training progress visually.

---

**Note:** Ensure that all dependencies are correctly installed before proceeding with training and prediction.

