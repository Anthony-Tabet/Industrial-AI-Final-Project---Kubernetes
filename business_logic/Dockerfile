FROM python:3.11.8

# Set working directory
WORKDIR /app

# Install system dependencies
# RUN apt-get update && apt-get install -y \
    # libgl1-mesa-glx ffmpeg libsm6 libxext6

# Copy requirements file
COPY requirements.txt .

# Install Python dependencies
RUN pip install -r requirements.txt

# Copy your application code
COPY . /app

# Expose any necessary ports
EXPOSE 5000

# Command to run your application
CMD ["python", "app.py"]
