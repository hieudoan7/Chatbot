# Weekly Tasks

## Weak 01: General Study

### Yêu cầu 
(13/07/2019)
1. Các vấn đề của chatbot?
2. Thành phần chatbot
3. Giải quyết như thế nào
4. Ngôn ngữ khác tiếng anh: tiếng trung tham khảo
5. Vấn đề gì cần đi sâu vào
6. Ở VN, chatbot tới đâu rồi? trải nghiệm thử một số cái
7. Chatbot 1 chiều (hỏi-đáp) vs 2 chiều (đối thoại)
8. Ghi document cho nhưng gì đã tìm hiểu.
-------------------------------------------------
## TÓM TẮT CÁC BÀI PAPER
### Learning from Dialogue after Deployment: Feed Yourself, Chatbot!
Chatbot có khả năng tự thu thập dữ liệu train từ các cuộc đối thoại với người dùng.  
   - Đánh giá mức độ thoả mãn của câu trả lời. Khi cuộc trò chuyện diễn ra suôn sẻ, phản hồi của người dùng trở thành dữ liệu train mới.  
    - Khi chatbot mắc lỗi, nó sẽ yêu cầu phản hồi từ người dùng. Dự đoán phản hồi từ người dùng sẽ cải thiện khả năng đàm thoại của chatbot.  
Một số vấn đề được đề cập đến:  
    - Dunning-Kruger: Mô hình không tốt cũng sẽ không biết được điều nó làm là không tốt.
### Chatti: A Conversational Chatbot Platform
Bài báo chủ yếu nói về ứng dụng chatti. Kiến trúc của ứng dụng được chia như sau:  
   - Dialog Management (DM): dùng để quản lý nội dung đối thoại.  
    - Action Planning (AP): đưa ra kế hoạch xử lý.  
    - Natural Language Understanding (NLU): gom ý chính của cuộc đối thoại, có nhiều phương pháp như (Pattern-base, statistical, deep neural (LSTM, CNN,...)).  
    - Natural Language Generation (NLG): sinh ra phản hồi.  
    - Knowledge Base (KB) lưu trữ và quản lý dữ liệu.  
  
[Chatti](./assets/imgs/Chatti.png)

### Did I Say Something Wrong? Towards a Safe Collaborative Chatbot
Phát hiện ra được người dùng những từ ngữ xấu khi dạy chatbot và các biện pháp hạn chế trong tương lai.

### Understanding User Interactions with a Chatbot: A Self-determination Theory Approach
Bài này chủ yếu nói về UI/UX trong NLP có tác động như thế nào với trải nghiệm người dùng. 

### Ứng dụng thuật toán học có giám sát MULTI-CLASS SVM trong xây dựng hệ thống chatbot hỏi đáp tiếng việt
Xây dựng hệ thống chatbot đóng (Vietnam airline chatbot) với thuật toán học có giám sát Multi-Class SVM. Sử dụng kỹ thuật túi từ BoW (Bag of Words) và phương pháp túi từ TF-IDF(Term Frequency - Inverse Document Frequency) 

------------------------
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

----------------------------------
## Week 02: Read Papers 
Mon, 05/08/2019
Đọc tất cả papers liên quan chatbot: abstract, experiment
- Bài toán
- Hướng giải quyết
- Hiệu quả: dataset, so sánh (them), độ đo
- chinese chatbot
- Liệu  apply tiếng việt

Ghi note mind map: Vấn đề bài báo đó là gì => Người ta giải quyết như thế nào: (chỉ cần ghi tên thuật toán và để link vào, ko sa đà chi tiết).


