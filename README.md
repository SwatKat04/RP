# Expressive-Speech-Synthesis

Given a paragraph, the implemented LSTM model classifies each sentence of the paragraph into one of the following six basic emotions :- Fear, Disgust, Anger, Joy, Sadness and Surprise.
Further the model classifies each emotion under 4 levels or degrees[0, 0.25, 0.50, 1], higher the degree greater is emphasis on expressiveness of the speech. Then expressive speech for each of the sentence with the classified empotion and degree is synthezised using the IBM Watson TTS Engine.

## Training DataSet

Curated from **SemEval 2007** and **ISEAR** for optimal results.

## Dependencies
* ### ibm_cloud_sdk_core.authenticators
* ### ibm_watson
* ### keras
* ### nltk
* ### numpy
* ### pandas
* ### tensorflow

## Usage

1 Clone this Project Locally
  ```bash
  git clone https://github.com/manugeorge04/Expressive-Speech-Synthesis.git
  ```
2 Set-Up IBM Watson
  Create a free account to access [IBM - Watson](https://www.ibm.com/in-en/cloud/watson-text-to-speech)
  Obtain the authenticator key and enter it in the notebook
  ```python
    authenticator = IAMAuthenticator('API_KEY') #paste your auth key here
  ```  

3 Run the Jupyter Notebook

4 To predict emotion of a given sentence
```python
  pred("I scored a centum on my math paper") #returns 'joy'
  pred("I fell down the stairs today") #returns 'sadness'
```

5 To predict the degree of emotion of a given sentence
```python
  pred_degree("I am happy") #returns ["I am happy",0.25]
  pred_degree("I very happy") #returns ["I very happy",0.5]
```
 
6 To obtain expressive speech
  ```python
  para = "I was scared that I will miss my flight. I was annoyed with the driver for coming late and I yelled at him. I am happy we reached on time. I feel sad for yelling at my driver."
  audioFileName = "ExpressiveSpeech"
  getVoice(para,audioFileName)
  ```
