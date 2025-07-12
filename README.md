# SOGM Dataset

This document provides details about the **Event Sentence Dataset**, its format, structure, and how to load it for training purposes.

---

## Event Sentence Dataset

### **File Format**
- **File Type:** JSON Lines (`event_dataset.jsonl`)  
- **Encoding:** UTF-8  

### **Columns**
- `doc_id`: Document ID  
- `doc_title`: Title of the document  
- `text`: Full text of the document  
- `text_category`: Category of the text  
- `event_quantity`: The number of event sentences in the document  
- `event_sentence1`, `event_sentence2`, ...: Sentences related to events  

---

### **Example**

| doc_id | doc_title  | event_sentence1                 | event_sentence2              |
|--------|------------|---------------------------------|------------------------------|
| 7781   | 강남·송파... | 17일 한국부동산원에 따르면... | 경기 지역 역시 재건축...    |

**JSON Representation**:
```json
{
  "doc_id": 7781,
  "doc_title": "강남·송파...",
  "event_sentence1": "17일 한국부동산원에 따르면...",
  "event_sentence2": "경기 지역 역시 재건축..."
}
```

---

### **How to Load the Dataset**

#### Using `pandas`
```python
import pandas as pd

df = pd.read_json('event_dataset.jsonl', lines=True, encoding='utf-8')
print(df.head())
```

#### Using `json`
```python
import json

with open('event_dataset.jsonl', encoding='utf-8') as f:
    data = [json.loads(line) for line in f]
```

#### Remote Loading Example
```python
url = 'https://raw.githubusercontent.com/yourusername/yourrepo/main/event_dataset.jsonl'
df = pd.read_json(url, lines=True, encoding='utf-8')
```

---

### **License**
This dataset is released under the **CC BY-NC 4.0** license.

---
