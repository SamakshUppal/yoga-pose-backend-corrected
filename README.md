# YogaPoseBackend (Final Fixed)

## Fix Applied
- Fixed issue where landmarks in DB were empty due to double JSON encoding.
- Now backend checks if landmarks are already a string; only converts when needed.

## Quickstart
```bash
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
python app.py
```
