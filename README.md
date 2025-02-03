# Image Classification with TensorFlow on macOS GPU

This project demonstrates how to build and train an image classifier using TensorFlow with GPU acceleration on macOS, leveraging Apple's Metal framework.

## Features

- Utilizes TensorFlow with Metal GPU acceleration for macOS
- Implements a simple Artificial Neural Network (ANN) for image classification
- Supports multiple classes: buildings, forest, glacier, mountain, sea, and street
- Optimized for performance on Apple Silicon (M1/M2/M3) GPUs

## Requirements

- macOS 13 (Ventura) or later
- Python 3.9+
- TensorFlow 2.x
- Apple Silicon Mac (M1/M2/M3) for GPU acceleration

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/adityaamehra/Image-Classifier.git
   cd Image-Classifier
   ```

2. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```

3. Install the required packages:
   ```bash
   pip install tensorflow-macos tensorflow-metal
   ```

## Usage

1. Prepare your dataset:
   - Organize images into `train` and `test` folders
   - Each class should have its own subfolder

2. Update the `data_dir` variable in the script to point to your dataset location

3. Run the training script:
   ```bash
   python train.py
   ```

4. Monitor the training progress and GPU utilization using Activity Monitor

## Model Architecture

The model uses a simple ANN with the following layers:
- Flatten layer (input: 150x150x3)
- Dense layer (512 units, ReLU activation)
- Dense layer (256 units, ReLU activation)
- Output layer (6 units, Softmax activation)

## Optimizations

- Uses `tf.data.AUTOTUNE` for optimized data pipeline
- Implements mixed precision training for improved performance
- Leverages Metal GPU acceleration for faster training

## Troubleshooting

If you encounter issues with GPU detection:
1. Ensure you're running macOS 13 (Ventura) or later
2. Reinstall TensorFlow dependencies:
   ```bash
   pip install --upgrade tensorflow-macos tensorflow-metal
   ```
3. Verify Xcode command-line tools are installed:
   ```bash
   xcode-select --install
   ```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the [MIT License](LICENSE).
