# -Invoice-Data-Extraction-Using-Machine-Learning
# Invoice Data Extraction

This project extracts key information from invoices using machine learning, handling various formats in English without hardcoded labels.

## Table of Contents

- [Setup](#setup)
- [Data Preprocessing](#data-preprocessing)
- [Model Training](#model-training)
- [Model Optimization](#model-optimization)
- [Model Deployment](#model-deployment)
- [Documentation](#documentation)

## Setup

1. **Clone the Repository:**
   ```sh
   git clone <repository-url>
   cd invoice_data_extraction
2. **Create and Activate a Virtual Environment:**
   python -m venv invoice_env
source invoice_env/bin/activate
3. **Data Preprocessing**
   1. Place your invoice PDFs in the invoices directory.

   2.Run the Data Preprocessing Script:
    This script extracts text from the PDF invoices and preprocesses it.
 python data_preprocessing.py

**Model Training**
1. Annotate Your Data: Create annotated_data.json with entries like:
{
    "text": "Invoice from ABC Ltd. to XYZ Ltd. Total: $1000. VAT: 123456789.",
    "annotations": {
        "sender": "ABC Ltd.",
        "receiver": "XYZ Ltd.",
        "amount": "$1000",
        "vat_number": "123456789"
    }
}
2. **Run the Model Training Script**
 python model_training.py

**python model_training.py**
1. Run the Model Optimization Script:
   python model_optimization.py

**Model Deployment**
1. Ensure the Client Environment Has Necessary Libraries:
   pip install onnx onnxruntime transformers
   
3. Run the Model Deployment Script:
   python model_deployment.py








   

   
