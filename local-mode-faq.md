# Local Mode & Performance

## Short FAQ

### Why does local mode take longer?

Local analysis runs entirely on your machine for maximum privacy and control. Performance depends on your hardware and model size.

### How do I avoid timeouts?

Increase `NOOR_HTTP_TIMEOUT` or reduce `NOOR_ANALYZE_NUM_PREDICT`.

### When should I use cloud or Runpod?

Local mode is the recommended default.

Only consider cloud or Runpod if you need additional compute for very large files or are willing to trade off privacy for faster results.

## Local mode tuning

If analyses time out, increase `NOOR_HTTP_TIMEOUT`.

If output is too verbose or slow, reduce `NOOR_ANALYZE_NUM_PREDICT`.

Local models vary in speed depending on your hardware and model size.

---

## FAQ – Local mode & performance

### Why does local analysis take longer than cloud?

Local mode runs entirely on your machine using local LLMs (via Ollama).

This prioritizes **privacy, control, and data ownership**, but performance depends on:

- your hardware (CPU/RAM/GPU)
- model size
- file size and complexity

Cloud and Runpod environments may be faster for large files, but they require sending data to external compute.

---

### The analysis timed out – what should I do?

This usually means the local model needs more time or is generating too much output.

Try one of the following:

1. Increase timeout (more thinking time)  
2. Reduce max output (shorter responses)

Recommended starting point:

    export NOOR_HTTP_TIMEOUT=300
    export NOOR_ANALYZE_NUM_PREDICT=160

If it still times out, lowering output is often more effective than increasing timeout further.

---

### What do these parameters actually control?

- **NOOR_HTTP_TIMEOUT**  
  How long Noorlytics waits for the model to finish.

- **NOOR_ANALYZE_NUM_PREDICT**  
  How much text the model is allowed to generate.

In practice:

Timeout controls patience.  
Num predict controls verbosity.

---

### The output is too long or slow – how do I make it more concise?

Lower the max output:

    export NOOR_HTTP_TIMEOUT=300
    export NOOR_ANALYZE_NUM_PREDICT=160

This encourages shorter, more focused findings and improves local performance.

---

### What values should I use for larger or legacy files?

For larger files or legacy codebases:

    export NOOR_HTTP_TIMEOUT=600
    export NOOR_ANALYZE_NUM_PREDICT=220

Expect longer runtimes locally. This is normal.

---

### Which model should I use locally?

- Smaller models (e.g. 1.5B)  
  Faster and more stable on modest hardware.

- Larger models (7B+)  
  Better reasoning, but slower locally.

If you analyze large files often, consider:

- lowering output limits  
- using a smaller model  

Switching to Runpod or cloud should be a last resort if local performance is not sufficient and privacy is not a concern.

---

### When should I use Runpod or cloud mode instead?

Local mode is the default and recommended approach.

It keeps your code on your machine and gives you full control over your data.

Cloud or Runpod should only be used when you explicitly need more compute and are comfortable sending data to external services, for example:

- very large or complex codebases  
- batch processing across many files  
- situations where speed is more important than data control  

Most users stay local and only use cloud as a fallback when necessary.

---

### Is this instability a bug?

No. Local LLMs are inherently more sensitive to:

- input size  
- output length  
- available memory  

Noorlytics exposes tuning options so you can adapt to your environment instead of hiding these constraints.