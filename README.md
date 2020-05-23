# Generating Questions
This is module for produce question generation. Originally forked from [here](https://github.com/martiansideofthemoon/squash-generation)

I am uploading two python notebook in which you only need to run on colab with few changes in address.

>>One python notebook name PreprocessBOOLQ preprocesses the original BOOLQ dataset to SQUASH format.

>>Second python notebook produces BOOLEAN Questions named boolquestiongeneration produces boolean question.

Final generated question will be produced inside /squash/temp/quac_869/ folder with filename generated_questions.json.


<b>Note : Done as Questgen Open Source Initiative.</b>


## Requirements

Create a new Python 3.6 virtual environment. Run the following,

1. Clone the repo.Install the requirements using `pip install -r requirements.txt`.

2. Install the English `spacy` library using `python -m spacy download en_core_web_sm`.

2. Since the code uses a slightly modified version of [huggingface/pytorch-pretrained-BERT](https://github.com/huggingface/pytorch-pretrained-BERT), it needs to be installed locally. Run `cd pytorch-pretrained-BERT` followed by `pip install --editable .`

## Dataset

The training dataset for the question generation module is already kept in temp_dataset inside data folder.We converted the [BOOLQ dataset](https://github.com/google-research-datasets/boolean-questions) to SQUASH format.

#### Preprocessing Instructions

The trained model is kept inside this drive link.[Link](https://drive.google.com/drive/folders/1-CDmozJ3w2X9nw5etzYpgmm8KvHfr4GQ?usp=sharing).You need to download this model and keep in a new with folder name gpt2_corefs_question_generations inside question-generation folder.

## Question Generation

Our conditional question generation model is forked from [huggingface/transfer-learning-conv-ai](https://github.com/huggingface/transfer-learning-conv-ai). We generate conditional questions using a language model which is fine-tuned from OpenAI's GPT or GPT2. We convert our training data as follows,

1. For `general` questions - `<bos> ... paragraph text ... <answer-general> ... answer span ... <question-general> ... question span ... <eos>`
2. For `specific` questions - `<bos> ... paragraph text ... <answer-specific> ... answer span ... <question-specific> ... question span ... <eos>`.


## Citation

```
@inproceedings{squash2019,
Author = {Kalpesh Krishna and Mohit Iyyer},
Booktitle = {Association for Computational Linguistics,
Year = "2019",
Title = {Generating Question-Answer Hierarchies}
}
```
