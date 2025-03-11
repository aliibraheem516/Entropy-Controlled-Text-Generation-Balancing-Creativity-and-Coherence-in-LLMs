# Entropy-Controlled Text Generation

This project explores the use of **Shannon entropy** to control text generation in **Large Language Models (LLMs)**, balancing **diversity** (creativity) and **coherence** (logical flow). By dynamically adjusting entropy, we fine-tune the model’s output for applications like **creative writing**, **AI content generation**, and **adaptive conversational agents**.

---

## What is Shannon Entropy?

**Shannon entropy** is a concept from information theory that measures the **uncertainty** or **randomness** in a probability distribution. In the context of text generation:
- **High Entropy**: The probability distribution over the vocabulary is more spread out, meaning the model is less certain about the next word.
- **Low Entropy**: The probability distribution is more concentrated, meaning the model is more confident about the next word.

### How is Shannon Entropy Calculated?
For a probability distribution \( P = \{p_1, p_2, \dots, p_n\} \), the Shannon entropy \( H(P) \) is calculated as:
\[
H(P) = -\sum_{i=1}^n p_i \log p_i
\]
- \( p_i \): Probability of the \( i \)-th word in the vocabulary.
- \( \log \): Natural logarithm.

---

## How Shannon Entropy Affects Text Generation

### 1. **Controlling Diversity and Coherence**
- **High Entropy**: Encourages **diversity** by exploring a wider range of possible words, including less probable ones. This leads to more creative and varied text.
- **Low Entropy**: Encourages **coherence** by favoring high-probability, predictable words. This leads to more structured and logical text.

### 2. **Dynamic Sampling**
- At each step of text generation, the model outputs a probability distribution over the vocabulary.
- The Shannon entropy of this distribution is calculated.
- Based on a **target entropy** value, the sampling process is adjusted:
  - If the entropy is **lower than the target**, the distribution is flattened to encourage diversity.
  - If the entropy is **higher than the target**, the distribution is sharpened to encourage coherence.

### 3. **Trade-Off Between Creativity and Structure**
- **Low Target Entropy**: Generates coherent but potentially repetitive text.
- **High Target Entropy**: Generates diverse but potentially less coherent text.

---

## Features

- **Entropy-Controlled Sampling**: Adjusts text generation based on Shannon entropy to balance diversity and coherence.
- **Evaluation Metrics**: Measures text quality using **Distinct-n**, **Repetition Rate**, and **Perplexity**.
- **Flexible and Customizable**: Works with any Hugging Face language model.

---

## Installation

1. Clone the repository.
2. Install the required dependencies using the provided `requirements.txt` file.

---

## Usage

1. **Load a Pre-Trained Model**: Use Hugging Face's `transformers` library to load a language model and tokenizer.
2. **Generate Text**: Use the entropy-controlled text generation function to create text with varying levels of diversity and coherence.
3. **Evaluate Text**: Analyze the generated text using metrics like Distinct-n, Repetition Rate, and Perplexity.

---

## Evaluation Metrics

- **Distinct-n**: Measures the diversity of n-grams in the generated text.
- **Repetition Rate**: Measures how often n-grams are repeated.
- **Perplexity**: Measures how well the model predicts the text (lower is better for coherence).

---

## Applications

- **Creative Writing**: Generate diverse and engaging stories, poems, or scripts.
- **AI Content Generation**: Create coherent and contextually relevant content for blogs, articles, or marketing.
- **Adaptive Conversational Agents**: Fine-tune chatbot responses for better user interaction.

---

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

---


## Acknowledgments

- Built using Hugging Face's `transformers` library.
- Inspired by research on entropy-controlled sampling and text generation.

---
