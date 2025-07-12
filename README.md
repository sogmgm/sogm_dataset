# sogm_dataset
datasets for train



## Event Sentence Dataset

**Format:** JSON Lines (`event_dataset.jsonl`)  
**Encoding:** UTF-8  
**Columns:**  
- `doc_id`
- `doc_title`
- `text`
- `text_category`
- `event_quantity`
- `event_sentence1`, `event_sentence2`, ...
- 
### Example
| doc_id | doc_title | event_sentence1 | event_sentence2 |
|--------|-----------|-----------------|-----------------|
| 7781   | 강남·송파... | 17일 한국부동산원에 따르면... | 경기 지역 역시 재건축... |

```json
{"doc_id": 7781, "doc_title": "강남·송파...", "event_sentence1": "17일 한국부동산원에 따르면...", "event_sentence2": "경기 지역 역시 재건축..."}
```
### How to load
#### Python (pandas)
import pandas as pd
df = pd.read_json('event_dataset.jsonl', lines=True, encoding='utf-8')
print(df.head())

#### Python (json)
import json
with open('event_dataset.jsonl', encoding='utf-8') as f:
    data = [json.loads(line) for line in f]

### Remote loading example
url = 'https://raw.githubusercontent.com/yourusername/yourrepo/main/event_dataset.jsonl'
df = pd.read_json(url, lines=True, encoding='utf-8')

### License
CC BY-NC 4.0


