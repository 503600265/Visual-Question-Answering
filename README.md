# Visual Question Answering (VQA) with ViLT and Custom Loss

This project explores the application of Visual Question Answering (VQA), where the goal is to answer questions about images using computer vision and natural language processing techniques. The approach combines a pre-trained transformer model, ViLT, for efficient feature extraction, along with a custom classifier that integrates answer confidence into the training process.

## Overview

The task of VQA involves interpreting visual data and generating responses to related textual queries. Our project aims to develop a resource-efficient approach by leveraging pre-trained models for feature extraction and introducing a custom loss function that accounts for the confidence levels of annotated answers.

## Project Highlights

- **Model Architecture**: The model utilizes ViLT (Vision-and-Language Transformer) for feature extraction, followed by a Multi-Layer Perceptron (MLP) classifier to predict the answers.
- **Dataset**: The VQA 2.0 dataset was used, containing over 200,000 images and 1.1 million questions. The dataset includes multiple annotated answers with associated confidence levels for each question, filtered to the top 2,000 most frequent answers.
- **Custom Loss Function**: A custom loss function was implemented to weigh training samples based on their confidence scores. This penalizes incorrect answers more if they are marked with high confidence, thereby enhancing the model's accuracy and reliability.
- **Performance Evaluation**: The model was evaluated using official VQA metrics, comparing its performance against baseline models and state-of-the-art approaches.

## Methodology

1. **Preprocessing**: Images were resized to the input dimensions expected by the ViLT model. Both visual and textual data were preprocessed and passed to ViLT for feature extraction.
2. **Model Training**:
   - A custom loss function was applied during training to incorporate confidence levels associated with each answer.
   - The model was trained for 50 epochs using the Adam optimizer with a learning rate of 0.0001.
3. **Performance Comparison**: The model's performance was assessed against baseline approaches, demonstrating improvements in handling ambiguous questions by incorporating confidence metrics.

## Results

The model achieved reasonable accuracy on the VQA 2.0 dataset, especially in the "Other" category of questions, where confidence-aware training led to a more nuanced understanding of ambiguous cases. While it did not surpass the accuracy of cutting-edge models, it offered a computationally efficient alternative.

## Getting Started

To replicate this project, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/503600265/Visual-Question-Answering
   cd Visual-Question-Answering
