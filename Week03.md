# Week 03: Evaluation

## Requiment:
- Các vấn đề cần xem lại:
  - Consistent: cần làm rõ.
  - Nếu train 2 tập dữ liệu khác nhau có khác gì so với từng tập dữ liệu riêng biệt. (Khách sạn, nhà hàng)
  - Tối thiểu dataset bao nhiêu để làm mô hình end-to-end.
- Thuật toán, Độ đo => đạt được kết quả như thế nào => chọn hướng mới, kết quả ra sao?
- Dataset: có đặc điểm gì (tiếng anh, việt, trung), kích thước, dung lượng, lấy được không?
- Hệ thống chatbot có thương mại hoá:
  - Dùng luôn hay sao?
  - Miễn phí hay có phí để xài
  - Chất lượng: cơ chế đưa lên như thế nào, làm sao đưa lên, API.
  - Open-source hay không.
  - Chạy thử trước với dataset của mình như thế nào. (Tiếng việt hay tiếng anh)
- Xác định được hướng đi (có thể nhiều hướng).

## Evalution In NLP:

User satisfaction rating (Averagerd over all questions below)

| Property         | Explain                                                     |
| ---------------- | ----------------------------------------------------------- |
| TTS Performance  | Was the system easy to understand ?                         |
| ASR Performance  | Did the system understand what you said?                    |
| Task Ease        | Was it easy to find the message/flight/train you wanted?    |
| Interaction Pace | Was the pace of interaction with the system appropriate?    |
| User Expertise   | Did you know what you could say at each point?              |
| System Response  | How often was the system sluggish and slow to reply to you? |

1. Task completion success:
   - Task success can be measured by evaluating the correctness of the total solution.
   - Eg:
     - Frame-base architecture:
       - percentage of slots that were filled with the correct values or the percentage of subtasks
that were completed.

2. Efficiency cost:
    - Efficiency costs are measures of the system’s efficiency at helping
users.
    - Eg:
      -  the total elapsed time for the dialog in seconds.
      -  the number of total turns or of system turns.
      -  the total number of queries.
  
3. Quality cost: 
   - Measure other aspects of the interactions that affect users' perception of the system.
   - Eg:
     - Number of times the ASR system failed to return any sentence
     - Number of ASR rejection prompts
     - Number of times the user had to interupt the system or time-out prommpts played when the user didn't respond quickly enough.
      
4. Slot error rate:
    - How well the system understood and responded to the user.
    - Eg:
      - System's questions, answers, error messages.
      - Correctness of each question, answer, error message.

## Evalution in Chatbot
1. Slot-filling evaluation:
   
    - [Attention-Based RNN Models for JID & Slot Filling](https://arxiv.org/pdf/1609.01454v1.pdf)
    
    - F1 Score:
    $$ \frac{2}{F1} = \frac{1}{Precision} + \frac{1}{Recall} $$
    $$ \Rightarrow F1 = \frac{2*Precision*Recall}{Precision + Recall}$$
    
    - Trong đó:
    $$Precision = \frac{True Positive}{True Positive + False Positive}$$
    $$Recall = \frac{True Positive}{True Positive + False Negative}$$
2. BLEU:
   
    - BLEU score ([Papineni at el .2012](https://www.aclweb.org/anthology/P02-1040))
    Đưa ra 1 số câu reference (người dịch cung cấp), vd 4 câu
    Từ những câu candidate. Đếm số từ của câu ứng viên xuất hiện (exhautist) trong 4 câu reference/length(candidate)
    > BLEU is useful in translation, is a poor fit for dialogue models.

    - Entity Matching Rate
    - Objective Task Success Rate (Su at el . 2015)
3. [ADEM](https://aclweb.org/anthology/P17-1103):
	- learns to pre-dict human-like scores to input responses,using a new dataset of human responsescores.
	- predictions correlate significantly, and at alevel much higher than word-overlap met-rics such as BLEU.
4. Adversarial Evaluation ([paper](https://arxiv.org/pdf/1701.08198.pdf))
    - Generator (RNN-model) tao ra machine reply
    - Discriminator: phân biệt câu người vs câu máy
    - Đánh giá dựa vào câu trả lời của chatbot càng gần người càng tốt 