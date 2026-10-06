# copilot-training

## What it does

Learning Coach: turns SOPs and manuals into explanations, quizzes, fault scenarios and personalised training.

Part of the **department-copilots** suite: local-only copilots where the employee provides the input, Claude analyses it on the machine, and the employee decides what to do. No CRM, NMS, email or system integrations.

## Install

```bash
claude plugin marketplace add sara-hamza/department-copilots
```

```bash
claude plugin install training@department-copilots
```

Drop in the approved SOP, training manual or vendor guide (PDF, DOCX or pasted text) and get coached from it: structured explanations with checks for understanding, quizzes that withhold answers until you try, realistic fault scenarios revealed step by step, and a review of your answer against the material.

| Command | Use when |
|---|---|
| `/training:teach <topic> [from the dropped material]` | "Teach me": structured explanation from the supplied material only, with checks for understanding |
| `/training:quiz <topic> [n:5] [format:mcq|short|scenario]` | "Quiz me": N questions, answers withheld until you answer, then feedback |
| `/training:scenario <type: gpon-fault|provisioning|customer-case> [difficulty]` | "Give me a fault scenario": realistic NOC or field scenario, worked step by step, coach reveals progressively |
| `/training:review-answer <your answer> [to: question or scenario]` | "Where did I go wrong": CORRECT / MISSING / INCORRECT / WHERE TO READ against the material |

Requires `copilot-common` (document-reader for PDFs and DOCX).

The coach teaches only from what you supply. If the material does not cover something, it says so rather than filling the gap from general knowledge. It never gives the answer before you have tried.

Reference knowledge lives in `skills/learning-coach/references/`. company-specific thresholds, platforms and the approved material list are marked `CUSTOMISE`.
