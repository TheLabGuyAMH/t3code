# SUM

## 2026-11-22: teams in Agent mode (council result, nothing built)

Anthony, in the T3MC manager thread (T3 Code thread `mcp:d7366615-9e8b-4d45-87f2-d5e4d0d14329`):

> How can we turn agent mode into a team of agents that work together as an option?

> Talk it over with Gemini 4 Carbon High and Muse Wonder Full High and figure out the realistically optimal way to implement teams to MAX Agent toggle

> Looks like this work didn't get completed for some reason so can we go ahead and do that?

> Use Antigravity then

Who answered: Muse Wonder Full (High) reviewed the brief and the code on 2026-11-15. Gemini 4 Carbon did not answer: Antigravity stalled and Cursor failed on 2026-11-15; on 2026-11-22 Cursor refused ("Gemini 4 Carbon is not included in your weekly usage"), and Antigravity, after its managed runtime was updated from 1.4.5 to 1.5.14 through T3 Code's own setup, reports "Sign in with Google to use Antigravity." Two sign-in cards sent to Anthony timed out.

Proposal (not approved, nothing built): add a "Team" option inside Agent mode in two stages. Stage 1: a lead model hands pieces of the job to helper models with T3 Code's built-in hand-off tool (`delegate_task`), steered by a written team charter MAX sends as the first message. Stage 2: MAX keeps its own team record and shows a team panel with limits. Do not build a separate MAX-run pipeline. Scores out of 10, Muse / manager: lead-with-charter alone 7 / 6; MAX-run pipeline 4 / 4; full team panel as the first build 5 / 5, as the end state 8 / 8; staged path 9 / 9.

Stage 1 contents: Lead, up to three helpers and a reviewer picked in the existing model window; only the lead changes files, helpers research and review; the answer is labelled "lead worked solo" when no helper ran; lead choices limited to providers whose hand-off has been seen working.

Checked on Anthony's engine on 2026-11-22 (one small model per provider, scratch threads, all archived afterwards):

- A Claude lead handed a task to a GPT helper and reported its answer. A GPT lead handed a task to a Claude helper and was woken by the result in 36 seconds.
- A Muse lead stopped at a permission prompt before handing off, because Muse offers only "ask first" or "full access".
- Asked to list their hand-off tools, GPT, Cursor, GLM and Muse models named `delegate_task`; a Grok model said it had none; a Kimi model gave no answer. These are the models' own reports.
- The engine's record of the lead's chat lists each helper with its model, status and result (`subagents`), which is what a team panel needs. The helper inherited the lead's permission mode. Helper chats are not archived on their own.
- Waiting on a helper inside one tool call ends after 45 seconds, so the charter must tell the lead to hand off and be woken by the result.

Gap fills, not yet reviewed by Anthony:

- Finished helper chats are archived in T3 Code, following his 2026-10-30 instruction that council chats must not clutter T3 Code.
- Teams run without approval prompts where the provider allows it, following his 2026-10-30 objection to approval prompts on harmless work.

Open points:

- Anthony has not said to build this.
- How many helpers by default; each helper spends from its provider's usage limit.
- Whether helpers may ever change files, or only advise.
- Whether a Muse model may lead, which means running it with full access.
- Gemini 4 Carbon's view is missing until Antigravity is signed in (T3 Code, Settings, Providers, Antigravity, "Sign in with Google") or Cursor credits are bought.

## 2026-11-15: one Council/Agent switch

Anthony, in the T3MC manager thread (T3 Code thread `mcp:d7366615-9e8b-4d45-87f2-d5e4d0d14329`):

> So when I'm using the website and I click on Agent the tab there to switch between Council and Agent changes and that's confusing. Let's make it one of those two things not both.

Decision: keep the two-tab "Council | Agent" switch on every MAX screen and remove the separate "← MAX Council" button, following the spec's "top-bar switcher between Council Mode and Agent Mode" (Rev 3 §1).

Open points: none.
