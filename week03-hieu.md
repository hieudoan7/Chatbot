# Week 03: 
## I. Measure
[Attention-Based RNN Models for JID & Slot Filling](https://arxiv.org/pdf/1609.01454v1.pdf)
F1 Score:
$$ \frac{2}{F1} = \frac{1}{Precision} + \frac{1}{Recall} $$
$$ \Rightarrow F1 = \frac{2*Precision*Recall}{Precision + Recall}$$
Trong đó:
$$Precision = \frac{True Positive}{True Positive + False Positive}$$
$$Recall = \frac{True Positive}{True Positive + False Negative}$$

### Corpus-based Evaluation
- BLEU score ([Papineni at el .2012](https://www.aclweb.org/anthology/P02-1040))
Đưa ra 1 số câu reference (người dịch cung cấp), vd 4 câu
Từ những câu candidate. Đếm số từ của câu ứng viên xuất hiện (exhautist) trong 4 câu reference/length(candidate)
> BLEU is useful in translation, is a poor fit for dialogue models.
- Entity Matching Rate
  
- Objective Task Success Rate (Su at el . 2015)

### Human-evaluation
Amazon Mechanical Turk.

- Adversarial Evaluation ([paper](https://arxiv.org/pdf/1701.08198.pdf))
    + Generator (RNN-model) tao ra machine reply
    + Discriminator: phân biệt câu người vs câu máy
    + Đánh giá dựa vào câu trả lời của chatbot càng gần người càng tốt 
