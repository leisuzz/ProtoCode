# ProtoCode

The ProtoCode can standardized protocol by either reading the input text or URL for the literature.
To initiate protocol standardization in ProtoCode, users are required to submit their URL for the literature described in natural text, and choose the protocol for extraction using a dropdown menu. Upon submission, ProtoCode first performs a screening analysis to identify the text region corresponding protocol. Users can correct any miss-annotation by highlighting the region of interest. Next, ProtoCode performs data extraction on a protocol specific fine-tuned LLM. The extracted data, in JSONL format, can be converted into standardized natural language text. Moreover, if the corresponding protocol data contains information on equipment settings and/or programs, users can select the outputs for operating experimental equipment.

## Installation

Ensure you have the required dependencies installed by running:

```bash
pip install -r requirements.txt

```Navigate to the directory containing your environment.yml file using the terminal or command prompt.
conda env create -f environment.yml
conda activate name_of_your_environment


