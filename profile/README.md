# Premove AI

Premove AI is an open-source effort to reduce end-to-end latency in
conversational voice AI. We build practical infrastructure for real-time voice
agents, with a focus on making the path from speech to reliable action faster,
more efficient, and easier to run.

Premove ITN is our first public project. More open-source infrastructure for
conversational voice AI is in development and coming soon.

## Premove ITN

Premove ITN is an open-source, context-aware inverse text normalization library
for conversational voice-agent transcripts, with open weights. It converts
spoken ASR output into written forms for phone numbers, email addresses,
identifiers, dates, times, money, measurements, and alphanumeric codes.

```text
the room code is one oh five  →  the room code is 105
```

Premove ITN separates normalization into three steps: deterministic Rust
candidate generation, contextual scoring with one DeBERTa encoding, and exact
dynamic-programming decoding.

Install the Python package:

```bash
pip install premove-itn
```

```python
from premove_itn import PremoveITN

itn = PremoveITN.from_pretrained()
print(itn.normalize("the room code is one oh five"))
# the room code is 105
```

On the frozen 400-row voice-agent benchmark, Premove ITN reached 99.50%
semantic accuracy (398/400). The benchmark was held out from training and
checkpoint selection. It is a synthetic stress benchmark, not a sample of live
production traffic.

- [Source code and documentation](https://github.com/premove-ai/premove-itn)
- [Python package](https://pypi.org/project/premove-itn/)
- [Open model weights](https://huggingface.co/premove-ai/premove-itn)
- [Benchmark report](https://github.com/premove-ai/premove-itn/blob/main/eval/voice_agent_itn/results/first-evaluation/REPORT.md)
- [Architecture](https://github.com/premove-ai/premove-itn/blob/main/docs/architecture.md)
