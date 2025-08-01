![Sentiment Analyzer UI](screenshot.png)
🧠 SENTIMENT ANALYZER WEB APP USING NATURAL LANGUAGE PROCESSING (NLP)

Leveraging VADER Sentiment Analysis for Real-Time Text Emotion Classification

⚠️ Disclaimer

This project was developed purely for educational purposes. The data used is not sensitive or proprietary, and the app is meant to demonstrate my ability to build and deploy an NLP-powered sentiment classification tool using Python and Flask.

🧾 INTRODUCTION

This project showcases the development of a simple web-based Sentiment Analyzer App using Flask, NLTK’s VADER model, and basic frontend components.
The app analyzes user-submitted text and categorizes it into one of three sentiments:

Positive

Negative

Neutral

It leverages pre-trained lexicon-based sentiment scoring via VADER (Valence Aware Dictionary and sEntiment Reasoner) to quickly assess tone in user messages, making it useful for social media monitoring, customer feedback analysis, and more.

🧪 TECH STACK

Frontend: HTML, CSS (Bootstrap)

Backend: Python (Flask)

NLP Engine: NLTK VADER

Environment: PyCharm / VSCode (local), compatible with Streamlit/Heroku/Fly.io for deployment

🔬 METHODOLOGY

1️⃣ Project Setup and Dependencies

Installed necessary libraries (flask, nltk, etc.)

Downloaded VADER lexicon using nltk.download('vader_lexicon')

from nltk.sentiment.vader import SentimentIntensityAnalyzer
analyzer = SentimentIntensityAnalyzer()

2️⃣ Application Flow

User inputs text via an HTML form

The input is processed using the VADER Sentiment Analyzer

The compound score determines the overall sentiment category

The result is returned and rendered dynamically in the UI

3️⃣ Backend Logic (Flask)
python

@app.route('/', methods=['GET', 'POST'])

def index():

    if request.method == 'POST':
        text = request.form['text']
        score = analyzer.polarity_scores(text)
        if score['compound'] >= 0.05:
            sentiment = "Positive"
        elif score['compound'] <= -0.05:
            sentiment = "Negative"
        else:
            sentiment = "Neutral"
        return render_template('index.html', sentiment=sentiment, score=score)
4️⃣ Frontend UI

Simple and clean HTML form using Bootstrap:

Text input box

Submit button

Result section dynamically renders sentiment classification

📊 SAMPLE OUTPUTS

Input Text	Detected Sentiment	Score

"I love this product!"	Positive	0.76

"This is the worst experience ever."	Negative	-0.85

"She is going to the market today."	Neutral	0.01

🎯 RESULT AND IMPACT

The app performs real-time sentiment analysis with high speed and accuracy due to the light-weight VADER model.

Its simplicity allows for:

Educational use in NLP basics

Real-world application in feedback analysis

Extension into advanced NLP pipelines or social listening dashboards

🚀 POSSIBLE EXTENSIONS
🔁 Add language translation support for multilingual input

📈 Visualize sentiment trends from uploaded CSV files or APIs

🤖 Integrate with social media APIs to analyze tweets or YouTube comments

📌 INSTALLATION
Clone the repository:

git clone https://github.com/VictorSylva/sentiment-analyzer.git
cd sentiment-analyzer
Create virtual environment (optional but recommended):

python -m venv venv

source venv/bin/activate  # For Windows: venv\Scripts\activate

Install dependencies:

pip install -r requirements.txt

Run the app:

python main.py

🧠 CONCLUSION
This project demonstrates the practical application of Natural Language Processing in sentiment analysis. Using Python and open-source libraries like NLTK and Flask, we can build efficient, real-time tools to understand how people feel—critical for businesses, researchers, and developers alike.

🙏 THANK YOU
If you find this helpful or want to collaborate, feel free to reach out or fork the repo and build on it!
You can also 🔗 Connect with me on [LinkedIn](https://www.linkedin.com/in/mbasiti-sylvanus-2119ba222/)