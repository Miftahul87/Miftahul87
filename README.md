<h1 align="center">Md Miftahul Hoda Khan </h1>




---

## Benchmark & evaluation work

My day job is adversarial: take a domain problem, turn it into an executable task, then build the
scorer that decides whether an agent genuinely solved it or merely looked like it did.

| Where | Benchmark | What |
| --- | --- | --- |
| **Handshake AI** · Project Dynamo | Terminal-Bench 2 | Benchmark task development, authoring tasks that evaluate AI agents working in terminal environments. |
| **Handshake AI** · Project Insight | Terminal-Bench 4 | Benchmark task development, hands-on across task authoring and grading agent output. |
| **Handshake AI** · Project LUMIERE | STEM (Engineering) | Engineering-domain task authoring, where a correct answer has to come from the underlying physics rather than from pattern-matching the prompt. |
| **Mercor** | Real World Engineering | Data Engineering task author for long-horizon engineering tasks. |
| **Chegg** | STEM (Computer Science) | Subject matter expert and STEM task author in computer science, writing and reviewing worked solutions that have to be correct end to end rather than plausible. |
| **Alignerr** | | CFD task design on **OpenFOAM**, turning simulation problems into checkable engineering tasks. |
| **Ethara AI** · onsite | | LLM post-training. |

**Domains I have authored in:** data engineering · STEM and engineering · computer science · computational fluid dynamics

### What a task package actually contains

The problem statement is the easy part. A task is only usable as an eval when all five pieces hold
together:

| Piece | Why it decides whether the task is worth anything |
| --- | --- |
| **Runnable environment** | Containerised and deterministic. If it drifts between runs, every score it produces is noise. |
| **Instructions** | Unambiguous about the goal and silent about the method, or you are testing reading comprehension instead of engineering. |
| **Automated scorer** | Checks the outcome, not the shape of the output. String-matching a solution grades style, not correctness. |
| **Reference solution** | Proves the task is solvable at all, and sets the ceiling the scorer must award full marks to. |
| **Validation evidence** | Shows the whole thing behaves: reference scores full, a no-op scores zero, and the gap between them is real. |

### How I calibrate

A task that every agent passes measures nothing, and one that nothing can pass is usually a broken
verifier rather than a hard problem. So the first job after building is to attack my own task:

- **Both ends pinned.** The reference solution must score full marks and a do-nothing attempt must
  score zero. If the no-op scores above zero, the scorer is reading something it should not.
- **Near-misses must fail.** A plausible, confidently-wrong answer is the case that matters. If it
  passes, the scorer is checking appearance rather than outcome.
- **Hidden cases stay hidden.** Grading assets and expected outputs live outside the environment the
  agent can see. An agent that can read the answer key is not being evaluated.
- **Failure analysis separates causes.** When an agent fails, the question is whether it reasoned
  badly, whether the verifier is wrong, or whether the infrastructure broke. Grading agent output at
  Handshake is mostly this: reading trajectories and telling those three apart.

The part that matters is not the problem statement. It is the environment that runs reproducibly, the
reference solution, and a scorer strict enough that a plausible-looking wrong answer still fails.

---

## Open source: found by reading the code

My contributions to [**BasedHardware/omi**](https://github.com/BasedHardware/omi), the Python CLI for
the Omi wearable, are all the same shape: a defect nobody had reported, found by reading the code,
fixed in one narrow diff, and shipped with the regression test that fails without it. The live list
below is generated from the GitHub API, so it is current rather than something I remembered to update.

Four of them, to show what that means in practice:

- An IPv4-mapped address slipped past the webhook delivery check, so `omi app webhook verify` printed
  **pass** for a URL the backend silently drops. The rule was written for one spelling of an address
  and `::ffff:100.64.0.1` is another.
- A 429 reported the rate-limit policy as its own budget, `dev:ask (dev:ask)`, because the lookup
  defaulted to its own key. The table held 3 of the 16 policies the backend actually defines, so this
  fired on most real rate limits.
- An unreadable config file crashed **every** command, `omi version` included, and left the guard
  that protects it disarmed. The function documented the opposite behaviour; the file open just sat
  outside the `try`.
- `b64decode(validate=True)` rejects newlines, so a line-wrapped screenshot payload, which is what
  every MIME encoder produces, was refused as corrupt data.

> A maintainer on #13192: *"clean, narrow change with genuinely good test coverage."*

**Terminal-Bench task: legacy ledger migration.**
[A task I authored](https://github.com/harbor-framework/terminal-bench/pull/1908): a Python 2.7 batch
ledger system ported to Python 3 **byte-exactly**. BAI, CSV and fixed-width ingest, a reconciliation
engine, a Docker environment, and a scorer running 16 hidden input corpora against golden outputs.
276 files.

---


<!-- activity:end -->

---

## Projects

**[incident-engineer](https://github.com//incident-engineer)** - two agents that find and fix
real bugs. A fix is only accepted once the full test suite passes. **11 of 11** incidents resolved,
against **0 of 11** for a single-prompt baseline. The gate is the point: the agent does not get to
declare its own success.

---

## Stack

| | |
| --- | --- |
| **Languages** | Python · Java · SQL · JavaScript |
| **Backend** | FastAPI · Spring Boot · Django REST · REST API design |
| **Data** | PostgreSQL · MySQL · MongoDB |
| **Infra** | Docker · GitHub Actions · Terraform · AWS (EC2, VPC) · Linux |
| **Evaluation** | Task and verifier design · reproducible environments · scorer calibration · failure analysis |
| **Simulation** | OpenFOAM · CFD task design |

### Currently learning

Kubernetes · CUDA and GPU kernel profiling · Lean 4 for certificate-based verification · distributed
data processing at scale

---
 Noida Institute of Engineering and Technology, 2026
