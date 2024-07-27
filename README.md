# Educational Chatbot

Final project for the Building AI course

## Summary

This project aims to develop an educational chatbot that assists children with their homework by answering simple questions about various school subjects such as math, science, and history. The chatbot is designed to provide quick, accurate, and engaging responses to foster a love for learning.

## Background

Homework can sometimes be challenging for children, and they may not always have access to immediate help. This educational chatbot addresses the need for accessible, instant educational support. By leveraging AI, we can provide a tool that helps children understand their subjects better, making learning more interactive and enjoyable. This project is particularly relevant in today's digital age, where technology can play a significant role in education.

## How is it used?

The chatbot can be accessed via a web interface or a mobile app. Here’s how it works:

1. **User Interaction**: Children can type or speak their questions into the chatbot.
2. **Processing**: The chatbot processes the question using natural language processing (NLP) techniques to understand the query.
3. **Response Generation**: Based on the understanding of the question, the chatbot provides a clear and concise answer.
4. **Feedback Loop**: Children can ask follow-up questions or provide feedback on the chatbot’s responses to improve its accuracy over time.

### Example Use Cases

- A child asks, "What is the capital of France?" and the chatbot responds, "The capital of France is Paris."
- A child asks, "How do you solve 3x + 4 = 10?" and the chatbot provides a step-by-step solution.


## Data sources and AI methods

The chatbot uses the following resources and methods:

- **Data Sources**: Open educational resources, publicly available datasets on school subjects, and custom-generated data for training purposes.
- **NLP Techniques**: Tokenization, Named Entity Recognition (NER), Part-of-Speech (POS) tagging, and dependency parsing to understand and generate responses.
- **Machine Learning Models**: The LLAMA model, which is an open-source language model that can be fine-tuned for specific educational content.

Example code snippet for processing a question using LLAMA:
```python
from transformers import LlamaTokenizer, LlamaForCausalLM

tokenizer = LlamaTokenizer.from_pretrained("facebook/llama-7b")
model = LlamaForCausalLM.from_pretrained("facebook/llama-7b")

def get_answer(question):
    inputs = tokenizer(question, return_tensors="pt")
    outputs = model.generate(**inputs)
    answer = tokenizer.decode(outputs[0], skip_special_tokens=True)
    return answer

question = "What is the largest planet in our solar system?"
answer = get_answer(question)
print(answer)  # Expected output: "The largest planet in our solar system is Jupiter."
```

## Challenges

- **Understanding Complex Questions:** The chatbot might struggle with highly complex or ambiguous questions.
- **Maintaining Engagement:** Ensuring that the chatbot remains engaging and does not frustrate children with incorrect or unclear answers.
- **Ethical Considerations:** Ensuring that the data used is appropriate for children and that the chatbot provides safe and accurate information.

## What next?

To further develop this project, we could:

Expand the Knowledge Base: Continuously update the data sources and improve the NLP models.
Voice Interaction: Implement voice recognition and response capabilities to make the chatbot more interactive.
User Personalization: Adapt responses based on the individual child's learning style and preferences.
Gamification: Introduce gamified elements to make learning more fun and engaging.

## Acknowledgments

- **Inspiration :** Inspired by various educational tools and the potential of AI in education.
- **Resources :** Utilized open-source educational datasets and the LLAMA model.
- **Contributors :** Thanks to all who provided feedback and contributed to the development of this project.
