FROM python:3.11.8

# Set working directory
WORKDIR /app

# Install system dependencies
RUN apt-get update && apt-get install -y \
    libgl1-mesa-glx ffmpeg libsm6 libxext6

# Install PyTorch with CUDA support
RUN pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118

# Create necessary directories
RUN mkdir -p /app/road_traffic_sign_detection/static
RUN mkdir -p /app/road_traffic_sign_detection/model

# Set permissions for the directory
RUN chmod -R 777 /app/road_traffic_sign_detection/static
RUN chmod -R 777 /app/road_traffic_sign_detection/model

# Copy model file
COPY model/road_traffic_sign_detection_model.pt /app/road_traffic_sign_detection/model/

# Copy requirements file
COPY requirements.txt .

# Install Python dependencies
RUN pip install -r requirements.txt

# Copy your application code
COPY . /app

# Expose any necessary ports
EXPOSE 5003

# Command to run your application
CMD ["python", "app.py"]
