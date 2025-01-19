# AI-Powered News Recommendation System

## Project Overview

The **AI-Powered News Recommendation System** is designed to provide personalized news recommendations to users. By leveraging user and news article features, the system predicts the relevance of articles to users and recommends the top articles based on their preferences. The project integrates machine learning and natural language processing (NLP) techniques to analyze news titles and classify them into categories such as "Sports," "Medical," and "Tech."

## Key Functionalities

1. **Data Collection and Preprocessing**:
   - Fetch user and news article data from APIs (e.g., JSONPlaceholder).
   - Classify news articles into predefined categories using Hugging Face's zero-shot classification pipeline.
   - Scale user features, article features, and interaction scores for compatibility with the neural network.

2. **Neural Network Training**:
   - Train a neural network with two sub-models:
     - A user-specific model to encode user preferences.
     - An article-specific model to encode article features.
   - Compute interaction scores using the dot product of user and article embeddings.

3. **Recommendations**:
   - Predict interaction scores for all articles for a given user.
   - Recommend the top N articles with the highest predicted scores.

4. **Evaluation**:
   - Evaluate the model's performance using test data.
   - Analyze the recommendations for accuracy and relevance.

## How to Use It

### Prerequisites

- Python 3.8+
- Required libraries:
  - `tensorflow`
  - `transformers`
  - `requests`
  - `pandas`
  - `numpy`
  - `scikit-learn`

Install dependencies using pip:
```bash
pip install tensorflow transformers requests pandas numpy scikit-learn
```

### Steps to Run the Project

1. **Clone the Repository**:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. **Fetch and Preprocess Data**:
   - The script automatically fetches user and article data from JSONPlaceholder APIs.
   - It preprocesses the data, classifies articles into categories, and scales the features.

3. **Train the Model**:
   - Run the script to train the neural network:
     ```bash
     python train_model.py
     ```
   - The model will use user and article features to learn interaction scores.

4. **Get Recommendations**:
   - Use the provided function `recommend_top_n_articles(user_id, n)` to get the top N recommendations for a user.
   - Example:
     ```python
     top_articles = recommend_top_n_articles(user_id=0, n=5)
     print("Top articles for user 0:", top_articles)
     ```

5. **Evaluate the Model**:
   - The script includes evaluation metrics to test the model's performance on test data.

### Example Output

- **Recommended Articles**:
  - For user 0, the top 5 articles could be:
    - "Breaking News: Tech Giant Acquires Startup"
    - "Sports Highlights of the Week"
    - "Medical Breakthrough: New Treatment Announced"
    - "Top Gadgets to Watch in 2025"
    - "Fitness Trends for a Healthier Life"

### Notes
- You can customize the categories in the `candidate_labels` variable to align with your requirements.
- The neural network architecture and training parameters can be adjusted to improve recommendation quality.

Feel free to explore and modify the project to suit your needs!

