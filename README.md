# ProtoCode: Large Language Model pipeline for enhanced human and machine interpretable protocol resource construction

![Framework of ProtoCode](https://github.com/leisuzz/ProtoCode/blob/main/figs/protocode_cover.png)

The ProtoCode can standardized protocol by either reading the input text or URL for the literature.
To initiate protocol standardization in ProtoCode, users are required to submit their URL for the literature described in natural text, and choose the protocol for extraction using a dropdown menu. Upon submission, ProtoCode first performs a screening analysis to identify the text region corresponding protocol. Users can correct any miss-annotation by highlighting the region of interest. Next, ProtoCode performs data extraction on a protocol specific fine-tuned LLM. The extracted data, in JSONL format, can be converted into standardized natural language text. Moreover, if the corresponding protocol data contains information on equipment settings and/or programs, users can select the outputs for operating experimental equipment.

## ProtoCode embraces a full-stack framework with four layers:

1. **Data source layer**: This layer collects data from different sources.
2. **Protocol Extraction layer**: This layer retrieves the content from article URLs, which is particularly helpful for reducing the input tokens for the model.
3. **LLM layer**: This layer mitigates the input protocols, ensuring the model’s relevance and accuracy with fine-tuning and cross-validation.
4. **Application layer**: Practical applications, this layer highlights the potential capability of the ProtoCode in different functions.

* ProtoCode Framework: Large Language Model for enhanced human and machine interpretable protocol resource construction

![Framework of ProtoCode](https://github.com/leisuzz/ProtoCode/blob/main/figs/Framework.png)

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

## Paper_Extraction

[Paper_Extraction](https://github.com/leisuzz/ProtoCode/blob/main/Paper_Extraction.ipynb) extract and save content from URL

### Content Configuration

1. Select a [BioRxiv](https://www.biorxiv.org/) URL (full-text) for the paper.
2. Paste the URL on the input_path in the [input file].
3. The result will be saved based on the output_path.
4. The number of keywords selected determines the quality of the extracted protocol.

## Robot Language

[Robot Language](https://github.com/leisuzz/ProtoCode/blob/main/Robot%20Language.ipynb) has functions include:
1. Read extracted content or custom input
2. obtain output from the fine-tuned model
3. convert the output to robot language

### Conversion Configuration

1. Use the extracted protocol as the input from the [input_file].
2. If the quality is not satisfactory, manually extract content and paste it in [input_content].
3. Choose a number between 1 and 5 to select one of the five fine-tuned models.
4. The result will be saved based on the output_path.

## content_config

[content_config](https://github.com/leisuzz/ProtoCode/blob/main/content_config.ini) is the Config file for Paper Extraction

### Required setting

* URL for the article
```
[input_link]
url = 
```

### Optional setting

1. Output path - output_path
2. Number of keywords - num_keywords # default is 4

```
[output_path]
out_path = ./protocols/protocol.csv

[num_keywords]
num_keywords = 
```

## conversion_config

[conversion_config](https://github.com/leisuzz/ProtoCode/blob/main/conversion_config.ini) is the config file for Robot Language

### Required setting:

* Use extracted content - input_file
* Or customized content - input_content

```
[input_file]
input_path = ./protocols/protocol.csv

[input_content]
content = 
```

### Optional setting:

1. Choice of fine-tuned model - model_selection
2. Output path - output_path

```
[model_selection]
model_num = 1

[output_path]
output_path = ./output_language/
```

## Citing ProtoCode

```
@article{,
  title={Shuo Jiang, Daniel Evans-Yamamoto, Dennis Bersenev, Sucheendra K. Palaniappan, and Ayako Yachie-Kinoshita},
  author={},
  journal={},
  year={2023}
}
```




