
# ChatGPT Fine-Tuning Guide

## Introduction
This repository provides an example on how to fine-tune the ChatGPT model for a specific task. 

It draws inspiration from the [GrammarGPT project](https://github.com/FreedomIntelligence/GrammarGPT). 

You're free to modify the input files as per your requirements.

## Steps to Fine-Tune Your Model

### 1. Setup

Ensure you have the latest OpenAI package installed (version `openai>=0.27.9`).

```bash
pip install -r requirements.txt
```

### 2. Data Preparation

Prepare your custom training data (e.g., `train_data.jsonl`) and validation data (e.g., `dev_data.jsonl`).

**Note:** The size of the input file is currently capped at 50MB. For more details, refer to the [OpenAI documentation on dataset preparation](https://platform.openai.com/docs/guides/fine-tuning/preparing-your-dataset).

### 3. Model Training

To train your model, use the `train_model.py` script:

```bash
python train_model.py
```

**Important:** In `train_model.py`, ensure that you first upload the custom data to OpenAI. Once the upload is successful, the training will commence. The training process might take several hours, so please be patient.

### 4. Model Testing

To test your fine-tuned model, use the `test_model.py` script:

```bash
python test_model.py
```

**Note:** You need to get the model id before the test.

## Experimental Results

| Model                     | # Param. | Data| Word-level (P/R/F) | Char-level(P/R/F)         |
|:--------------------------|:---------|:----|:-------------------|:--------------------------|
| S2S_BART                  | 375M     | 1061| 21.08/10.54/17.57  | 22.09/10.62/18.16         |
| GrammarGPT                | 7B       | 1061| **42.42**/16.87/32.56  | **46.67**/18.58/**35.84** |
| Fine-tuning GPT-3.5 Turbo | -        | 1061| 36.16/**34.75**/**35.87**  | 36.17/**33.69**/35.65     |


## Additional Resources

- Official OpenAI API documentation on fine-tuning: [API Reference](https://platform.openai.com/docs/api-reference/fine-tuning/create)
- OpenAI Guide on creating a fine-tuned model: [Python Guide](https://platform.openai.com/docs/guides/fine-tuning/create-a-fine-tuned-model)
- Video tutorial on fine-tuning ChatGPT: [YouTube Tutorial](https://www.youtube.com/watch?v=_yzmQbez7gk)

## Acknowledgments

Special thanks to the following repository for its invaluable insights:

[OpenAI Fine-tuning Guide](https://github.com/horosin/open-finetuning/tree/main)
