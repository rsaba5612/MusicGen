
# AudioBooks Generotor

A brief description of what this project does 



## Deployment

To deploy this project run

```bash
streamlit==1.22.0
langchain==0.0.176
openai==0.27.7
tiktoken==0.4.0
unstructured==0.6.8
tabulate==0.9.0
pdf2image==1.16.3
pytesseract==0.3.10
```


## Problem

Many people enjoy reading books, but sometimes it's
not convenient to read due to tasks like driving,
exercising, or multitasking
## Solution

Develop a text-to-audio converter that can turn
digital books or text documents into human-like
audio narration. Use text-to-speech (TTS) technology
to generate natural-sounding audio from text
content. Users can then listen to their favorite books on-the-go
## Lessons

During my participation in the hackathon as a first-time participant, I gained valuable insights and experiences. I had the opportunity to familiarize myself with various libraries and technologies, which greatly enhanced my technical skills. Throughout the hackathon, I encountered a few challenges, but each presented an opportunity for learning and growth.
## Usage/Examples

```python

import validators
import streamlit as st
from langchain.chat_models import ChatOpenAI
from langchain.document_loaders import UnstructuredURLLoader
from langchain.chains.summarize import load_summarize_chain
from langchain.prompts import PromptTemplate
from transformers import AutoProcessor, MusicgenForConditionalGeneration
import scipy

# Streamlit app
st.subheader('URL to Song:')
st.caption(
    "ChatGPT will turn the contents of this URL's website into a song description and Audiocraft will then create a song out of it and save it as musicgen_out.wav in your project's folder. This might take a while the first time your run it because Audiocraft needs to download the models.")

