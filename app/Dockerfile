FROM python:3.8.12-slim-buster

EXPOSE $PORT
WORKDIR /app

RUN apt-get update && apt install -y \ 
    libgl1-mesa-glx \
    libglib2.0-0 && apt-get clean

RUN pip install --no-cache-dir \
    streamlit==1.7.0 \ 
    opencv-python-headless==4.5.5.62 \
    onnxruntime==1.10.0

ENV ENCODER_PATH ./src/encoder.onnx
ENV DECODER_PATH ./src/decoder.onnx

COPY . /app

CMD ["sh", "-c", "streamlit run --server.address=0.0.0.0 --server.port $PORT /app/app.py"]