# HW4 — Short Answers

Answer each question in 2–3 sentences.

## 1. Rolling-update safety
Why does the Deployment use `maxUnavailable: 0`, and what would change if it were `maxUnavailable: 1`?

This means Kupernetes is allowed to take a maximum of zero pods down while while updating. Having this at 0 does slow the process down a bit, but it maintains consistent availability, which 1 wouldn't.

## 2. Health probes
Why do the liveness/readiness probes target `/health` instead of `/predict`?

Health checks for the basic health of the model and is easier/quicker to recall. /predict could fail for other reasons not related to the model's health.

## 3. Model Volume
Your HPA scales at 40% CPU up to 8 pods. If request volume doubled, what would you expect to happen, and what happens once it reaches the maximum?

Utilization would likely rise above this target if requests doubled, so more pds would be created. 8 pods being the maximum, additional trffic at that point would increase latency or potentially lead to failure.
