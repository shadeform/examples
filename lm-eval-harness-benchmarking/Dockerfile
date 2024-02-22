# Use the huggingface/transformers-pytorch-gpu base image
FROM huggingface/transformers-pytorch-gpu:latest


VOLUME ~/.cache/huggingface /root/.cache/huggingface
# Set the working directory in the container to /app
WORKDIR /app

# Copy the setup script into the container
COPY ./setup.sh .

# Make the script executable
RUN chmod +x setup.sh

# Run the setup script
RUN ./setup.sh

#start the server
ENTRYPOINT lm_eval --model hf --model_args pretrained=$model --tasks $tasks --device cuda:0 --batch_size 8
