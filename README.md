# Model Testing

A place where I put the models I mess around with.

## TinyLLM — own 5.6M model (Oct 24, 2026)

Trained from scratch on TinyStories with Karpathy's llama2.c on a Kaggle Tesla T4 — not fine-tuned.

- **Loss:** 10.39 (near random) → 1.75 train / 1.76 val over 10,000 steps (~82M tokens)
- **Config:** dim 144, 4 layers, 4 heads, max seq len 128, batch 32, grad accum 2, lr 1e-3, float32
- **Finding:** grammar arrived by 5.6M params; holding onto an entity did not. More params bought entity preservation first, then story structure. Temperature changed how the model picked, not what it knew.

## Files

- `tinyllm-own-5m-10k-2026-10-24-model_0_mk7m.bin` — the model checkpoint (22 MB)
- `tokenizer.bin` — tokenizer (required for local `./run`, keep this exact name)
- `tinyllm-5m-10k-2026-10-24-summary.pdf` — full training notes, samples, and the 5.6M vs 15M vs 42M comparison
