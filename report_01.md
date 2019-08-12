# Week 01: General Study
Mon, 29/07/2019 - 05/08/2019
## I. Chatbot Operation
![giai_doan_chatbot](https://lh6.googleusercontent.com/qL0g26dUhd5Gk5GA1WDT1VUaNpP8K3MbenJjR3t0eQDeViQ9BLAaqby2KDtCZIkt3X9xuGKxxe1LvWwXl8XQr-K-aUWM7atphZFXFjNaoanTJtSlgPYuqUYtad2a7wB7qkGuZJnlmjy2WdkAmg)

Example
![example](https://miro.medium.com/max/700/1*-f1gD5s1e1P2aNpeFOY9HA.png)

Một vài task mà 1 chatbot phải làm:
- Hiểu message: intent + parameter
- Xử lý (intent + parameter) -> next action (ask subsequent question or delivered a response)
- Maintain the Context in a single session. (its state with all parameters)
  
## II. Problems
1. How to get intents & entities
2. Context: what & how to save
3. How to response

## III. Proposed Methodology
1. Get intents
   Using intent classification
   > DATA: đưa vào bao nhiêu class intents, rồi bỏ vào mạng deep learning.

   Xử lý dữ liệu: lemmatize, stemming, stopword removal.

2. Get entities
    Build entity recognizer with NLTK & SpaCy
    (person, location, date)

3. Context
   Save parameters + entites + intents
   
## IV. Experiences
1. Semantic Similarity Chatbot 
   (belong to Information Retrieval Chatbot)  
   [link](https://colab.research.google.com/drive/19MM2mDwB_-y2PuBcJnDoTL4502fLK2hs)
   - data: cornell-movie
   - Biểu diễn word bằng vector (300 dimensions)
   - Câu => Vector(300 dimension) (mean all words)
   - Request => Vector => Nearest Turn (compare 2 vector) => Response

2. Chatbot using LSTM-RNN model  
   [link](https://colab.research.google.com/drive/1aDTCUj4FCFagilnXrhxbfVIDPMiZYxI7)
    Xây dựng mạng LSTM-RNN sử dụng Tensorflow.
