# ProtoCode

The ProtoCode can standardized protocol by either reading the input text or URL for the literature.
To initiate protocol standardization in ProtoCode, users are required to submit their URL for the literature described in natural text, and choose the protocol for extraction using a dropdown menu. Upon submission, ProtoCode first performs a screening analysis to identify the text region corresponding protocol. Users can correct any miss-annotation by highlighting the region of interest. Next, ProtoCode performs data extraction on a protocol specific fine-tuned LLM. The extracted data, in JSONL format, can be converted into standardized natural language text. Moreover, if the corresponding protocol data contains information on equipment settings and/or programs, users can select the outputs for operating experimental equipment.

## Installation

Ensure you have the required dependencies installed by running:

```bash
pip install -r requirements.txt
```

Make sure you have Conda installed on your system before proceeding. If you don't have Conda installed, you can download it from the official Conda website: https://docs.conda.io/en/latest/miniconda.html
```Navigate to the directory containing your environment.yml file using the terminal or command prompt.
conda env create -f environment.yml
conda activate name_of_your_environment
```

## 'Paper_Extraction'

Extract and save content from URL

### Content Configuration

1. Select a [BioRxiv](https://www.biorxiv.org/) URL (full-text) for the paper.
2. Paste the URL on the input_path in the [input file].
3. The result will be saved based on the output_path.
4. The number of keywords selected determines the quality of the extracted protocol.

## 'Robot Language'

1. Read extracted content or custom input
2. obtain output from the fine-tuned model
3. convert the output to robot language

### Conversion Configuration

1. Use the extracted protocol as the input from the [input_file].
2. If the quality is not satisfactory, manually extract content and paste it in [input_content].
3. Choose a number between 1 and 5 to select one of the five fine-tuned models.
4. The result will be saved based on the output_path.

## 'content_config'

Config file for Paper Extraction

### Required setting
URL for the article- input_link

### Optional setting
1. Output path - output_path
2. Number of keywords - num_keywords

## 'conversion_config'

Config file for Robot Language

### Required setting:

Use extracted content - input_file
Or customized content - input_content

### Optional setting:

1. Choice of fine-tuned model - model_selection
2. Output path - output_path








