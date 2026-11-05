# UW Student Projects: Start Here

Welcome, University of Washington Bothell capstone students (Winter 2027). This page is the single starting point for contributing to HelloblueAI's open-source projects as part of the course.

## What the program is

HelloblueAI maintains four public, MIT-licensed repositories. During the capstone you claim one scoped GitHub issue (alone or as a pair), do the work in your own fork, and open a pull request that a maintainer reviews. Everything listed as **ready** below runs on a normal laptop: no private credentials, no production access, no paid services, no API keys, and no GPU.

## The four projects

| Project | What it is | Prerequisites |
| --- | --- | --- |
| [Bleu.js](https://github.com/HelloblueAI/Bleu.js) | Python library with local, offline examples | Python 3, pip, venv, pytest, Markdown |
| [Bleu.js Reasoning Lab](https://github.com/HelloblueAI/bleujs-reasoning-lab) | TypeScript lab that benchmarks reasoning and retrieval against fixed, committed datasets | Node.js >= 22.12, pnpm, TypeScript |
| [B01-NUna LoRA trainer](https://github.com/HelloblueAI/b01-nuna-lora-trainer) | Python LoRA/QLoRA fine-tuning trainer with an eval gate; tests, dry runs, and probe checks run on CPU | Python >= 3.10, pip, pytest, JSON |
| [HelloblueGK](https://github.com/HelloblueAI/HelloblueGK) | .NET 9 rocket-engine performance platform with an ideal-rocket nozzle solver validated against published engine data (not flight-certified software) | .NET 9 SDK, C#, xUnit; basic compressible-flow knowledge helps for the solver tasks |

## Set up each repository

Fork the repo on GitHub, clone **your fork**, then do the following:

**Bleu.js**
```bash
git clone https://github.com/<you>/Bleu.js.git && cd Bleu.js
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -e .
python examples/quick_start.py    # offline, no account or API key
```

**Bleu.js Reasoning Lab**
```bash
git clone https://github.com/<you>/bleujs-reasoning-lab.git && cd bleujs-reasoning-lab
pnpm install
pnpm run check   # format + lint + type-check + unit tests + offline eval harness
pnpm run eval    # offline benchmarks over fixed datasets
```
You do not need a model API key. Don't run `eval:model` unless an issue explicitly says to.

**B01-NUna LoRA trainer** (CPU only)
```bash
git clone https://github.com/<you>/b01-nuna-lora-trainer.git && cd b01-nuna-lora-trainer
python3 -m venv .venv && source .venv/bin/activate
pip install -e ".[dev]"
pytest
python -m b01_nuna_lora.train --dry-run
python -m b01_nuna_lora.eval --check-only
```
Skip the CUDA `torch` install line in the README. You only need it for GPU training.

**HelloblueGK**
```bash
git clone https://github.com/<you>/HelloblueGK.git && cd HelloblueGK
dotnet restore HelloblueGK.sln
dotnet build HelloblueGK.sln
dotnet test Tests/HelloblueGK.Tests.csproj --filter "FullyQualifiedName~IdealRocketNozzleTests"   # nozzle validation
```
For the nozzle solver, see `Physics/IdealRocketNozzle.cs`, `Physics/EngineOperatingPoint.cs`, `Physics/NozzleFlowSolver.cs`, and `Docs/Technical/VALIDATION_AND_BENCHMARKS.md`.

Before you open a PR, read the repo's `CONTRIBUTING.md`.

## How to claim an issue

1. Pick an issue from the **Ready now** table below that has no assignee.
2. Comment `Claiming this for UW` on it. Say whether you're working alone or as a pair, and give your partner's GitHub handle if you have one.
3. Wait until a maintainer assigns you before you start. Each issue goes to one student or one pair.
4. Fork the repo, make a branch, and open a pull request that says `Fixes #<number>`.
5. Post a short progress comment or a draft PR within 7 days. If an issue has no activity for 14 days, it may be released so someone else can take it.

You can hold one issue at a time. Once your PR is merged, you can claim another.

## Individual vs pair work

Every ready issue can be done by one student. Issues marked **pair** in the table are large enough for two people. If you work as a pair, open one PR with both names in the description, and split the work visibly (for example, one person writes the tests and the other writes the docs).

## GPU tasks are not open yet

Some NUna tasks need a real GPU training or evaluation run. They stay **conditional** until UW confirms students have access to an **NVIDIA GPU with at least 8 GB of VRAM**. Don't claim them until a maintainer posts on the issue that they are open. On GitHub they carry the `needs-gpu` label. Don't make up GPU results or error messages.

## Areas that are off-limits

Stay out of authentication/SSO, billing, API keys and secrets, rate limiting, HelloblueGK `Certification/`, and any HelloblueGK engine-safety or control code (valve shutdown, MPC control, sensor checks). Never commit credentials or secret values.

## Ready now

| Repo | Issue | Size |
| --- | --- | --- |
| Bleu.js | [#367 test: smoke test that runs examples/quick_start.py offline](https://github.com/HelloblueAI/Bleu.js/issues/367) | Individual |
| Bleu.js | [#368 docs: align ISSUE_LABELING_GUIDE.md with real labels](https://github.com/HelloblueAI/Bleu.js/issues/368) | Individual |
| Bleu.js | [#237 ci: markdown link check for docs and README](https://github.com/HelloblueAI/Bleu.js/issues/237) | Individual or pair |
| Reasoning Lab | [#93 test: committed model result files are internally consistent](https://github.com/HelloblueAI/bleujs-reasoning-lab/issues/93) | Individual |
| Reasoning Lab | [#94 eval: 95% confidence intervals for per-tier scores](https://github.com/HelloblueAI/bleujs-reasoning-lab/issues/94) | Pair |
| Reasoning Lab | [#71 completion tokens per correct hard-tier item](https://github.com/HelloblueAI/bleujs-reasoning-lab/issues/71) | Individual |
| Reasoning Lab | [#69 one hard retrieval query the word-overlap baseline misses](https://github.com/HelloblueAI/bleujs-reasoning-lab/issues/69) | Individual |
| NUna | [#33 test: CPU-only config guards in dpo.py](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/33) | Individual |
| NUna | [#7 licensed SFT examples under datasets/community/](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/7) (your own MIT-licensed text) | Individual |
| HelloblueGK | [#166 docs: Web API controller map in DEVELOPERS.md](https://github.com/HelloblueAI/HelloblueGK/issues/166) | Individual |
| HelloblueGK | [#88 docs: XML doc comments on one non-certification controller](https://github.com/HelloblueAI/HelloblueGK/issues/88) | Individual |
| HelloblueGK | [#85 docs: local Swagger UI screenshot](https://github.com/HelloblueAI/HelloblueGK/issues/85) | Individual |
| HelloblueGK | [#311 test: check IdealRocketNozzle against γ = 1.4 isentropic flow table values](https://github.com/HelloblueAI/HelloblueGK/issues/311) | Individual |
| HelloblueGK | [#312 docs: worked validation report vs a textbook example problem](https://github.com/HelloblueAI/HelloblueGK/issues/312) | Pair |
| HelloblueGK | [#313 test: convergence study for the ExitMachNumber bisection](https://github.com/HelloblueAI/HelloblueGK/issues/313) | Individual |
| HelloblueGK | [#314 docs: inputs and outputs reference for the nozzle solver](https://github.com/HelloblueAI/HelloblueGK/issues/314) | Individual |
| HelloblueGK | [#315 example: offline console example for one nozzle operating point](https://github.com/HelloblueAI/HelloblueGK/issues/315) | Individual or pair |

**Conditional (do not claim yet):** NUna [#10](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/10) and [#11](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/11) need an NVIDIA GPU with at least 8 GB of VRAM. NUna [#6](https://github.com/HelloblueAI/b01-nuna-lora-trainer/issues/6) has an earlier claim and opens only if a maintainer releases it.

## Where to ask questions

- For questions about a specific task, comment on that issue.
- For setup problems, open an issue in the relevant repo and start the title with `Question:`. Include your OS, the command you ran, and the full error.
- For course logistics, contact your UW instructor. A maintainer (@pejmantheory) reviews PRs and assigns issues.
