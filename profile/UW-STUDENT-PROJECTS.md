# UW Student Projects: Start Here

This page is the assignment list for University of Washington students working with Helloblue's public repositories. Claim **one** issue, alone or with one partner. Two people may share an issue. Two people may not work the same issue separately.

University of Washington GPU access is unconfirmed. The assignments below do not need a GPU. Tasks that need CUDA are listed at the end and are not open to claim.

These repositories are public workshop and research code. The LoRA trainer is not the production NUna system. Production NUna is described only at [helloblue.ai/model-card](https://helloblue.ai/model-card).

## How to submit

1. Comment on the issue: `Claiming this for UW`, and name your partner if you have one.
2. If someone else already claimed it, pick a different issue.
3. Fork the repository named in the issue. Create a branch. Change only what that issue asks for.
4. Open a pull request that links the issue (`Fixes #NUMBER`).
5. Do not commit secrets, `.env` files, API keys, or model weights.

A maintainer reviews the pull request. Commenting on the issue does not by itself merge your work.

## Ready to claim

Ten assignments. Each one has a single expected result so two groups do not submit the same change.

| # | Project | Issue | Expected result | Skills and tools | GPU | Data license |
| --- | --- | --- | --- | --- | --- | --- |
| 1 | [LoRA trainer](https://github.com/HelloblueAI/b01-nuna-lora-trainer) | [#6 Add generalization probes](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/6) | Three to five new advisory probes that are not paraphrases of `datasets/train.json`. `eval --check-only` passes. | Python, JSON, regular expressions | No | Original probe text only |
| 2 | [LoRA trainer](https://github.com/HelloblueAI/b01-nuna-lora-trainer) | [#7 Licensed community SFT](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/7) | One new JSON file under `datasets/community/` of your own MIT-licensed chat rows. Do not edit `datasets/train.json`. | Python or a text editor, JSON | No | Required. Say MIT and that the rows are your original work |
| 3 | [LoRA trainer](https://github.com/HelloblueAI/b01-nuna-lora-trainer) | [#33 CPU tests for DPO config guards](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/33) | `tests/test_dpo_config.py` with the four cases in the issue, passing on CPU with no download | Python, pytest | No | None |
| 4 | [Reasoning lab](https://github.com/HelloblueAI/bleujs-reasoning-lab) | [#93 Result-file consistency tests](https://github.com/HelloblueAI/bleujs-reasoning-lab/issues/93) | A test that the committed model result JSON files match their own schema and totals | TypeScript, the repo's test runner | No | None. Do not add model outputs |
| 5 | [Reasoning lab](https://github.com/HelloblueAI/bleujs-reasoning-lab) | [#69 One hard retrieval item](https://github.com/HelloblueAI/bleujs-reasoning-lab/issues/69) | One new hard retrieval item that the word-overlap baseline ranks wrong, plus the test the issue names | TypeScript. No API key | No | Original passages you write |
| 6 | [Bleu.js](https://github.com/HelloblueAI/Bleu.js) | [#367 Offline quick-start smoke test](https://github.com/HelloblueAI/Bleu.js/issues/367) | A test that runs `examples/quick_start.py` with no network and no API key | Python, pytest | No | None |
| 7 | [Bleu.js](https://github.com/HelloblueAI/Bleu.js) | [#236 Server environment variables](https://github.com/HelloblueAI/Bleu.js/issues/236) | A short table in `docs/INSTALLATION.md` of the `[server]` variables already named in `.env.example` | Markdown. Read `.env.example`. Do not invent variables or paste secret values | No | None |
| 8 | [Bleu.js](https://github.com/HelloblueAI/Bleu.js) | [#368 Label guide matches the repo](https://github.com/HelloblueAI/Bleu.js/issues/368) | `.github/ISSUE_LABELING_GUIDE.md` lists the labels that exist, and no labels that do not | Markdown, `gh label list` | No | None |
| 9 | [HelloblueGK](https://github.com/HelloblueAI/HelloblueGK) | [#166 Web API controller map](https://github.com/HelloblueAI/HelloblueGK/issues/166) | One table in `DEVELOPERS.md` mapping the controllers named in the issue | Markdown. Reading C# is enough. This is not flight software and not a certification task | No | None |
| 10 | [HelloblueGK](https://github.com/HelloblueAI/HelloblueGK) | [#88 XML docs for HealthController](https://github.com/HelloblueAI/HelloblueGK/issues/88) | XML `<summary>`, `<param>`, and `<returns>` on the public actions of `HealthController` only | C# and .NET 9 | No | None |

## Waiting on a GPU

Do not claim these until a maintainer comments that a GPU is available. University of Washington GPU access is not confirmed.

| Project | Issue | Why it waits |
| --- | --- | --- |
| [LoRA trainer](https://github.com/HelloblueAI/b01-nuna-lora-trainer) | [#10 Promote probes to required](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/10) | Needs a generation eval on an NVIDIA GPU |
| [LoRA trainer](https://github.com/HelloblueAI/b01-nuna-lora-trainer) | [#11 Document a real CUDA failure](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/11) | Needs an error you actually hit on a GPU. Do not invent one |

Project descriptions live in each repository's README. The issue you claim is the assignment. If an issue's instructions and this table disagree, follow the issue and say so in the pull request.
