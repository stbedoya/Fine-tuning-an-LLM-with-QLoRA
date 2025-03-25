# Fine-tuning-an-LLM-with-QLoRA

For this tutorial, we’ll fine-tune the Llama 3 8B-Instruct model using the ruslanmv/ai-medical-chatbot dataset. The dataset contains 250k dialogues between a patient and a doctor. QLoRA stands for Quantized Low-Rank Adapter, and it's a method introduced to fine-tune LLMs models using much less GPU memory - without sacrificing much performance.

QLoRA combines two main ideas:

    Quantization (specifically 4-bit)
        It loads the base model weights in 4-bit precision instead of 16- or 32-bit.
        This saves massive amounts of VRAM (e.g., you can fine-tune LLaMA 13B on a single 24GB GPU).

    LoRA (Low-Rank Adaptation)
        Instead of updating all model weights, LoRA freezes them and adds small trainable "adapter" layers.
        These adapters inject learnable parameters into the model — they’re fast and cheap to train.

