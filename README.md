# Language Models


This repository contains Jupyter Notebooks implementing different language models from most simple like bigram to more complex.

## Models Implemented

### 1. **Bigram Model**
- **Context Size**: 2 and 3(bigram)
- **Token Size**: One letter
- **Description**: This model predicts the next character based on the previous one. It was trained on a list of names, attempting to learn name patterns and generate new names based on that training.
- **Performance**: 
    - The model performed poorly, generating names that more suited as nicknames for game than real names.

### 2. **Multilayer Perceptron (MLP) Model**
- **Context Size**: 1024
- **Vocabulary Size**: 10,240 (created by SentencePiece)
- **Description**: This MLP model uses a significantly larger context size and vocabulary for training. It leverages SentencePiece for tokenization and learns over a longer sequence of input characters. The model's goal is to generate at least something meaningfull based on the dataset.
- **Performance**: 
    - The model performed poorly, with a minimum loss value between 6.5 and 7, and the loss did not improve further during training.
    - The generated output was mostly nonsensical, but occasionally the model correctly produced an end-of-sequence token, effectively stopping the generation.

### 3. **WaveNet Model**
- **Context Size**: 1024
- **Vocabulary Size**: 10,240 (created by SentencePiece)
- **Description**: In this implementation, the model aims to generate text instead of audio.
- **Performance**: 
    - The model performed poorly with a consistent loss of 7 during training.
    - I think the model is just too deep, and without normalization layers or residual blocks, the model struggles to learn effectively.
 
### 4. **RNN Model**
- **Context Size**: 10
- **Vocabulary Size**: 91 (characted level tokenisation)
- **Description**: Created simple RNN and tried to teach it on Shecspir dataset, as you may thing nothing usefull it don`t generate, but it was quite good result compared to others
- **Performance**: 
    - The model performed poorly with a loss of 4.7 on training and validation datasets.
    - Whole problem is in RNN layer, even if it improve overall perfomance and lower loss, I couldn`t increase context size due to exploding gradient, so next i will make LSTM, maybe it will resolve this problem.
 
