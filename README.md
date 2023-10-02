# Download model weights

1. Install Git large file system (`git-lfs`)
  - [Github LFS](https://github.com/git-lfs/git-lfs/blob/main/INSTALLING.md)
  ```bash
  # Linuxmint 20.3 Una based on Ubuntu Focal
  curl -s https://packagecloud.io/install/repositories/github/git-lfs/script.deb.sh | os=ubuntu dist=focal sudo -E bash
  ```

- [llama github](https://github.com/facebookresearch/llama/blob/main/README.md)

1. Accept their license. [Meta AI](https://ai.meta.com/resources/models-and-libraries/llama-downloads/)

2. Request permission to meta-llama on [Huggingface](https://huggingface.co/meta-llama)
  - Each models

3. Clone the [llama repo](https://github.com/facebookresearch/llama)

```bash
cd bitsql-llm
git clone https://github.com/facebookresearch/llama.git
```

4. Install `llama`

```bash
cd llama # .../bitsql-llm/llama
pip3 install --upgrade pip wheel
pip3 install -e .
```

5. Download model and tokenizer at `llama` directory

```
git clone git@hf.co:meta-llama/Llama-2-7b-chat
```

6. Run `main_chat_completion.py`

```bash
cd .. # .../bitsql-llm
torchrun --nproc_per_node 1 main_chat_completion_cli.py --ckpt_dir ./Llama-2-7b-chat/ --tokenizer_path ./Llama-2-7b-chat/tokenizer.model --max_seq_len 512 --max_batch_size 6
```


