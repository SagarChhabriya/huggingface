## 🎯 **Essential Pipelines for Beginners**

### **1. Text Classification**
```python
# Sentiment Analysis
sentiment = pipeline("sentiment-analysis")
print(sentiment("I love this!"))

# Zero-Shot Classification
zero_shot = pipeline("zero-shot-classification")
print(zero_shot("This is a great movie", candidate_labels=["positive", "negative"]))

# Text Classification
classifier = pipeline("text-classification")
```

### **2. Text Generation**
```python
# Basic Text Generation
text_gen = pipeline("text-generation")
print(text_gen("Once upon a time"))

# Code Generation (if available)
code_gen = pipeline("text-generation", model="codeparrot/codeparrot-small")
```

### **3. Question Answering**
```python
# Extractive QA
qa = pipeline("question-answering")
context = "Hugging Face provides AI tools and models."
print(qa(question="What does Hugging Face provide?", context=context))
```

### **4. Translation**
```python
# English to French
en_fr = pipeline("translation_en_to_fr")
print(en_fr("Hello, how are you?"))

# English to German
en_de = pipeline("translation_en_to_de")
print(en_de("Good morning"))

# English to Spanish
en_es = pipeline("translation_en_to_es")
```

### **5. Summarization**
```python
summarizer = pipeline("summarization")
long_text = "Your long article here..."
print(summarizer(long_text, max_length=50))
```

### **6. Named Entity Recognition (NER)**
```python
ner = pipeline("ner", aggregation_strategy="simple")
text = "John works at Google in New York."
print(ner(text))
```

### **7. Feature Extraction**
```python
feature_extractor = pipeline("feature-extraction")
text = "Hello world"
embeddings = feature_extractor(text)
```

### **8. Fill-Mask**
```python
mask_filler = pipeline("fill-mask")
print(mask_filler("The weather is <mask> today."))
```

## 🌟 **Advanced but Beginner-Friendly**

### **9. Conversational AI**
```python
chatbot = pipeline("conversational")
# Note: This requires proper conversation format
```

### **10. Text2Text Generation**
```python
text2text = pipeline("text2text-generation")
print(text2text("translate English to French: Hello world"))
```

### **11. Image Classification**
```python
image_classifier = pipeline("image-classification")
# Requires PIL image
```

### **12. Automatic Speech Recognition (ASR)**
```python
speech_recognizer = pipeline("automatic-speech-recognition")
# Requires audio file
```

### **13. Text to Audio**
```python
text_to_speech = pipeline("text-to-speech")
# Converts text to audio
```

## 📚 **Complete Beginner's Cheat Sheet**

```python
from transformers import pipeline

# 🎯 MOST USEFUL FOR BEGINNERS:

# 1. Sentiment Analysis
sentiment = pipeline("sentiment-analysis")

# 2. Text Generation  
text_gen = pipeline("text-generation")

# 3. Question Answering
qa = pipeline("question-answering")

# 4. Translation
translator = pipeline("translation_en_to_fr")

# 5. Summarization
summarizer = pipeline("summarization")

# 6. Named Entity Recognition
ner = pipeline("ner")

# 7. Zero-Shot Classification
zero_shot = pipeline("zero-shot-classification")

# 8. Fill-Mask (Great for understanding how models work)
mask_filler = pipeline("fill-mask")
```

## 🚀 **Quick-Start Examples for Each**

```python
from transformers import pipeline

# 1. Quick Sentiment Check
print(pipeline("sentiment-analysis")("This is fantastic!"))

# 2. Creative Writing
print(pipeline("text-generation")("The future of AI", max_length=30))

# 3. Answer Questions
qa = pipeline("question-answering")
context = "The Eiffel Tower is in Paris, France."
print(qa(question="Where is the Eiffel Tower?", context=context))

# 4. Translate
print(pipeline("translation_en_to_fr")("Hello, world!"))

# 5. Summarize
text = "Long article about AI and machine learning..."
print(pipeline("summarization")(text, max_length=30))

# 6. Find Entities
ner = pipeline("ner", aggregation_strategy="simple")
print(ner("Apple was founded by Steve Jobs in California."))

# 7. Custom Classification
zero_shot = pipeline("zero-shot-classification")
print(zero_shot("I love this product", candidate_labels=["positive", "negative", "neutral"]))

# 8. Complete the Sentence
print(pipeline("fill-mask")("The capital of France is <mask>."))
```

## 🎪 **Fun & Educational Pipelines**

```python
# Poetry Generation
poet = pipeline("text-generation", model="gpt2")
print(poet("Roses are red,", max_length=20))

# Story Telling
storyteller = pipeline("text-generation")
print(storyteller("In a galaxy far away,", max_length=50))

# Code Explanation (using text generation)
coder = pipeline("text-generation")
print(coder("# Python function to calculate factorial", max_length=100))
```

## 🔧 **Practical Use Cases**

```python
# Email Sentiment Checker
emails = [
    "I'm very satisfied with your service!",
    "This product is terrible and broken.",
    "It's okay, could be better."
]
sentiment = pipeline("sentiment-analysis")
for email in emails:
    print(f"📧 {email} -> {sentiment(email)[0]}")

# Content Summarizer
articles = [
    "Long news article text here...",
    "Research paper abstract here..."
]
summarizer = pipeline("summarization")
for article in articles:
    summary = summarizer(article, max_length=30)[0]['summary_text']
    print(f"📰 Summary: {summary}")

# Language Translator
translations = [
    ("Hello, how are you?", "translation_en_to_fr"),
    ("Good morning", "translation_en_to_es"),
    ("Thank you", "translation_en_to_de")
]

for text, task in translations:
    result = pipeline(task)(text)[0]['translation_text']
    print(f"🌐 '{text}' -> '{result}'")
```

## 💡 **Teaching Tips for Each Pipeline**

### **Best for Absolute Beginners:**
1. **`sentiment-analysis`** - Instant gratification
2. **`text-generation`** - Fun and creative  
3. **`translation`** - Easy to understand concept
4. **`fill-mask`** - Shows how AI "thinks"

### **Intermediate Complexity:**
5. **`question-answering`** - Requires context understanding
6. **`summarization`** - Shows practical utility
7. **`ner`** - Introduces entity concepts
8. **`zero-shot-classification`** - Most flexible

### **Advanced but Cool:**
9. **`conversational`** - For chatbot projects
10. **`feature-extraction`** - For understanding embeddings

## 🛠️ **Troubleshooting Common Issues**

```python
# If you get memory errors, use smaller models:
sentiment = pipeline("sentiment-analysis", model="distilbert-base-uncased-finetuned-sst-2-english")

# If it's too slow, use CPU (default) or smaller batches:
results = sentiment(texts, batch_size=8)

# For long texts, they might need truncation:
results = sentiment(long_text, truncation=True)
```

## 📋 **Quick Reference Card**

```python
# Copy-paste this starter kit:
pipelines = {
    "sentiment": pipeline("sentiment-analysis"),
    "text_gen": pipeline("text-generation"),
    "translator": pipeline("translation_en_to_fr"),
    "qa": pipeline("question-answering"),
    "summarizer": pipeline("summarization"),
    "ner": pipeline("ner", aggregation_strategy="simple"),
    "zero_shot": pipeline("zero-shot-classification"),
    "mask_filler": pipeline("fill-mask")
}

# Use any pipeline:
result = pipelines["sentiment"]("I love AI!")
print(result)
```

These pipelines cover 95% of what beginners need and are perfect for:
- 🎓 Learning AI concepts
- 🚀 Building quick prototypes  
- 🎯 Understanding different NLP tasks
- 💡 Creating fun projects
