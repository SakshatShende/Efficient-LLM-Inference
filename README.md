#  Inference Optimization: LLaMA 3B

**Model**: `meta-llama/Llama-3.2-3B-Instruct`
**Assistant-Model**: `meta-llama/Llama-3.2-1B-Instruct`
**Hardware**: RTX 3090 (24 GB VRAM)  
**Prompt**: Single prompt with `max_new_tokens=50`, `prompt_lookup_num_tokens=5`  
**Precision**: FP16

| Mode                    | Inference Time ↓ | Peak GPU Memory ↓ |
|-------------------------|------------------|--------------------|
|  **Base Only**         | `1.734 s`         | `8507.54 MB`       |
|  **Speculative Decoding** | `1.428 s`      | `8532.89 MB`       |
|  **Prompt Lookup**     | `1.455 s`         | `8517.05 MB`       |

 Results measured using Hugging Face Transformers with `generate()` + timing + `torch.cuda.max_memory_allocated()`.

---

![Graph(18)](https://github.com/user-attachments/assets/056ee3c7-2fbf-4ded-af50-ca8ba7f36754)
