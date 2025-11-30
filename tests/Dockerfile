FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY src/ ./src/
COPY tests/ ./tests/

CMD ["python", "-m", "pytest", "tests/", "-v"]
```
4. **Commit message**：
```
feat: add Dockerfile for containerization
```
5. ** "Commit new file"**

---

### 3 .dockerignore

1. "Add file" → "Create new file"**
2. .dockerignore`
3. content：
```
__pycache__/
*.pyc
*.pyo
*.pyd
.Python
*.so
*.egg
*.egg-info/
dist/
build/
.pytest_cache/
.coverage
htmlcov/
.git/
.github/
screenshots/
*.md
```


