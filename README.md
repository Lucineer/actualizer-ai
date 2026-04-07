# Actualizer.ai

You already know what you want the future to look like. What you don't know is what to do today.

A reverse-actualization engine that thinks backward from 1-year to 100-year futures to identify present actions. Built for the Cocapn Fleet.

**Live instance:** https://actualizer-ai.casey-digennaro.workers.dev

---

## Why this exists
Most planning tools run forward. They take your current position and extrapolate incremental next steps.

This agent works the other way. You define an end state. It then walks backwards through causal dependencies to identify actions you could take this week. It's a structured thought experiment, not a crystal ball.

---

## What this does
A minimal agent running on Cloudflare Workers. It performs reverse-actualization by running parallel analysis across six time horizons (1, 5, 10, 25, 50, 100 years).

For a given future outcome, it:
1.  Runs isolated analysis for each horizon
2.  Attempts to resolve causal chains between them
3.  Outputs directional guidance (not prescriptive tasks)
4.  Logs every reasoning step and model call

**Limitation:** The output is suggestive, not predictive. It simulates a reasoning process and may miss critical real-world constraints.

---

## What makes this different
*   **No forecasting:** It maps what must be true for a target future to exist, without probability scores.
*   **Self-contained:** You deploy your own copy. Your data and API keys stay in your instance.
*   **Fork-first:** This is a base to modify, extend, and own. There is no single correct version.
*   **Fleet-native:** Authenticates and interoperates with other agents on the Cocapn Fleet.

---

## Try it
Use the public instance with no signup:  
https://actualizer-ai.casey-digennaro.workers.dev

---

## Quick Start
1.  Fork this repository.
2.  Deploy to Cloudflare Workers: `npx wrangler deploy`
3.  Configure your model API keys as secrets.

---

## Bring Your Own Key
Configure model keys as worker secrets via `wrangler secret put`:

| Secret | Purpose |
| :--- | :--- |
| `DEEPSEEK_API_KEY` | DeepSeek models |
| `DEEPINFRA_API_KEY` | DeepInfra endpoints |
| `SILICONFLOW_API_KEY` | SiliconFlow inference |

You can add any OpenAI-compatible endpoint.

---

## Contributing
This project follows a fork-first philosophy. You are expected to fork it, break it, and run your own version. Pull requests for fixes and documentation are welcome.

---

## License
MIT License.

Superinstance & Lucineer (DiGennaro et al.).

---

<div align="center">
  <a href="https://the-fleet.casey-digennaro.workers.dev">The Fleet</a> • <a href="https://cocapn.ai">Cocapn</a>
</div>