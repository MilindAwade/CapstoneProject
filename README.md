# Sentiment-Based Product Recommendation System

URL : https://tinyurl.com/437rv6e6

This repository contains a **Sentiment-Based Product Recommendation System**, which combines **Collaborative Filtering** techniques and **Sentiment Analysis** to recommend products based on user preferences and sentiment from reviews. The system includes a Flask web application deployed on **AWS Lightsail** for live interaction.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Technologies Used](#technologies-used)
- [Setup Instructions](#setup-instructions)
- [Model Details](#model-details)
- [Deployment](#deployment)
- [File Structure](#file-structure)
- [Future Improvements](#future-improvements)
- [License](#license)

URL : https://.../

---

## Project Overview

E-commerce platforms thrive on personalized recommendations. To stay competitive, this project focuses on improving recommendations by leveraging customer reviews and ratings. It integrates **Sentiment Analysis** with **User-User Collaborative Filtering** to offer highly personalized and relevant product suggestions.

The system allows users to:
- Get product recommendations based on similar users.
- Filter recommendations based on positive sentiment analysis of reviews.

---

## Key Features

1. **User-User Collaborative Filtering**: Recommends products based on similarities in user preferences.
2. **Sentiment Filtering**: Prioritizes products with positive sentiment reviews.
3. **Professional Web Interface**: Modern, responsive design with blue-grey color scheme and smooth animations.
4. **Interactive User Experience**: Enhanced UI with loading states, hover effects, and keyboard navigation.
5. **Flask Web Application**: Provides an intuitive interface for users to interact with the recommendation system.
6. **Cloud Deployment**: The application is hosted on **AWS Lightsail** for seamless accessibility.
7. **Reusable Models**: Trained models and preprocessing components are stored as pickle files for easy deployment.

---

## Technologies Used

- **Python 3.7+**: Core programming language.
- **Flask**: Web framework for building the application.
- **Scikit-learn**: For building and evaluating machine learning models.
- **Pandas** and **NumPy**: For data manipulation and analysis.
- **Bootstrap 5**: For responsive UI components and layout.
- **CSS3**: Custom styling with modern animations and transitions.
- **JavaScript**: Enhanced user interactions and dynamic content.
- **Font Awesome**: For professional icons and visual elements.
- **AWS Lightsail**: Cloud platform for deployment.
- **Pickle**: For saving trained models and preprocessing objects.

---

## Setup Instructions

### Prerequisites

1. Install **Python 3.7+**.
2. Install **Git** to clone the repository.
3. Ensure you have a AWS account if deploying the app.

### Step 1: Clone the repository

```bash
git clone https://github.com/your-username/sentiment-based-recommendations.git
cd sentiment-based-recommendations
```

### Step 2: Install dependencies

Create and activate a virtual environment:

```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

### Step 3: Load models and data

Ensure the following pickle files are in the `pickle_file` directory:
- `model.pkl`: Trained sentiment analysis model.
- `user_final_rating.pkl`: User-user collaborative filtering model.
- `count_vector.pkl`: Count vectorizer for text data.
- `tfidf_transformer.pkl`: TF-IDF transformer for text features.

Ensure the dataset `sample30.csv` is present for testing.

### Step 4: Run the Flask application

Start the Flask server:

```bash
python app.py
```

Access the application at `http://127.0.0.1:5000/`.

---

## Model Details

### 1. Sentiment Analysis

- **Input**: Preprocessed customer reviews.
- **Model**: Logistic Regression (trained with TF-IDF features).
- **Output**: Sentiment labels (Positive, Negative, Neutral).
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1-Score.

### 2. User-User Collaborative Filtering

- **Input**: User-product rating matrix.
- **Method**: Cosine similarity between users.
- **Output**: Predicted ratings for unseen products.
- **Evaluation Metric**: RMSE.

### Integration

The final recommendation system combines predictions from collaborative filtering and filters the results using sentiment analysis. Products with high predicted ratings and positive sentiments are prioritized.

---

## Deployment

### Local Deployment

Run the Flask app locally by following the setup instructions above.

### AWS Lightsail Deployment

Steps to deploy a Python Flask application on AWS Lightsail:

---

### **1. Set Up a Droplet**
- Log in to your [AWS Lightsail account](https://www.AWS.amazon.com/).
- Create a new droplet with a preferred Linux distribution (e.g., Ubuntu 22.04).
- Choose a size and data center region, then launch the droplet.
- Connect to your lightsail using SSH:
  ```bash
  ssh ubuntu@lightsail_ip
  ```

---

### **2. Install Required Software**
- Update the system and install essential packages:
  ```bash
  sudo apt update && sudo apt upgrade -y
  sudo apt install python3 python3-pip python3-venv nginx git -y
  ```
- Install and configure Gunicorn:
  ```bash
  pip3 install gunicorn
  ```

---

### **3. Upload and Configure Your Flask App**
- Clone or upload your Flask app to the droplet:
  ```bash
  git clone https://github.com/your-repo.git /var/www/your-app
  cd /var/www/your-app
  ```
- Set up a Python virtual environment:
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  pip install -r requirements.txt
  ```
- Test the app with Gunicorn:
  ```bash
  gunicorn --bind 0.0.0.0:8000 app:app
  ```

---

## File Structure

```
sentiment-based-recommendations/
├── app.py                    # Flask application
├── model.py                  # Core recommendation system code
├── pickle_file/              # Directory for model and vectorizer pickle files
│   ├── model.pkl
│   ├── user_final_rating.pkl
│   ├── count_vector.pkl
│   ├── tfidf_transformer.pkl
├── static/                   # Static assets directory
│   └── css/
│       └── style.css         # Custom CSS 
├── templates/                # Flask HTML templates
│   └── index.html            # Main application page with modern UI
├── requirements.txt          # Python dependencies
├── README.md                 # Project documentation (this file)
└── sample30.csv              # Sample dataset for testing
```

---

## Future Improvements

1. **Hybrid Recommendation System**: Combine collaborative filtering with content-based filtering for better accuracy.
2. **Advanced Sentiment Analysis**: Use deep learning models (e.g., BERT) for improved sentiment prediction.
3. **Scalability**: Use distributed systems like Spark for large-scale data.
4. **UI Enhancements**: Improve the user interface for a seamless experience.
5. **Additional Metrics**: Incorporate diversity and novelty metrics into the recommendations.


## Conclusion

This sentiment-based product recommendation system enhances the user experience by combining traditional collaborative filtering with sentiment analysis. By offering personalized and sentiment-aware recommendations, it improves customer satisfaction and engagement. The system is accessible through a Flask application, with live deployment on AWS Lightsail.

