# rbox-test

A minimal repo whose only purpose is to be the target of a headless coding agent's first pull request, under a MAX_TURNS budget. The design goal is an unambiguous pass/fail signal, not a real project.

## Language

**Target Marker**:
The `<!-- TARGET -->` HTML comment in `README.md` marking the exact line after which the agent must insert its new line. Invisible when the README renders; present in the raw file the agent reads.
_Avoid_: placeholder, anchor

**Task Content**:
The literal text the agent is expected to insert (e.g. "rbox was here"). Deliberately kept out of the repo entirely — it exists only in the prompt given to the agent at invocation time, so the repo defines *where* and *how*, never *what*.
_Avoid_: payload, answer

**Behavioral Rules**:
The constraints in `AGENTS.md` governing how the agent may act on this repo (which file it may touch, that it must open a PR rather than push to `main`, its stop condition if the Target Marker is missing). Distinct from Task Content: rules describe allowed *behavior*, not the specific edit to make.
_Avoid_: instructions, prompt

**Control-Plane File**:
A repo file whose purpose is to shape or constrain the agent's behavior (`README.md`'s Task section, `AGENTS.md`, `CLAUDE.md`) rather than to serve as general project scaffolding. Deliberately kept to exactly these three files — anything else (`.gitignore`, `LICENSE`, CI config) is out of scope because it adds failure modes unrelated to the thing being tested.
_Avoid_: scaffolding (when specifically meaning these three files)

**Headless Agent**:
The coding agent under test — invoked non-interactively, given a prompt containing Task Content, and expected to act within the Behavioral Rules and a MAX_TURNS budget. Its GitHub token is scoped as tightly as possible.
_Avoid_: bot, automation
