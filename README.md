# Sandbagging Audit
For my BlueDot Technical AI Project Sprint, I conducted a preliminary investigation to audit the sandbagging evaluation methodology. The results indicate that non-target behaviours can explain “sandbagging”-based misalignment. This repo contains an audit of the sandbagging eval methodology using the AMR checklist to surface dimensions to stress-test methodological decisions. For code for experiments, please refer to: https://github.com/ms3744/sandbagging_extension

## Project Plan

At a broad level, the project was divided into two phases:

**Phase 1**: Grading Sandbagging Eval Against Anthropomorphic Misalignment Checklist
I selected van der Weij et al.’s (2024) method as the primary Sandbagging Eval methodology. I audited this methodology using the Anthropomorphic Misalignment Research (AMR) Checklist (Gupta et al., 2026). This audit raised questions on behaviour definition, evidence levels, experimental design choices and stress-tests. 

**Phase 2**: Perturbing the Evaluation Method to Stress Test Against Checklist
I selected a few unvalidated design choices that surfaced from the audit, and ran a corresponding experiment to measure how reported behaviour survives the perturbations.

# Method
In lieu of peer-based feedback, I consolidated audits from three sources: my own judgments, ChatGPT (GPT 5.6 Luna), and Claude (Sonnet 5 medium). I ran the audit myself before passing through the LLMs to avoid bias in my responses. For the LLMs, I used the free-tier chat interface. Finally, I consolidated the three responses into a single pass. 

# Results
Based on the consolidated results, the paper provides L1 (behavioural) evidence of sandbagging. A snapshot of the results are provided in the table below. For detailed logs of each individual pass and the consolidated pass, please refer to files in this rep. 

| Evidence                                                                   | Checklist Items |
|----------------------------------------------------------------------------|-----------------|
| Verified                                                                   | 11              |
| Partially verified (including fuzzy evidence or a lack of robust evidence) | 8               |
| Not verified                                                               | 6               |
| Not applicable                                                             | 8               |
|                                                                      Total | 33              |


The checklist helped uncover gaps where sandbagging behaviour could not be verified, including experiments on generalisation across formats & confounding features. More specifically, I found some plausible extensions take shape as:
- Extending the methodology to explore underlying non-target explanations  (e.g. instruction following, role-play etc.) that can possibly explain the results
- Evaluating sandbagging in longer, more complex tasks and environments to measure if this behaviour can persist across evaluation formats
- Conducting an ablation study for prompts, task domains, output formats & sampling methods for evaluation datasets. 

## Prompt Used for Claude, ChatGPT

> You are given a task on evaluating how current evaluation techniques for sandbagging fare against the attached checklist (sourced from https://arxiv.org/pdf/2606.07612v1). In your response, write down clearly answering whether and how the methods described in the paper “AI Sandbagging: Language Models can Strategically Underperform on Evaluations” addresses each point in the checklist. Where possible, provide references to page numbers and/or sections. You are free to use the additional information provided in the appendix and the code repository, however, you are not allowed to respond to any point using information sourced from outside the sources provided below. 
>
>Sources:
>Main paper + Appendix: https://arxiv.org/pdf/2406.07358
> 
>Code repository: https://github.com/TeunvdWeij/sandbagging

### References
Van Der Weij, T., Hofstätter, F., Jaffe, O., Brown, S., & Ward, F. (2025, May). Ai sandbagging: Language models can strategically underperform on evaluations. In International Conference on Learning Representations (Vol. 2025, pp. 73152-73189).

Gupta, V., Nutter, P., Stante, S., Krause, A., Tramèr, F., Fluri, L., ... & Hedström, A. (2026). Position: Anthropomorphic Misalignment Research Needs Stronger Evidence. arXiv preprint arXiv:2606.07612.
