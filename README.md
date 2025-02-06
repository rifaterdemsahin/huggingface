### Programmatic access
- Use the Hub’s Python client library

## Getting started with our git and git-lfs interface

### You can create a repository from the CLI (skip if you created a repo from the website)

```sh
pip install huggingface_hub
# You already have it if you installed transformers or datasets

huggingface-cli login
# Log in using a token from huggingface.co/settings/tokens

# Create a model or dataset repo from the CLI if needed
huggingface-cli repo create repo_name --type {model, dataset, space}

# Clone your model, dataset or Space locally

Make sure you have git-lfs installed
Git LFS

git lfs install
git clone https://huggingface.co/username/repo_name

# Then add, commit and push any file you want, including large files
git add .
git commit -m "commit from $USER"
git push

In most cases, if you're using one of the compatible libraries, your repo will then be accessible from code, through its identifier: username/repo_name
For example for a transformers model, anyone can load it with:
from transformers import AutoTokenizer, AutoModel

tokenizer = AutoTokenizer.from_pretrained("username/repo_name")
model = AutoModel.from_pretrained("username/repo_name")
