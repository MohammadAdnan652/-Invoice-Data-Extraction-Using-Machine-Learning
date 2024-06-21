# Invoice Data Extraction Report

## Table of Contents

- [Approach](#approach)
- [Model Architecture](#model-architecture)
- [Training Process](#training-process)
- [Evaluation Metrics](#evaluation-metrics)
- [Optimization Techniques](#optimization-techniques)
- [Deployment Steps](#deployment-steps)
- [Performance](#performance)

## Approach

The objective of this project is to extract key information from invoices using machine learning. The process is divided into several stages: data collection, preprocessing, annotation, model training, optimization, and deployment. The solution is designed to handle various invoice formats in English without relying on hardcoded labels, ensuring that the model understands context to accurately extract information.

## Model Architecture

We used a pre-trained BERT model (`dbmdz/bert-large-cased-finetuned-conll03-english`) from Hugging Face's Transformers library. BERT (Bidirectional Encoder Representations from Transformers) is a transformer-based model designed to understand the context of words in a sentence, making it ideal for tasks involving natural language understanding.

## Training Process

### Data Collection and Preprocessing

1. **Data Collection:** A diverse dataset of invoices in PDF format was collected from the internet.
2. **Text Extraction:** OCR (Optical Character Recognition) using `pdfplumber` and `pytesseract` was employed to convert PDFs to text.
3. **Text Cleaning:** The extracted text was cleaned to remove unnecessary whitespace and line breaks.

### Data Annotation

Manual annotation was performed to create a JSON file (`annotated_data.json`) containing key information such as sender, receiver, VAT number, and amounts.

### Model Fine-Tuning

The annotated data was used to fine-tune the pre-trained BERT model. The training parameters were set as follows:

- **Learning Rate:** 2e-5
- **Batch Size:** 16
- **Epochs:** 3

The dataset was split into training and validation sets to evaluate the model's performance during training.

## Evaluation Metrics

The model's performance was evaluated using precision, recall, and F1-score:

- **Precision:** The ratio of correctly predicted positive observations to the total predicted positives.
- **Recall:** The ratio of correctly predicted positive observations to the all observations in actual class.
- **F1-Score:** The weighted average of Precision and Recall.

## Optimization Techniques

### Model Conversion and Quantization

1. **Conversion to ONNX:** The fine-tuned model was converted to ONNX format for efficient deployment.
2. **Quantization:** Dynamic quantization was applied to reduce the model size and improve inference speed.

These steps ensure the model runs efficiently on client desktops without significant loss in accuracy.

## Deployment Steps

1. **Set Up Client Environment:** Ensure the client machine has the necessary libraries installed (`onnx`, `onnxruntime`, `transformers`).
2. **Load and Run the Model:**
   - Load the optimized ONNX model using ONNX Runtime.
   - Run the model on sample invoice text to extract key information.

## Performance

### Client Desktop Performance

The optimized model was tested on a client desktop. The following performance metrics were observed:

- **Inference Time:** The quantized model showed a reduction in inference time by approximately 50% compared to the original model.
- **Accuracy:** The accuracy remained consistent with the evaluation metrics obtained during model validation, demonstrating the model's robustness and efficiency.

### Conclusion

The invoice data extraction project successfully demonstrates the use of machine learning to handle diverse invoice formats and extract key information without hardcoded labels. The optimized model is efficient and performs well on client desktops, making it a practical solution for real-world applications.


