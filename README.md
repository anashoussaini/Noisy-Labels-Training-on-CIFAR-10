# CIFAR-10 Classification on Symmetric and Asymmetric Noise

## Overview
This project explores the impact of label noise on the CIFAR-10 dataset and evaluates strategies to mitigate its effects. The study incorporates symmetric and asymmetric noise at varying levels (10%, 30%, 50%, 80%, and 90%) and applies several machine learning methodologies to enhance noise robustness. Three model architectures are developed and compared:
1. **Base CNN with Cross Entropy Loss**
2. **Regularized CNN with Symmetric Cross Entropy Loss**
3. **Advanced Regularized CNN with Normalized Cross Entropy and Reverse Cross Entropy Loss**

## Dataset
The CIFAR-10 dataset consists of 60,000 32x32 color images across 10 classes, divided into:
- **Training set:** 50,000 images
- **Test set:** 10,000 images

Label noise is introduced to simulate real-world data imperfections:
- **Symmetric Noise:** Random mislabeling across all classes.
- **Asymmetric Noise:** Systematic mislabeling of specific classes into predefined others.

## Models

### Base CNN + Cross Entropy Loss
- A simple convolutional neural network architecture.
- Uses traditional Cross Entropy Loss.
- Designed as a baseline for comparison.

### Regularized CNN + Symmetric Cross Entropy Loss
- Enhances the Base CNN by adding batch normalization and dropout layers.
- Implements Symmetric Cross Entropy Loss to balance robustness and accuracy.

### Advanced Regularized CNN + NCE and RCE Loss
- Introduces Kaiming and Xavier initialization.
- Employs the Active Passive Loss framework, combining Normalized Cross Entropy (NCE) and Reverse Cross Entropy (RCE).
- Optimized with SGD and fine-tuned hyperparameters.

## Methodology
1. **Noise Incorporation:** Simulate symmetric and asymmetric noise in training data while keeping validation and testing data clean.
2. **Data Preprocessing:**
   - Convert images to tensors.
   - Normalize pixel values (mean=0.5, standard deviation=0.5).
   - Batch size: 64.
3. **Training:** Models trained on noisy datasets with varying noise levels, using different loss functions and optimizers.
4. **Evaluation:** Compare test accuracies under different noise levels for each model.

## Results
The models\u2019 performance under symmetric and asymmetric noise conditions:
- **Base CNN:** Struggles with high noise levels, overfitting noisy labels.
- **Regularized CNN:** Improved robustness but shows limitations under extreme noise.
- **Advanced Regularized CNN:** Demonstrates superior resilience, maintaining higher accuracy across noise levels.

### Key Findings:
- NCE+RCE Loss outperforms Symmetric Cross Entropy Loss in high-noise scenarios.
- Regularization techniques like dropout and batch normalization enhance model generalization.

## Experimentation
- Experiments conducted on Google Colab Pro using NVIDIA Tesla V100 GPU.
- Models trained with 10 random seeds to ensure robustness.
- Training configurations include fixed epochs, learning rate tuning, and noise-specific parameter adjustments.

## Dependencies
- Python (>=3.7)
- PyTorch
- NumPy
- Matplotlib

## Usage
1. Clone the repository.
2. Install required dependencies.
3. Run the scripts to reproduce experiments:
   ```bash
   python train_model.py --model {base|regularized|advanced} --noise {symmetric|asymmetric} --level {10|30|50|80|90}
