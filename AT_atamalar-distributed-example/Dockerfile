FROM pytorch/pytorch:2.0.1-cuda11.7-cudnn8-runtime

RUN pip install torch torchvision transformers datasets bitsandbytes peft

# Set the working directory 
WORKDIR /demo

# Copy the current directory contents into the container at /demo
COPY distributed.py launch.sh /demo/

# Create the checkpoint directory
RUN mkdir -p /demo/Meta-Llama-3.2-3B-Instruct-ONNX-INT4 && chmod -R 777 /demo/Meta-Llama-3.2-3B-Instruct-ONNX-INT4

# Run the bash file
RUN chmod u+x launch.sh
CMD ["./launch.sh"]
