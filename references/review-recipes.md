# Review recipes: website content and product UX

Use only the recipe that fits the request. Tailor its scope to the material the user supplied; do not imply access to a live site, analytics, user research, or source code unless you actually have it.

## Website content review

### Inspect

- The page's intended audience, job, and primary next action. If these are not stated, infer cautiously from the page and mark the assumption.
- The order and clarity of the headline, supporting message, proof, benefits, and calls to action.
- Claims that need a source, date, qualification, or correction. Verify current factual claims with reliable primary sources when browsing is available and appropriate.
- Readability, terminology, consistency, Persian spelling/spacing when relevant, and whether the copy matches the page or product being shown.
- Mobile content hierarchy when a mobile screenshot or live responsive view is available.

### Report

Prioritize a short list of findings. For each, provide the exact text or location, evidence, why it may hinder the stated page goal, and a concrete rewrite or next check. Separate factual errors from editorial judgment. Mark unavailable context, analytics, and tests instead of filling the gap with invented conversion effects.

### Copy-ready prompt

> Review [page URL or supplied content] for [audience] whose main goal is [goal]. Inspect [screenshots/source/analytics, if supplied]. Rank the three most consequential content issues. For each, show the exact evidence, likely effect on the page goal, and a specific revision. Check factual claims and cite sources for claims you verify. Label assumptions and anything that needs user or analytics validation.

## App or website UX audit

### Inspect

- The user's main task, entry point, expected outcome, and relevant device or viewport.
- The actual screens or live flow available; note missing states and steps that could not be inspected.
- Navigation, hierarchy, affordances, feedback, error recovery, accessibility, responsive behavior, and RTL reading/order when relevant.
- Friction that blocks or adds work to the task. Do not rank findings by visual taste alone.

### Report

Use a compact findings table: **priority · observed evidence · user impact · recommendation · confidence / verification needed**. Keep observed defects separate from heuristic risks. Use severity labels consistently and explain them briefly; do not invent frequency, analytics, task success, or user-test results. End with the smallest useful next step or a proposed verification plan.

### Copy-ready prompt

> Audit the [app/site] flow for [user] trying to [task] on [device/viewport]. Inspect only [provided URL, screenshots, or files]. Return up to five prioritized findings with observed evidence, user impact, a specific fix, and confidence. Separate directly observed problems from heuristic risks. Check accessibility, responsive behavior, and RTL where applicable. Do not claim user testing or analytics unless I provide them.

## Turn a review into an implementation

When the user asks to fix findings, select the highest-impact verified issue that is in scope, inspect the relevant implementation, and make the smallest coherent change. Then check the affected states and report what actually passed, failed, or could not be checked. A critique alone is not implementation; a plausible edit alone is not verification.

### Copy-ready prompt

> From this review, implement [finding]. Preserve [constraints]. Inspect the relevant files first, make the smallest complete fix, and verify the affected behavior at [states/viewports]. Report the changed files and checks actually run; call out anything you could not verify.

## Limits

These recipes structure expert inspection. They do not replace content owners, domain review, accessibility testing, analytics, or usability research. If evidence is missing, say what can be concluded now and what would require additional data.
