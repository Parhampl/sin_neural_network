# Sin Neural Network Project

This repository contains a MATLAB project where a neural network is trained to approximate the sine function using two different activation functions (`logsig` and `tansig`).

## Project Overview

- **Objective:** Train and evaluate a neural network to approximate the sine function.
- **Activation Functions Used:**
  - `logsig`
  - `tansig`
- **Training Algorithm:** Scaled Conjugate Gradient (`trainscg`)
- **Performance Metric:** Mean Squared Error (`mse`)

## File Structure

```
sin_neural_network_project/
│
├── README.md               # Project instructions and details
├── Sin_Neural_Network.m    # MATLAB script for training the network
├── images/
│   ├── image.png           # Training interface screenshot
│   ├── Figure_Image.png    # Activation function comparison plot
│   └── comparison.pdf      # PDF of comparison plots
```

## Getting Started

### Prerequisites

- MATLAB (tested with R2023a or later).
- Neural Network Toolbox installed.

### Running the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/sin_neural_network_project.git
   cd sin_neural_network_project
   ```

2. Open `Sin_Neural_Network.m` in MATLAB.

3. Run the script:
   ```matlab
   run('Sin_Neural_Network.m')
   ```

4. The script will:
   - Train the neural network.
   - Generate plots comparing the true and predicted sine values for each activation function.
   - Save the comparison plots as `comparison.pdf`.

### Results

You can view the training results in the `images/` folder:

- **Training Interface:**
  ![Training Interface](images/image.png)

- **Activation Function Comparison:**
  ![Comparison Plot](images/Figure_Image.png)

- **PDF of Comparison Plots:** See [`comparison.pdf`](images/comparison.pdf).

## Key Sections in the Code

- **Data Creation:**
  ```matlab
  x = linspace(-2*pi, 2*pi, 1000);
  y = sin(x);
  ```
  Generates input and target values for the sine function.

- **Model Training:**
  ```matlab
  net = fitnet(hiddenLayerSize, 'trainscg');
  net.layers{1}.transferFcn = activation_functions{i};
  [net,tr] = train(net,x,y);
  ```
  Trains the neural network using `trainscg` with different activation functions.

- **Visualization:**
  ```matlab
  subplot(2, 2, i);
  plot(x, y, 'b', 'LineWidth', 1.5);
  hold on;
  plot(x, y_pred, 'r', 'LineWidth', 1.5);
  ```
  Plots the true and predicted sine values for comparison.

## Future Enhancements

- Experiment with additional activation functions.
- Compare other training algorithms (e.g., Levenberg-Marquardt).
- Extend to other mathematical functions (e.g., cosine, exponential).

## Contributions

Feel free to fork the repository and submit pull requests for enhancements or bug fixes.

---

Enjoy exploring the project! 🚀
