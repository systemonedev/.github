# systemonedev

**Open tools and models for System One decision models**: models that answer typed questions about
your program's state (yes/no, pick one, rate on a scale) with calibrated probabilities, in
milliseconds, without generating text.

```python
from systemone import Client, Noul

r = Client("http://localhost:8093").system_one(
    state={"email": {"from": "security@paypa1-support.com", "body": "Verify your account within 24 hours..."}},
    questions={"phishing": Noul("Is this email a phishing attempt?")},
)
r.nouls["phishing"].noul    # 0.90: act, close, or ask a person
```

| | |
|---|---|
| 🧠 **[Kenning](https://huggingface.co/systemonedev/kenning-large-v0.4)** | An open System One model. Apache-2.0 weights, 435M parameters, runs on a ~2 GB GPU footprint or a CPU, with documented training data and published benchmarks. |
| 🛠️ **[SystemOne Builder](https://github.com/systemonedev/systemone-builder)** | Serve, train, distil and benchmark your own System One models on one GPU, from a dashboard or the command line. |
| 🐍 **[systemone-client](https://pypi.org/project/systemone-client/)** | One Python client for Kenning, Cloudflare's Clef and TypeSafe's Jev: same code, switch with a URL. |
| 📚 **[systemone.dev](https://systemone.dev)** | The community hub: concepts, cookbook patterns and end-to-end projects, with code that runs. |

### Get involved

- 💬 Questions and ideas: [Discussions](https://github.com/systemonedev/systemone-builder/discussions)
- 🧪 Most wanted: small, openly licensed, hand-labelled **benchmark suites** for new domains, and
  benchmarks from real workloads. See the [roadmap](https://systemone.dev/community/roadmap/).
- 🤝 [Contributing](https://systemone.dev/community/contributing/) ·
  [Code of conduct](https://github.com/systemonedev/.github/blob/main/CODE_OF_CONDUCT.md) ·
  [Security](https://github.com/systemonedev/.github/blob/main/SECURITY.md)

We publish where our models lose as well as where they win. Everything here is open source: code
under Apache-2.0 or MIT, Kenning weights under Apache-2.0.

<sub>Created and maintained by [David Rodriguez](https://github.com/jesusdrodriguez). Not affiliated
with TypeSafe AI or Cloudflare. Contact: systemonedev@gmail.com</sub>
