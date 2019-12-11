# Experiment 5 - Transfer learning on Pre-trained Transformers

# Create a virtual environment

Create a directory for your project 
```sh
$ mkdir my_project && cd my_project
```
Create a new virtual env
```sh
$ virtualenv env
```
Activiate the virtual env
```sh
$ source env/bin/activate
```
# Downloading the Pre-trained model and source code from Hugging Face
```sh
$ git clone https://github.com/huggingface/transformers
$ cd transformers
$ pip install --editable .
```

# Installing dependencies
```sh
pip install -r ./examples/requirements.txt
```
 
# Language model fine-tuning
GPT
```sh
$ python ./examples/run_lm_finetuning.py --train_data_file=./examples/bestamericanshortstories.txt --model_type=openai-gpt --output_dir=./openAiTf --model_name_or_path=openai-gpt --do_train --no_cuda
```
GPT-2
```sh
$ python ./examples/run_lm_finetuning.py --train_data_file=./examples/bestamericanshortstories.txt --model_type=gpt2 --output_dir=./gpt2Tf --model_name_or_path=gpt2 --do_train --no_cuda
```
# Text Generation

With fine tuned GPT
```sh
python ./examples/run_generation.py  --model_type=openai-gpt  --length=20  --model_name_or_path=./openAiTf --length=50 --no_cuda
```
With fine tuned GPT-2
```sh
python ./examples/run_generation.py  --model_type=gpt2  --length=20  --model_name_or_path=./gpt2Tf --length=50 --no_cuda
```
# Model Prompt
Enter text as model prompt (eg: Alice was walking home)

# Citation


```
@article{Wolf2019HuggingFacesTS,
  title={HuggingFace's Transformers: State-of-the-art Natural Language Processing},
  author={Thomas Wolf and Lysandre Debut and Victor Sanh and Julien Chaumond and Clement Delangue and Anthony Moi and Pierric Cistac and Tim Rault and R'emi Louf and Morgan Funtowicz and Jamie Brew},
  journal={ArXiv},
  year={2019},
  volume={abs/1910.03771}
}
```

