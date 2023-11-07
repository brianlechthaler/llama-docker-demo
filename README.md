# `llama-docker-demo`
This repository contains a basic demonstration of text generation with LLMs such as Llama.
Please keep in mind that this is not a "reference implementation", and should never be used in production.
## Prerequisites
* Docker
* NVIDIA Container Toolkit
* At least 140GB VRAM (on one or more GPUs)
* NVIDIA Drivers and CUDA

## Quickstart
1. Clone this repository: `git clone https://github.com/brianlechthaler/llama-docker-demo.git`
2. Change directory to cloned repository: `cd llama-docker-demo`
3. Build Docker Image: `docker build -t llama-docker-demo .`
4. Run docker image: `sudo docker run --gpus=all --cap-add SYS_RESOURCE -e USE_MLOCK=0 -e MODEL=/var/model/ggml-model-f16.gguf -v /path/to/folder/with/your/gguf/model/:/var/model -ti stream_test "what is a hello world?"`
   * You must replace `/path/to/folder/with/your/gguf/model/` with the path to your `gguf` model in order for this to work.
   * You can replace `"what is a hello world?"` with whatever prompt you want.