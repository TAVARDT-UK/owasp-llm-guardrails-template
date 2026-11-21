# OWASP LLM01 Guardrails Template & AI Security Blueprint | TAVARDT UK

[![Licence MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![OWASP LLM01](https://img.shields.io/badge/OWASP-LLM01%20Hardened-ff0055.svg)](https://owasp.org/www-project-top-10-for-large-language-model-applications/)
[![Language](https://img.shields.io/badge/Language-English%20(UK)-green.svg)](README.md)
[![AI Diagnostics](https://img.shields.io/badge/TAVARDT-AI%20Evaluator-5b3cf5.svg)](https://tools.tavardt.com/uk/llm-robustness-evaluator/)

Production-grade open source middleware and defence blueprint for mitigating Prompt Injection (OWASP LLM01), system prompt extraction, and adversarial jailbreaks, aligned with UK NCSC AI Security Guidelines and UK GDPR.

Engineered and maintained by the AI safety and security engineering practice at **[TAVARDT UK](https://ag.tavardt.com/uk/super-intelligence/)**.

---

## 1. AI Security Architecture Overview

This repository provides a modular, dependency-light security middleware delivering deterministic **guardrails** for autonomous agents, RAG workflows, and enterprise applications interfacing with foundational LLMs (OpenAI, Anthropic, Gemini, Llama).

### Essential Protection at the Application Boundary
Foundation models do not intrinsically distinguish privileged system guidelines from untrusted user inputs. Lacking rigorous boundary enforcement, conversational agents and automated reasoning systems risk context override, proprietary IP disclosure, and arbitrary tool triggering.

---

## 2. Threat Vectors Addressed (OWASP Top 10 for LLMs)

| Defence Layer | Threat Vector Mitigated | Protection Mechanism |
| :--- | :--- | :--- |
| **Input Sanitiser** | Direct Prompt Injection & Jailbreaks | Pre-execution pattern detection intercepting contextual escape syntax (`ignore instructions`, adversarial roleplay). |
| **Canary Token Verifier** | System Prompt Exfiltration | Detection of embedded canary tokens in responses to prevent internal prompt leaks. |
| **RAG Boundary Guard** | Indirect Prompt Injection | Isolation of untrusted external content retrieved from document indexes and vector stores. |
| **Structured Output Filter** | Unauthorised Tool Dispatch | Schema validation for function calls and MCP tools prior to execution. |

---

## 3. Pre-Deployment AI Robustness Audit

Benchmark your conversational systems and AI pipelines against adversarial techniques before releasing to production:

* **AI Robustness Check:** [TAVARDT UK LLM Robustness Evaluator](https://tools.tavardt.com/uk/llm-robustness-evaluator/)
* **Complete Diagnostic Platform:** [TAVARDT Tools UK](https://tools.tavardt.com/uk/)

---

## 4. Installation & Implementation Instructions

### Clone & Execução

```bash
git clone https://github.com/TAVARDT-UK/owasp-llm-guardrails-template.git
cd owasp-llm-guardrails-template
python examples/quickstart.py
```

### Exemplo de Integração

```python
from guardrails.validator import LLMGuardrail

guard = LLMGuardrail()

# 1. Validação de Ingress (Input Guardrail)
is_safe, error = guard.validate_input(user_input)
if not is_safe:
    raise ValueError(f"Blocked input: {error}")

# 2. Injeção de Canary no Prompt de Sistema
hardened_system_prompt = guard.get_canary_injection_prompt(system_prompt)

# 3. Validação de Egress (Output Guardrail)
is_valid, leak_error = guard.validate_output(completion)
if not is_valid:
    raise SecurityError("System prompt leak detected!")
```

---

## 5. AI Security Advisory & Enterprise Agent Engineering

For organisations requiring comprehensive AI security audits, automated conversational agent safeguarding, or technical incident support:

* **Corporate Portal:** [TAVARDT UK](https://ag.tavardt.com/uk/super-intelligence/)
* **Technical Contact:** [Liaise with Engineering](https://ag.tavardt.com/uk/contact/)

---

## Licence

Distribuído sob a licença de código aberto MIT. Consulte o arquivo [`LICENSE`](LICENSE) para mais detalhes.  
Copyright (c) 2026 TAVARDT UK.
