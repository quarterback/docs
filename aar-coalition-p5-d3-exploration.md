# Agent Action Record: COALITION p5/D3 exploration

**Review date:** 2026-10-29, America/Los_Angeles  
**Reviewed by:** Agent self-review, with a separate documentation-scope review. Human selection of a library is pending.  
**Agent / system:** ChatGPT  
**Task or period under review:** Explore useful p5/D3 interactions for COALITION and preserve the discussion after the documentation follow-up.  
**Accountable human (name or role):** Ron Bronson, concept author and project owner.  
**Repository:** `quarterback/docs`  
**Branch:** `coalition-build-prompt`

**Status:** p5 is the agent's recommendation for the first interactive scene. D3 is an optional candidate for relationships and dependencies. These are proposals; no library was selected, installed, or used to build a prototype.

## 1. Intent: what was supposed to happen

**Instruction given (actual wording):**

> can we do anything cool with p5 OR d3 ?

Follow-up:

> did you update the docs with this?

**Success defined in advance as:**

No formal acceptance criteria were given. The immediate request was to explore what the libraries could contribute to COALITION. The follow-up and earlier archive instructions established the need to preserve that discussion in the repo.

**Authority granted to the agent:**

Research library capabilities, propose interactions grounded in the existing concept, and update its documentation.

**Out of scope:**

Building the game, choosing a library on Ron's behalf, prescribing a boardgame, or turning the project into the unrelated clinic or data-story examples from the other agent's earlier response.

## 2. Action: what actually happened

**What the agent did (step by step):**

1. Consulted official p5 and D3 documentation and obtained a separate design review.
2. Proposed four applications: an interactive pixel-art scene, a map of people and commitments, a playable service blueprint, and a reconstruction of a completed run.
3. Recommended starting with p5 and HTML/CSS. Explained how a pinned library could be included in the one delivered HTML file while retaining offline operation.
4. Initially left that answer in chat. After Ron's follow-up, checked the current repository branch, reviewed the existing prompt and index, and added this record and links to it.

**What it produced or changed:**

Added `aar-coalition-p5-d3-exploration.md`. Added a technology-status note to `coalition-build-prompt.md` and a report entry and chronology note to `coalition-notes-index.md`.

**Where actual behavior differed from the instruction:**

The initial answer did not carry the discussion into the established archive. Ron had to ask whether that had happened.

**Stayed within granted authority?**

Yes, as an agent self-assessment. This update records proposals without converting them into accepted implementation requirements.

## 3. Judgment: human in the loop

**Decisions the agent made on its own:**

Recommended p5 first, retained HTML/CSS for readable controls, and treated D3 as useful when relationships or dependencies become a substantial player interaction. Chose to save the discussion as a new record and link it from the existing brief, preserving the earlier review as history.

**Of those, which should a human have made or seen:**

The library choice and the proposed interaction need Ron's creative judgment. The original no-library requirement and the p5 alternative must be reconciled in the selected build brief.

**Where a human actually intervened:**

Ron introduced the p5/D3 question and then prompted the documentation update. He did not select p5, D3, or a combination of them in these messages.

**Points where it should have escalated and didn't:**

None identified. Recording the discussion was already within the archive request. The missing step was saving it, not asking for another permission.

**Accountable for these actions:**

Ron owns the concept and final creative decisions. ChatGPT owns the recommendations and this account of its work.

## 4. Deviation: the gaps

**Gaps between intent and action, and why (root cause):**

The agent treated the p5/D3 question as a conversational answer and failed to carry forward the ongoing documentation task. The follow-up exposed that gap.

**Good deviations (correct departures from a flawed instruction):**

None claimed.

**Confidently wrong:**

No implemented or tested interaction was claimed. The suggestion that a library can help make the interface is a design recommendation, not evidence that these particular interactions are enjoyable or perform well on a phone.

## 5. Consequence: what it cost or risked

**Actual outcome (did the work hold up):**

The discussion is now recorded alongside the proposed build brief. The current prompt identifies the open technology choice. No game, prototype, performance measurement, or playtest result was produced.

**Harm / cost / risk: realized or narrowly avoided:**

Ron spent an extra message checking whether the discussion had been saved. Leaving it in chat would make later work more likely to miss the ideas or combine a p5 instruction with the existing ban on libraries. Adding both libraries without a clear interaction could also increase implementation complexity.

**Downstream affected parties:**

Ron and whoever implements COALITION from these records.

**Expected failure if this run happened 100 times:**

Repeatedly preserving only the formal brief would lose later design reasoning. Repeatedly treating exploration as approval would turn suggestions into unwanted requirements. These are qualitative risks, not measured rates.

## 6. Change: what happens next

**Specific changes before next run:**

Carry substantive COALITION design updates into the established archive as part of the work. Before implementation, settle the renderer in the selected brief and replace any conflicting runtime clause. Evaluate the scene interaction first; add a D3 view if it makes the player's decisions clearer.

**Keep doing:**

Connect visible interactions to the service blueprint, actual capabilities, pending work, and consequences. Keep proposals attributed to their author and fictional Nelosphere details open to invention.

**Should not be delegated to an agent at all:**

An agent must not record its own library preference as Ron's creative approval.

**Signal that the change worked:**

The next person can find the options from the build prompt, tell what remains undecided, and build from one consistent runtime specification.

---

## The interface ideas worth preserving

These are proposals from the discussion, not four mandatory new features.

### 1. A p5 scene the player can act on

Present a readable pixel-art location containing people, objects, and work in progress. Selecting a card can reveal the people or arrangements it can affect. The player taps a target, reads the known requirements and consequences, then confirms the action.

After the action resolves, the scene reflects its result: a person makes a call, someone returns from a task, a departure board changes, or a service becomes available. Occupied people and unfinished arrangements can make waiting and dependencies visible. Inspection and animation remain free of game-time costs, as in the existing brief.

The artwork needs deliberate pixel patterns and scale. p5 provides an offscreen drawing buffer through `createGraphics()`. In 2D, `noSmooth()` helps preserve sharp image scaling but does not make shapes or text into pixel art automatically. Keep dialogue, card text, and accessible action controls in HTML/CSS. [p5 buffers](https://p5js.org/reference/p5/createGraphics/), [p5 smoothing behavior](https://p5js.org/reference/p5/noSmooth/).

### 2. A D3 view of who can make something happen

Tap a person, arrangement, or immediate objective to see the relevant connections. A well-connected family member might influence one office while having no reach at the next location. Someone helped earlier might possess the specific local capability needed now. This would make contextual power visible through play.

Show relationships, capabilities, promises, and offers as distinct records. A relationship can persist after a particular favor is spent. Use stable positions, readable labels, and a focused neighborhood of connections on a phone. Show only information available to the selected side.

D3 can bind JavaScript objects to displayed elements and update them as state changes. Fictional people and commitments are sufficient data; no external dataset or data-story premise is required. Its layout calculations can also be rendered through Canvas. A small authored network may be simpler without D3, so the library should earn its place through the interaction. [D3 data joins](https://d3js.org/d3-selection/joining), [D3 force layouts](https://d3js.org/d3-force).

### 3. A playable service blueprint

A compact work view could show what is pending, who is occupied, what each task depends on, and which arrangement would open the next action. The player can inspect a blockage, identify the missing cooperation or work, and commit a response through the same action system used by the scene.

This gives the blueprint a direct role in decision-making. It also develops the earlier Hundred Days comparison: work has duration, dependencies, and consequences for later turns. D3 is a possible implementation for updating these relationships, but the design does not require a large diagram on every screen.

### 4. A reconstruction of the run

At the end, show the chain of actual decisions and outcomes: an earlier favor enabled a later arrangement, a missed promise changed someone's response, or an unfinished task left an option unavailable. Pixel scenes or a focused causal diagram could provide that account.

Build it from recorded events and state changes. Do not generate an explanation merely because it sounds plausible. The reconstruction should make the particular run understandable and support replay. It is optional additional presentation work, not an implemented feature.

## What this would change in the build prompt

The current [build prompt](coalition-build-prompt.md) still prohibits libraries. Its other delivery constraints can coexist with p5: include a pinned copy in the delivered HTML file, retain required library notices, and make no runtime network requests. p5 offers downloadable library files; using a CDN at runtime would conflict with the existing offline requirement. [p5 downloads](https://p5js.org/download/).

The recommendation is to start with p5 for the interactive scene and HTML/CSS for readable UI. Add D3 only if a substantial relationship or dependency interaction justifies it. A small route map can be drawn with p5. Neither library supplies the rules, authored encounters, or game balance.

If the p5 option is selected, replace the conflicting no-library clause and incorporate this proposed language:

```text
Use p5.js for the interactive pixel-art scenes and route presentation.
Keep dialogue, cards, resource descriptions, and controls in HTML/CSS.

Include a pinned copy of the library in the delivered index.html,
retaining its required notices. The finished game must make no runtime
network requests. Keep all game content and assets inside that file.

Selecting a card should reveal the people, objects, or arrangements
it can affect using information available to the selected side.
Let the player inspect those applications before committing.
Provide equivalent readable controls for scene actions.
Resolve the game action first, then animate its consequences.

Show pending work through the scene: occupied people, changing objects,
available services, and completed arrangements.

Keep simulation state independent of rendering and animation.
Use native Web Audio for synthesized sound.
```

This wording is an alternative for a later selected brief. It has not replaced the current runtime instructions. If D3 is selected too, define its precise view and include its pinned code under the same offline constraint. Layout animation must not advance the game clock or alter authoritative game state; D3 force simulations maintain their own layout state and can run a timer. [D3 simulation documentation](https://d3js.org/d3-force/simulation).

## Record and verification

The six-part record follows the [ClosedTab skill at the revision already consulted for this archive](https://github.com/quarterback/closedtab/blob/36f1a69a5da5c104cb5901786798c9f2608176c6/skills/closedtab/SKILL.md). The library sources above were consulted during the discussion. The documentation update received a separate scope review and checks for the record's sections, relative links, and consistency with the current brief.

No ClosedTab CLI score, runtime test, or independent trace reconciliation is claimed. The previous environment attempt to access npm was blocked; this documentation update did not repeat that network operation.
