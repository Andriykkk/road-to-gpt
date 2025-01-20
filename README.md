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
 
### 5. **LSTM Model**
- **Context Size**: 100-400
- **Vocabulary Size**: 91 (characted level tokenisation)
- **Description**: Created LSTM and teach it on Shecspir dataset, again it don`t generate anything useful, still loss too big and probably problems with tokenisation as character level is give too much tokens in which lstm cant find anything useful, but it was quite big improvement compared to usual rnn, but it not just lstm as i added other layers after lstm to increase perfomance
- **Performance**: 
    - The model performed poorly with a minimum loss of 3.2 which is quite big improvement compared to previous model, but still generate gibberish.
    - Problem right now I think is that lstm is not for text, it is definitely better that others that I tried, but transformer is just better and at such size it`s not so expensive, but i want to find something that not transformer as i have no clue of how to expand transformers so they could give good results outside of Shecspir dataset.
 
### 5. **Transformer Model**
- **Context Size**: 32
- **Vocabulary Size**: 91 (characted level tokenisation)
- **Description**: Created Transformer and teach it on Shecspir dataset, very big improvement from lstm and one of the reason is that i made mistake in lstm due to which it couldn`t learn, but still i think that trasnformer work just better and also i get quite good results, it even generate something that look like something readable.
- **Performance**: 
    - The model performed quite good with a minimum loss of 1.7. It is great improvement compared to previous model.
    - Problem is that i train model in vacuum, I want to get some real life results, so next model, will be again transformer just bigger, probably. I want to test how it will work will dataset I found on huggingface.
- **Example**
```
DUCHESS OF YORK:
Besome till perty of Rome, I ull.
Yet.

SICINIUS:
Thy lease spreatune's eagure and thou sea let,
And my goot whither's hold chaughts:
Thy telmains, now and when in her?

Swilt:
Think Romen matibles, our good of solven him.

HENRY BOLINGBRown I:
whither, but it
How
What dours, Poling and what he hast boot outtending you womo shame
Will ruthines; what the tear?

KING RICHARD III:
Somet!

KING RICHARD III:
That's Maries: in this too?
```
 
