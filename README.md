<h1 align="center">Md Miftahul Hoda Khan </h1>
<div align="center">

<h3>AI evaluation · task and verifier authoring · backend engineering</h3>

<br/>

<img src="https://readme-typing-svg.demolab.com?font=Courier+Prime&weight=700&size=38&duration=3000&pause=1000&color=FFFFFF&center=true&vCenter=true&width=750&height=90&lines=%3E+I+make+agents+prove+it." alt="I make agents prove it." />

<br/><br/>

<p>
I turn domain problems into executable benchmark tasks: the environment, the<br/>
reference solution and the scorer, across data engineering, STEM and CFD.
</p>

<br/>

<a href="https://linkedin.com/in/md-miftahul-hoda-khan-9621b1249">
<img src="https://img.shields.io/badge/LINKEDIN-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>

<a href="https://github.com/Miftahul87">
<img src="https://img.shields.io/badge/GITHUB-181717?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="https://github.com/Miftahul87?tab=repositories">
<img src="https://img.shields.io/badge/OPEN_SOURCE-333333?style=for-the-badge&logo=github&logoColor=white"/>
</a>

</div>

---

## Benchmark & evaluation work

My day job is adversarial: take a domain problem, turn it into an executable task, then build the
scorer that decides whether an agent genuinely solved it or merely looked like it did.

| Where | Benchmark | What |
| --- | --- | --- |
| **Handshake AI** · Project Dynamo | Terminal-Bench 2 | Benchmark task development, authoring tasks that evaluate AI agents working in terminal environments. |
| **Handshake AI** · Project Insight | Terminal-Bench 4 | Benchmark task development, hands-on across task authoring and grading agent output. |
| **Handshake AI** · Project LUMIERE | STEM (Engineering) | Engineering-domain task authoring, where a correct answer has to come from the underlying physics rather than from pattern-matching the prompt. |
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
reference solution, and a scorer strict enough that a plausible-looking wrong answer still fails.-


<!-- activity:end -->

---

## Projects

### 01 / Incident Engineer

**Agentic Root-Cause Debugging**

[GitHub Repository](https://github.com/Miftahul87/incident-engineer-)

- Built a two-agent debugging system with a triage agent and an investigator agent.

- Implemented tool-based investigation using logs, grep, test execution and sandboxed Python.

- Designed a verification gate that accepts fixes only after the complete test suite passes.

- Evaluated against 11 incidents: 11/11 resolved compared with 0/11 for the single-prompt baseline.

- Average execution: approximately 5 minutes and $0.0079 per task.

### 02 / Cloud-Native DevOps

**Infrastructure & Deployment Platform**

[GitHub Repository](https://github.com/Miftahul87/cloud-native-devops-)

- Provisioned AWS infrastructure using Terraform.

- Configured VPC, public subnet, security groups and EC2.

- Containerized the application using Docker.

- Configured Nginx as a reverse proxy.

- Implemented automated build and deployment using GitHub Actions.

### 03 / LLM Strategy Agent

**Strategy Generation & Evaluation Harness**

[GitHub Repository](https://github.com/Miftahul87/llm-strategy-agent)

- Built a sandboxed LLM pipeline converting natural-language trading ideas into executable strategy code.

- Implemented static validation and automatic provider failover.

- Developed a 39-case evaluation harness with hidden test data and look-ahead bias detection.

- Recorded 92% pass rate for GPT-OSS-120B versus 28% for Qwen2.5-Coder 7B.

- Built a Numba-based backtesting engine processing 25,000 parameter combinations in under one second.
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

## Find me

[LinkedIn](https://linkedin.com/in/md-miftahul-hoda-khan-9621b1249) · [GitHub](https://github.com/Miftahul87) · [mdmiftahulhodakhan@gmail.com](mailto:mdmiftahulhodakhan@gmail.com)

**B.Tech Noida Institute of Engineering and Technology, Greater Noida, 2026**
 
