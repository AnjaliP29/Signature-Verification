# Signature Verification Deep Learning Project

A signature verification tool using deep learning techniques to determine the authenticity of signatures by comparing them to reference signatures. This tool can be particularly useful in banks for verifying signatures on cheques or demand drafts.

## 🎯 Project Overview

This project utilizes a **Multilayered Perceptron (MLP)**, a type of artificial neural network, to learn patterns and features necessary for accurate signature verification. The system extracts 9 key features from signature images and uses deep learning to classify signatures as genuine or forged.

## ✨ Features

- **Signature Similarity Score**: Generates a similarity score (0-1) indicating how closely the provided signature matches the reference signature
- **Deep Learning Classification**: Uses a neural network with multiple hidden layers to classify signatures
- **Feature Extraction**: Automatically extracts 9 key features from signature images:
  - Ratio (ink density)
  - Centroid (X, Y coordinates)
  - Eccentricity & Solidity (shape characteristics)
  - Skewness & Kurtosis (statistical distributions)
- **Web Interface**: User-friendly Flask web application with authentication
- **Banking Applications**: Designed for verifying signatures on cheques or demand drafts

## 🛠️ Technologies Used

- **Python 3.x**: Core programming language
- **Flask**: Web framework for the user interface
- **TensorFlow & Keras**: Deep learning framework
- **OpenCV & scikit-image**: Image processing
- **NumPy, Pandas, SciPy**: Data processing and analysis
- **Matplotlib**: Visualization

## 📋 Prerequisites

- Python 3.7 or higher
- pip (Python package installer)

## 🚀 Installation

1. **Clone the repository**
   ```bash
   git clone <your-repository-url>
   cd SignVeri-clean
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   
   # On Windows:
   venv\Scripts\activate
   
   # On macOS/Linux:
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## 💻 Usage

1. **Start the Flask application**
   ```bash
   python index.py
   ```

2. **Access the web interface**
   - Open your browser and go to: `http://localhost:5000`
   - Login credentials:
     - Username: `admin`
     - Password: `password`

3. **Verify a signature**
   - Enter the Person ID (e.g., `001` for person 1)
   - Upload a signature image (PNG format)
   - Click "Submit"
   - View the results: Genuine/Forged status and Similarity Score

## 📁 Project Structure

```
SignVeri-clean/
│
├── index.py                 # Flask web application
├── signprec.py             # Core ML model and feature extraction
├── requirements.txt        # Python dependencies
├── README.md              # This file
│
├── Features/              # Training and testing CSV files
│   ├── Training/         # Training feature datasets
│   └── Testing/          # Testing feature datasets
│
├── TestFeatures/         # Temporary test feature extraction
│
├── real/                 # Genuine signature images
├── forged/              # Forged signature images
│
├── templates/           # HTML templates
│   ├── index.html
│   ├── Result.html
│   ├── aboutteam.html
│   ├── documentation.html
│   └── other.html
│
└── static/             # Static files (images, PDFs)
    ├── logo.jpg
    └── research_paper.pdf
```

## 🔧 How It Works

1. **Image Preprocessing**
   - Convert RGB image to grayscale
   - Convert grayscale to binary
   - Crop to signature boundaries

2. **Feature Extraction**
   - Extract 9 features from the preprocessed image
   - Save features to CSV format

3. **Model Training/Evaluation**
   - Load training data for the specified person ID
   - Train a neural network on genuine vs forged signatures
   - Predict on the uploaded signature

4. **Similarity Calculation**
   - Calculate Euclidean distance between test features and training data
   - Generate similarity score (higher = more similar)

5. **Result Display**
   - Classify as Genuine or Forged
   - Display similarity score

## 📊 Model Architecture

- **Input Layer**: 9 features
- **Hidden Layer 1**: 7 neurons (tanh activation)
- **Hidden Layer 2**: 10 neurons
- **Hidden Layer 3**: 30 neurons
- **Output Layer**: 2 classes (Genuine/Forged)

## 🔒 Security

- Basic authentication enabled by default
- Change credentials in `index.py` for production use

## 📝 Notes

- The model requires training data for each person ID (001-012)
- Signature images should be in PNG format
- The system is trained on 12 different people's signatures
- Training data uses first 3 images, testing uses images 3-5

## 🤝 Contributing

Feel free to submit issues and enhancement requests!

## 📄 License

This project is open source and available for educational purposes.

## 🙏 Acknowledgments

- Open-source community for providing tools and libraries
- Team members for their contributions and support

---

**Note**: This project is for educational purposes. For production banking applications, additional security measures and compliance requirements should be implemented.

