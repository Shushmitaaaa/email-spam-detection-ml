# 📩 **_Email/SMS Spam Classifier 🔍🚫_**  

## 🧠 **_About the Project_**  
A Machine Learning-powered web application that classifies your messages as **Spam** or **Not Spam** in real-time. Built using **Python**, **NLTK**, **Scikit-learn**, and deployed with **Streamlit** on **Render**.

---

## 📌 **_Step-by-Step Workflow_**

### **_Step 1: Finding the Dataset_**  
I began by finding a well-structured dataset (from Kaggle) containing labeled SMS messages as either *ham* (not spam) or *spam*.  

📂 Source: [UCI SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)

---

### **_Step 2: Cleaning the Dataset_**  
- Checked for null values and inconsistencies  
- Removed duplicates  

---

### **_Step 3: EDA (Exploratory Data Analysis)_**  
Visualized patterns and insights:
- **Ham messages** tend to be longer in words, characters, and sentence count.
- **Spam messages** use certain repeated keywords and have a different tone.
- Analyzed most commonly used words using word clouds.
- Identified **outliers** to improve model reliability.

*This step was crucial in understanding the data’s distribution and selecting the right preprocessing techniques.*

---

### **_Step 4: Text Preprocessing_**  
Transforming text into a digestible format for ML:
1. Convert to **lowercase**
2. **Tokenization** – splitting into individual words  
3. Remove **punctuation & stopwords** (since they add noise, not value)  
4. **Stemming** – converting words to their root forms (e.g., “loved” → “love”)  

🧠 Handled via `NLTK`:
```python
nltk.download('punkt')
nltk.download('stopwords')
```

---

### **_Step 5: Vectorization_**  
Used **TF-IDF Vectorizer**:
- Converts text into numeric features
- Identifies **most important words** in context (not just frequently used ones)
- Selected top **3000 features** for maximum performance

> TF-IDF helps highlight the truly meaningful words — not just the loudest. This converts textual data into numerical vector features since the model only understands numbers.

---

### **_Step 6: Model Building_**  
- Split the dataset into **Train** and **Test** data  
- Chose **Multinomial Naive Bayes (MNB)** for classification:
  - Best suited for **text-based** problems  
  - Fast, efficient, and performed exceptionally well  
  - Model performance is determined using metrics like **accuracy**, **precision**

---

### **_Step 7: Model Saving_**  
Used `pickle` to store:
- Trained ML Model (`model.pkl`)
- Fitted Vectorizer (`vectorizer.pkl`)  

```bash
import pickle
pickle.dump(model, open('model.pkl', 'wb'))
pickle.dump(tfidf, open('vectorizer.pkl', 'wb'))
```

---

### **_Step 8: Web App with Streamlit_**  
Created a sleek UI to interact with the classifier:
```bash
streamlit run app.py
```

Users can input any message and see whether it’s spam or not — with a stylish red/green display for clarity.

---

### **_Step 9: Deployment on Render_**  
Deployed using [Render](https://render.com):

- Created `requirements.txt`
- Pushed code to GitHub
- Set up Python environment in Render dashboard
- Deployed using `app.py` as entry point

🚀 [🔗 Try the Live App](https://email-spam-detection-ml-11.onrender.com)

---

## **_Technologies Used_**
- Python  
- NLTK (Natural Language Toolkit)  
- Scikit-learn  
- Streamlit  
- Pandas, Matplotlib, Seaborn  
- Render (for deployment)

---

## **_Contributions_**

Contributions to this project are welcome.  
If you find any issues or have any suggestions for improvement, please open an issue or a pull request on this repository.

---
