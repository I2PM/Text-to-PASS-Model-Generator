# LLMs-For-Subject-Oriented-ProcessModeling

This repository contains the source code, prompts, and generated visualizations for Masters Thesis on:  
**Exploring the Potential of LLM Technology to Create Subject-Oriented Process Models from Natural Language Texts**.   
It includes implementations for zero-shot, one-shot, and chain-of-thought (CoT) prompting strategies, as well as a web-based interactive Graphical User Interface (GUI) for interactive human-in-the-loop PASS process modeling.


 ## Repository Structure

 This repository has the following structure:  
```text
LLMs-For-Subject-Oriented-ProcessModeling/  
├── Outputs/  
│   ├── Thesis_Illustrations/               # Full-size vector graphics used in the thesis  
│   ├── CoT/                                # CoT visualizations  
│   ├── OWL/                                # OWL visualizations  
│   ├── OneShotPrompting/                   # OneShotPrompting visualizations  
│   └── ZeroShotPrompting/                  # ZeroShotPrompting visualizations  
├── src/                                    # Source code (all scripts)
    ├── CoT/
    ├── GUI/                                # GUI notebooks
        ├── GUI-Interactive/                # Final Web-based human-in-the-loop interactive GUI notebooks
        ├── Llama/                          # Original Llama notebook (non-interactive)
        ├── Mistral-Small/                  # Original Mistral notebook (non-interactive)
    ├── OWL/ 
    ├── OneShotPrompting/
    ├── ZeroShotPrompting/ 
├── README.md                               # This file  
└── Requirements.txt                        # Python dependencies

```

### Model-Specific Folders  

- **Llama:** Contains code used for experiments with Llama model. Experiments are organized by prompting strategy: zero-shot, one-shot, and chain-of-thought.    

- **Mistral-Small:** Contains code used for experiments with Mistral-Small model. Experiments are organized by prompting strategy: zero-shot, one-shot, and chain-of-thought.   

> The variable `model` in each notebook determines which model is used in the notebook. You can change it to your preferred model (e.g., `"mistral-small"`).
 
### Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/shadiamanan/LLMs-For-Subject-Oriented-ProcessModeling.git  
cd LLMs-For-Subject-Oriented-ProcessModeling  
pip install -r Requirements.txt

```

## Configuration

Before running the notebooks, configure your API key and preferred model.

```python

from openai import OpenAI

api_key = "YOUR_API_KEY"
model = "Llama-3.3-70B"  # change to your preferred model
client = OpenAI(api_key=api_key, base_url=base_url)

```

### **Model Usage Notes**

**Mistral**: Best for linear simple scenarios.  
Responses may be truncated if the context window is exceeded.  

**Llama**: Recommended for complex scenarios requiring decision flows and longer context window.  

### File Paths
The notebooks reference local directories for saving diagrams or files (e.g., `E:\Thesis\PASS Diagrams\Diagram\llama`).    

To run the notebooks, you can either:    
1. Create a folder structure on your local machine where the outputs will be saved, **or**  
2. Update the path variables in the notebooks to match a directory of your choice.

### Running the GUI in Jupyter Notebook
The repository provides a **web-based, human-in-the-loop interactive GUI** for exploring different LLMs in process modeling.

### Steps to launch

Each GUI notebook has a **last cell** that launches the web-based interactive GUI.  

- The **top of this cell** contains the `model` variable, which determines which LLM will be used in the GUI:

```python
model = "mistral-small"  # You can change it to your preferred model  
```

Open the corresponding GUI notebook and run the **last cell** in the notebook. It ends with:  

```python  
app.show()

```  
the web-based interactive GUI will launch.

### Model Details for GUI

- **Llama folder**: contains code using Llama model. This GUI uses **one-shot complex scenario prompt**.
- **Mistral-Small folder**: contains code using Mistral-Small model. This GUI uses **one-shot simple scenario prompt**.

Prompts used differ between the two GUI versions.

> The variable `model` in each notebook determines which model is used in the GUI. You can change it to your preferred model (e.g., `"mistral-small"`). All GUI calls will use this variable.

### GUI Notebook Notes

- The final GUI notebooks in the **GUI-Interactive** folder use the **one-shot prompting strategy**, which produced the best overall results in experiments.

### Configuring for a Different LLM  

If you are **not using the Uni Münster LLM**, update the following variables:  

`base_url` variable in the notebook to match your LLM provider’s endpoint. For example:  

```python
base_url = "https://api.openai.com/v1"  # OpenAI endpoint
``` 

`model` variable in the notebook for using LLM of choice. For example:   

```python
model = "mistral-small"  # model used  
```

In GUI notebooks, the `model` and `base_url` variables are at the top of the last cell in the notebook. 
In other notebooks, update the variables in initialization cells for a specific prompt strategy. 


