# Week 02: Read Papers 
05-08-2019 -> 12-08-2019
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
#Tuan 02: Read papers
## Paper 1: [Personalizing Dialogue Agents: I have a dog, do you have pets too?](https://arxiv.org/abs/1801.07243)
Vấn đề đặt ra: lack specificity, do not display a consistent personality and are often not very captivating (quyến rũ)
Giải pháp: conditioning on profile information
Colect data to train models 
- Condition on their given profile information
- information about the person they are talking to.
Dataset: PERSONA-CHAT

## Paper 2: [Dialogue Learning with Human Teaching and Feedback in End-to-End Trainable Task-Oriented Dialogue Systems](https://arxiv.org/abs/1804.06512)
Vấn đề: mismatch: dialogue state distribution between offline training and online interactive learning stages
Giai phap: hybrid imitation and reinforcement learning method
trước khi cho ra ngoài học, học với giáo viên của nó.

## Paper 3: Sounding Board: A User- Centric and Control-Driven Social Chatbot
## Paper 4: [Training Millions of Personalized Diaglogue Agents](https://arxiv.org/abs/1809.01984)
Giống bài 1 nhưng với dataset lớn hơn vẫn cải thiện nhiều:
+ 5 million personas (so với 1k of 1)
+ 700 million persona-based dialogue

## Paper 5: [A Large-Scale Multi-Domain Wizard-of-Oz Dataset for Task-Oriented Dialogue Modelling](https://arxiv.org/abs/1810.00278)
Tập dữ liệu lơn.

## Paper 6: [Sematic Parsing for Task Oriented Dialog using Hierarchical Representations](https://arxiv.org/abs/1810.07942)
Ván đề: cũ: one intent per query and one slot label per token.
cannot model complex compositional request
=> semantic parsing system -> van de: annotate and parse
Giai phap: hierarchical annotation scheme for semantic parsing that allow the representation of compositional queries
this method outperform sequence-to-sequence approaches on this dataset

## Paper 7: [Towards Universal Dialogue State Tracking](https://arxiv.org/abs/1810.09587)

## Paper 8: [Unsupervised Transfer Learning for Spoken Language Understanding in Intelligent Agents](https://arxiv.org/abs/1811.05370)

## Paper 9: [Few-Shot Generalization Across Dialogue Tasks](https://arxiv.org/abs/1811.11707)
Van de: han chế trong extend khả năng với new domain.
Vi du: from restaurant reservation -> booking a hotel
Giai phap: REDP (Recurrent Embedding Dialogue Policy)

## Paper 10: [Learning from Dialogue after Deployment: Feed yourself, Chatbot!](https://arxiv.org/abs/1901.05415)
chit-chat dataset (131k training example)
When the conversation appears to be going well, the user's responses become new training examples to imitate. When the agent believes it has made a mistake, it asks for feedback, learning to predict the feedback that will be given improves that chatbot's dialogue abilities further.

## Paper 11:[Towards a Continuous Knowledge Learning Engine for Chatbots](https://arxiv.org/pdf/1802.06024.pdf)
van de: cannot learn new knowledge during the conversation process.
Giai phap: Lifelong interactive learning and inference (LiLi)

## Paper 12: [OntBot: Ontology based chatbot]
## Paper 13: [DocChat: An information Retrieval Approach for Chatbot Engines Using Unstructured Documents](https://www.aclweb.org/anthology/P16-1049)
Cai ten noi len tat ca

## Paper 14: [Joint Online Spoken Language Understanding and Language Modeling with Recurrent Neural Networks](https://arxiv.org/pdf/1609.01462v1.pdf)
The model keeps updating the intent predictions as word in the transcripbed utterance arrives and uses it as contextual features in the joint model.

## Paper 15: [Attention-Based Recurrent Neural Network Models for Joint Intent Detection and Slot Filling](https://arxiv.org/abs/1609.01454v1)
Our joint training model further obtains 0.56% absolute (23.8% relative) error reduction on intent detection and 0.23% absolute gain on slot filling over the independent task models.

## Paper 16: [A Network-based End-to-End Trainable Task-oriented Dialogue System](https://arxiv.org/abs/1604.04562)
challenges: + creating multiple components
=> neural network-based text-in, text-out end-to-end trainable goal-oriented dialogue system
new way of collecting dialogue dta based on a novel pipi-lined Wizard-of-Oz framwork

## Paper 17: [Conditional Generation and  Snapshot Learning in Neural Dialogue Systems](https://arxiv.org/abs/1606.03352)
method: Snapshot learning
different archictecture provide different trade-offs between the two.

## Paper 18: [Incorporating Unstructured Textual Knowledge Sources into Neural dialogue Systems](http://media.wix.com/ugd/b6d786_137894b7b3a341a09ed0c0b45b46dbb6.pdf)
-> leverage additional informatin about the topic of the conversation to improve the prediction accuracy.
simple method for extracting this knowledge: using a combination of hashing and TF-IDF.

## Paper 19: [End-to-end LSTM-based dialog control optimized with supervised and reinforcement learning](https://arxiv.org/pdf/1606.01269v1.pdf)
giảm handcrafting

## Paper 20: [Towards End-to-End Reinforcement Learning of Dialogue Agents for Information Access](https://arxiv.org/abs/1609.00777)
Replace symbolicc queries with an induced "soft" posterior distribution over the KB that indicates which entities the user is interested in.
Integrating the soft retrieval process with a reinforcement learners leads to higher task success rate and reward in both simulations and againts real users.

## Paper 21: [End-to-End Joint Learning of Natural Language Understanding and Dialogue Manger](https://arxiv.org/abs/1612.00913)
vande: pipeline model: NLU - SAP (system action prediction)
giai quyet: an end-to-end recurrent neural network with limited contextual dialogue memory by jointly NLU and SAP on DSTC4 multi-domain human-human dialogues.
=> Experiment: outperform state-of-the-art pipeline model

## Paper 22: [Hybrid Code Networks: practical and efficient to end-to-end dialog control with supervised and reinforcement learning](https://arxiv.org/abs/1702.03274)
van de: end-to-end learning of RNN is an attractive solution for dialog system, but current techniques are data-intensive and require thousands of dialogs to learn simple behavior.
=> Hybrid Code Networks (HCNs): combine RNN with domain-specific knowledge encoded as software and system actioon template
Kqua: reduce amount of training data require, while retaining the key benefit of inferring a latent representation of dialog state
state-of-the-art performance on th bAbi dialog dataset.

## Paper 23: [Learning Sysmetric Collaborative Dialogue Agents with Dynamic Knowledge Graph Embeddings](https://arxiv.org/abs/1704.07130)
dataset: 11K human-human dialogues.
=> neural model with dynamic knowledge graph embedding 
two agents, each with private knowledge, must strategically communicate to achieve a common goal.

## Paper 24: [Key-Value Retrieval Networks for Task-Oriented Dialogue](https://arxiv.org/abs/1705.05414)
dataset of 3.031 dialogues:3 tasks in-car personal assistant space: calendar schelduling, weather information retrieval, and point-of-interest navigation
problem: struggle to smoothly interface with a knowledge base
solution: new neural dialogue agent that able to effectively sustain grounded, multi-domain discourse through a novel key-value retrieval mechanism.

## Paper 25: [Deal or No Deal? End-to-End Learning for Negotiation Dialogues](https://arxiv.org/abs/1706.05125)
possible to train end-to-end models for negotiation.

## Paper 26: [Generative Encoder-Decoder Models for Task-Oriented Spoken Dialog Systems with Chatting Capability](https://arxiv.org/abs/1706.08476)
Problem: Generative encoder-decoder models have mainly been applied to open-domain conversations. 
This paper presents a practical and novel framwork for building task-oriented dialog systems based on encoder-decoder models.

## Paper 27: [An End-to-End Trainable Neural Network Model with Belief Tracking for Task-Oriented Dialog](https://arxiv.org/pdf/1708.05956.pdf)
track dialog state, 
jointly learning belief tracking and KB result processing conditioning on the dialog history.
dataset: Dialog State Tracking Challenge corpus
outperforming prior end-to-edn model using per-response accuracy evaluation metrics

## Paper 28: [End-to-End Recurrent Entity Network for Entity-Value Independent Goal-Oriented Dialog Learning](http://workshop.colips.org/dstc6/papers/track1_paper02_wu.pdf)
framwork based on Recurrent Entity Networks
is able to astract linguistic entity by using a delexicalization mechanism.

## Paper 29: [Toward Continual Learning for Conversation Agents](https://arxiv.org/pdf/1712.09943.pdf)
end-to-end neural conversation models have led to promissing advances in reducing hand-crafted feature and errors induced by the traditional complex system archictecture.
vande: require enormous amount of data due to the lack of modularity
previous study: a hybrid approach with knowledge-based components either to abstrack out domain-specific information or to augment data to cover more diverse patterns
=> a domain-indepentdant neural conversational model and introduce a novel neural continual learning algorithm that allows a conversational agent to accumulate skills across different tasks in a data-efficient way.
This is the first work applies continual learning to conversation systems.


## Paper 30: [Building a Conversational Agent Overnight with Dialogue Self-Play](https://arxiv.org/abs/1801.04871)
Machines Talking to Machines (M2M)
Compareed to the Wizard-of-Oz approach for data collection, M2M achieves greater diversity and coverage of salient dialogue flows while maintaining the nautralnesss of individial utterances.
2 phases
the entire process can finish within a few hours. 
propose a new corpus of 3000 dialogues spanning 2 domains collected with M2M.

Repeat/Practice until you get used to it.

## Paper 31: [Mem2Seq: Effectively Incorporating Knowledge Bases into End-to-End Taks-Oriented Dialog Systems](https://arxiv.org/abs/1804.08217)
problem of end-to-end dialog system: challenge of incorporating knowledge bases
solutions: memory-to-sequence(Mem2Seq)
combines the multi-hop attention over memories with the idea of pointer network.
## Paper 32: [Sub-domain Modelling for Dialogue Management with Hierarchical reinforcement Learning](https://arxiv.org/pdf/1706.06210.pdf)
problem: standart flat reinforcement learning methods do not provide an efficent framwork for modelling such dialogues.
=> focus on the under-explored problem of multi-domain dialogue management.
new method: hierarchical reinforcement learning using the `option` framwork.
cho ra policies tot hon

## Paper 33: [Cross-domain Dialogue Policy Transfer via Simultaneous Speech-act and Slot Alignment](https://arxiv.org/abs/1804.07691)
Dialogue policy transfer enables us to build dialogue policies in a target domain with little data
PROMISE model can effectively transfer dialogue policies across domains with different speech-acts and disjoint slots.
Policy tTransfer across dOMaIns and SpEech-acts (PROMISE) model

## Paper 34: [Zero-Shot Dialog Generation with Cross-Domain Latent Actions](https://arxiv.org/abs/1805.04803)
ZSDG that can instantly generalize to new situations with minimal data.
ZSDG enables an end-to-edn generative dialog system to generalize to a new domain for which only a domain description is provided and no training dialogs are available.
Action Matching, 
--chatbot
## Paper 35: [A Neural Conversational Model](https://arxiv.org/abs/1506.05869)
problems: often restricted to specific domains and require hand-crafted rules.
the strength of our model is that it can be trained end-to-end thus requires much fewer hand-crafted rules.

## Paper 36: [A Neural Network Approach to Context-Sensitive Generation of Conversational Response](https://arxiv.org/pdf/1506.06714v1.pdf)
can be trained end to end on large quantities of unstructured Twitter conversations.