# Weekly Tasks

## Weak 01: General Study

### Yêu cầu 
(13/07/2019)
1. Các vấn đề của chatbot?
   - Đối với chatbot tự học sau khi train: Phải giải quyết được bài toán xác định được các câu trả lời của người dùng có phù hợp.
2. Thành phần chatbot
   Chatbot bao gồm phần chính:
   - Natural Language Understanding
   - Natural Language Generation
   - Knowledge Base
3. Giải quyết như thế nào
4. Ngôn ngữ khác tiếng anh: tiếng trung tham khảo
5. Vấn đề gì cần đi sâu vào
6. Ở VN, chatbot tới đâu rồi? trải nghiệm thử một số cái
7. Chatbot 1 chiều (hỏi-đáp) vs 2 chiều (đối thoại)
8. Ghi document cho nhưng gì đã tìm hiểu.
   
### Phân chia công việc
[Tài liệu tham khảo](https://drive.google.com/drive/folders/11kdkERhyU4W0SZ5-hkRXWW0GxgwF13ci)
1. Tóm tắt abstract của paper (trừ file 3 với file 12)
   - Hùng: file lẻ.
   - Hiếu: file chẵn.
2. Vừa đọc vừa tóm tắt các yêu cầu trên tuỳ vào từng chủ đề của bài báo.
3. Paper là 1 phần, phần chính là trả lời được những câu hỏi ở trên.
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
