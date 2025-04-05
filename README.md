# Intel® Unnati Industrial Training 2025 - Bug Detection and Fixing

🔗 **See how our model performs**: [Buggy Code Fixer 2.0 on Hugging Face](https://huggingface.co/spaces/Eleuther/buggy-code-fixer_2.0)

## Problem Statement 1: Bug Detection and Fixing

## Project Overview

This project focuses on bug detection and fixing using a fine-tuned LLaMA 3.1 8B model. It was developed as part of the Intel® Unnati Industrial Training 2025 program.

## Model Fine-Tuning

We fine-tuned the LLaMA 3.1 8B model using:

- LoRA (Low-Rank Adaptation) and QLoRA (Quantized LoRA) techniques  
- Transformer models from HuggingFace  
- Unsloth library for efficient fine-tuning  
- **Google Colab with free T4 GPU**  
- Quantization to optimize model size and performance  

### LoRA Model Components

The `lora_model` folder contains the following key files for the fine-tuned model:

- `adapter_config.json`: Configuration file specifying LoRA parameters like rank (r), alpha, and target modules  
- `adapter_model.safetensors`: Contains the trained LoRA adapter weights in a safe tensor format  
- `tokenizer_config.json` & `tokenizer.json`: Tokenizer configuration and vocabulary files  
- `special_tokens_map.json`: Defines special tokens used during training  

These files work together to enable:

- Efficient storage of only the adapter weights (typically <1% of full model size)  
- Safe loading of the fine-tuned components  
- Seamless integration with the base LLaMA model  

The fine-tuning process is documented in `intell_buggy_to_fix.ipynb` which includes:

- Dataset downloading and preprocessing  
- Model fine-tuning implementation  

## Dataset

All datasets used for training are available in the `Data_sets` folder, originally sourced from HuggingFace datasets (free to download). The model is trained on multiple programming languages including Python, JavaScript, Java, Ruby, C, and Rust. The datasets contain buggy/fixed code pairs for each language:

- humanevalpack_python.csv  
- humanevalpack_js.csv  
- humanevalpack_java.csv  
- humanevalpack_rust.csv  
- humanevalpack_go.csv  

These datasets are combined and formatted into a JSON file (`formatted_datasetfordataset_buggy_fixed_code_dataset.json`) which is used to fine-tune the model. Each entry contains 'buggy' and 'fixed' versions of code snippets.
## Sample Outputs Image
- the sample outputs of the model in Sample_outputs folder
## Model Deployment

To run the fine-tuned model:

1. Use `loading_fine_tuned_model.ipynb` to load the model  
2. The notebook includes Gradio deployment code  
3. The model performs bug detection and provides fixed versions of code snippets  

### Deployment Details

We have successfully deployed our model using:

- Gradio for creating an interactive user interface  
- Hugging Face Spaces for hosting the deployment  

### Sample Outputs

We have included example outputs in the `sample_output` 

folder which demonstrate:

- Various bug detection scenarios  
- Fixed code examples  
- Multi-language support results  

## Getting Started

1. Clone this repository  
2. Install required dependencies (see `intell_buggy_to_fix.ipynb` for package requirements)  
3. Run `loading_fine_tuned_model.ipynb` to test the model  

## Team Members

- **Dhanush Raja** – Second Year, Department of Computer Science and Business Systems  
- **Koushik** – Second Year, Department of Computer Science and Business Systems  