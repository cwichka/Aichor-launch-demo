FROM rayproject/ray:2.36.1-py39-gpu
WORKDIR /app

ENV TZ=Europe/Paris
ENV LANG=C.UTF-8 PYTHONDONTWRITEBYTECODE=1 PYTHONUNBUFFERED=1

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt && \
    pip cache purge && \
    find /usr/local/lib/python3.9 -type d -name __pycache__ -exec rm -r {} + 2>/dev/null || true && \
    find /usr/local/lib/python3.9 -name "*.pyc" -delete

COPY main.py .
