# Text Summarizer for Tamil and English

This repository contains a Django web application that serves as a text summarizer for both Tamil and English languages. The project is designed to provide users with a convenient way to summarize textual content efficiently.

## Project Overview

### 1. User Interface

The user interface was designed to be simple and intuitive, with a clear separation of the input and output pages. The text box on the input page is prominent and easily accessible, allowing the user to quickly enter the text they wish to summarize. Once the user submits the text, they are immediately directed to the output page, where the summary is displayed. The output page has a clean and minimalistic design, with the summary presented in a clear and concise manner. The summary is easy to read and contains only the most important information from the original text. Additionally, the application supports two languages, English and Tamil, with the language detection happening automatically. Overall, the user interface was designed to provide a smooth and efficient experience for the user.

### 2. Text Preprocessing

The stop words were removed to ensure that the summarization process is focused on the relevant and meaningful words in the text. After removing the stop words, the text is tokenized into individual words or sentences, depending on the language of the text. The frequency of each word is then calculated and stored in a frequency table. This frequency table is used to determine the importance of each sentence in the text. Sentences with a higher frequency of important words are given higher scores and are considered to be more important than sentences with lower scores. The summary is generated using the sentences with scores that are higher than a certain threshold. This threshold is calculated as a percentage of the average score of all the sentences in the text. This ensures that the summary is a concise representation of the most important information in the original text.

### 3. Sentence Scoring

The scoring of sentences is carried out by calculating the frequency of each word in the input text. The frequency table is constructed for the preprocessed text. Each sentence in the preprocessed text is then scored based on the sum of the frequency of each word in that sentence. The higher the score of a sentence, the more important it is considered to be, and therefore, it has a higher chance of being included in the summary. This method of scoring the sentences is efficient in extracting the most significant sentences from the input text, and it allows for the creation of a summary that accurately represents the main ideas of the text. The summarizer has been tested on various texts and has shown to be effective in creating accurate summaries.

### 4. Sentence Selection

After scoring each sentence, the application selects the sentences with the highest scores for inclusion in the summary. To ensure that the summary contains relevant sentences, a threshold is set by calculating the average score of all the sentences. Any sentence with a score greater than 1.2 times the average score is included in the summary. This approach helps to ensure that the summary contains the most important sentences and eliminates sentences that are less relevant. Additionally, the threshold can be adjusted based on the length and complexity of the input text, allowing the application to generate summaries that are appropriate for different types of texts.

### 5. Translation

For the English input text, the summary is directly displayed on the summary page. However, for Tamil input text, the summary is translated to Tamil using the Google Translate API. The translation process is initiated by sending the summary text to the API, and the translated summary is received as a response. The translated summary is then displayed on the summary page. To handle different types of input text, the application was designed to have separate functionalities for English and Tamil input. The scoring system and summarization algorithm were designed to work for both languages. However, the translation process was added specifically to handle Tamil input text, as it allows for a wider range of users to benefit from the application.

### 6. Deployment

To deploy the Django web application, Apache and mod_wsgi were used as the web server and application server respectively. The server was configured to handle multiple requests at the same time to ensure optimal performance even during peak traffic. To test the application's scalability and performance, load testing was conducted using various tools such as Apache JMeter and Siege. The results showed that the application could handle a significant number of concurrent requests without any major issues. Furthermore, the application was optimized for faster response times by implementing caching and minimizing the number of database queries. This helped reduce the load on the server and ensured a smoother user experience.

## Installation

To install and run the Text Summarizer project locally, follow these steps:

1. Clone the repository to your local machine:

   ```bash
   git clone https://github.com/your-username/text-summarizer.git
2. Navigate to the project directory:

   ```bash
   cd text-summarizer
3. Create a virtual environment (recommended):

   ```bash
   python -m venv venv
4. Activate the virtual environment:

   - On Windows:
     ```bash
     venv\Scripts\activate
     
   - On macOS and Linux:
     ```bash
     source venv/bin/activate
     
6. Install project dependencies:

   ```bash
   pip install -r requirements.txt
