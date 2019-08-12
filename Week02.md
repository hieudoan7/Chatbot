# Week 02: Read Papers 
## Requirement
Đọc tất cả papers liên quan chatbot: abstract, experiment
- Bài toán
- Hướng giải quyết
- Hiệu quả: dataset, so sánh (them), độ đo
- chinese chatbot
- Liệu  apply tiếng việt
Ghi note mind map: Vấn đề bài báo đó là gì => Người ta giải quyết như thế nào: (chỉ cần ghi tên thuật toán và để link vào, ko sa đà chi tiết).
## Abstract's paper summary:
### Hùng
1. Dialogue act classification (Phân loại intent của người nói)
  - Dataset:  
    - Switchboard corpus: 
      - switchboard-1 corpus: Phone dialogue.
      - Switchboard Dialogue Act Corpus: An improvement of switchboard-1 corpus with tag.
      - MRDA corpus: Meeting dialogue of 53 people.
  - Paper:
    - [Dialogue Act Sequence Labeling using Hierarchical encoder with CRF](https://arxiv.org/abs/1711.05568)
      - Assigning label tag for each word. Building hierarchical RNN with LSTM and conditional random field (CRF) to classify utterance.
      - Level: word -> utterance -> dialogue.
    - [Dialogue Act Recognition via CRF -Attentive Structured Network](https://arxiv.org/abs/1709.04250)
      - Expand CRF with hierarchical sematic inference with model dataset. After that, transforming attention network to linear-chain CRF with input is both utterance and dialogue.
    - [A Context-based Approach for Dialogue Act Recognition using Simple Recurrent Neural Networks](https://arxiv.org/abs/1805.06280)
      - Novel context-based learning using to classify down to character-level.
2. Dialogue state tracking
  - Dataset:
    - DSTC2: Finding restaurant.
    - Wizard-of-Oz: Finding restaurant with acuracy.
    - MultiWOZ: human-human dialogue with tag.
  - Paper:
    - [Global-Locally Self-Attentive Dialogue State Tracker](https://arxiv.org/abs/1805.09655)
      - Giobal-Locally Self-Attentive Dialogue State Tracker (GLAD) use modules global-local to learn utterance. 
      - Global modules share information between diffirent.
      - Local modules learn specify dialogue type.
    - [Dialogue Learning with Human Teaching and Feedback in End-to-End Trainable Task-Oriented Dialogue Systems](https://arxiv.org/abs/1804.06512)
      - Design task-oriented and end-to-end neural netword to do: NLP understanding, Dialogue state (DL) tracking, dialogue policy learning.
      - Reinforcement learning (RL) với DL ostate.
      - Pre-trained with teacher.
    - [Neural Belief Tracker: Data-Driven Dialogue State Tracking](https://arxiv.org/abs/1606.03777)
      - Neural Belief Tracker (NBT)
        - leveraging sematic information from pre-trained word vectors to resolve lexical/morphological ambiguity
        - maximising the number of parameters shared across ontology values
        - having the flexibility to learn domain-specific paraphrasings and other kinds of variation that make it infeasible to rely on exact matching and delexicalisation as a robust strategy.
    - [Robust dialog state tracking using delexicalised recurrent neural networks and unsupervised gate](http://svr-ftp.eng.cam.ac.uk/~sjy/papers/htyo14.pdf)
      - RNN + delexicalised feature.
    - [Large-Scale Multi-Domain Belief Tracking with Knowledge Sharing](https://www.aclweb.org/anthology/P18-2069)
      - NBT (Neural Belief Tracker) + share information between domain 
    - [Toward Scalable Neural Dialogue State Tracking](https://arxiv.org/abs/1812.00899)
      - Improve GLAD(>1 recurrent networks with global and local conditional) by using 1 RNN with global conditional.
    - [Transferable Multi-Domain State Generator for Task-OrientedDialogue Systems](https://arxiv.org/abs/1905.08743)
      - TRADE: using copy mechanism which make knowledge transfer while training.
3. Retrieval-based Chatbot (response selection, that aims to find correct responses from a pre-defined index)
  - Dataset:
    - Ubuntu Corpus: 1 million multi-turn dialogues from the Ubuntu Chat Logs.
    - Reddit Corpus: 726 million multi-turn dialogues from the Reddit board. 
  - Paper:
    -  [Improved Deep Learning Baselines for UbuntuCorpus Dialogs](https://arxiv.org/abs/1510.03753)
      - 
4. Generative-based Chatbot (generate consistent and engaging response given the context)
  - Dataset:
  - Paper:
    - [Personalizing Dialogue Agents: I have a dog, do you have pets too?](https://arxiv.org/abs/1801.07243)
      - Problem: 
        - The lack of a consistent personality.
        - The lack of an explicit long-term memory as they are typically trained to produce an utterance given only the recent dialogue history.
        - A tendency to produce non-specific answers like "I dont know".
    - [Neural Machine Translation by Jointly Learning to Align and Translate](https://arxiv.org/abs/1409.0473)
      - Old encoder-decoder: encode a source sentence into a fixed-length vector from which a decoder generate a responds => bottleneck in improving the encoder-decoder architecture.
      - Method: allowing a model to automatically (soft-)search for parts of a source sentence that are relevant to predicting a target word, without having to form these parts as a hard segment explicitly.
    - [NIPS 2018 Workshop Presentation](http://convai.io/NeurIPSParticipantSlides.pptx)
    - [TransferTransfo: A Transfer Learning Approach for Neural Network Based Conversational Agents](https://arxiv.org/abs/1901.08149)
      - Combine of Transfer learning based training scheme + high-capacity Transfo-rmer model.
### Hiếu