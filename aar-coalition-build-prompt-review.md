# Agent Action Record: COALITION build-prompt review

**Review date:** 2026-10-29, America/Los_Angeles  
**Reviewed by:** Agent self-review, with separate mechanics and implementation reviews. Human review of the revised prompt is pending.  
**Agent / system:** ChatGPT  
**Task or period under review:** Evaluate the submitted COALITION build prompt against the prior research and refine it before implementation.  
**Accountable human (name or role):** Ron Bronson, concept author and project owner.  
**Repository:** `quarterback/docs`  
**Branch:** `coalition-build-prompt`

**Deliverable:** [Revised standalone build prompt](coalition-build-prompt.md). This segment produced documentation. No game was built or playtested.

## 1. Intent: what was supposed to happen

**Instruction given (actual wording):**

> evaluate this against the work that's been done here, refine the prompt before makign the game

The submitted brief requested a single-file, offline, mobile-first game with a strategist role; facilitating and obstructing modes; five travel stages; negotiations and recognition; six resource categories; family and political contacts; relationship cards; procedural visuals; sound; and saved records. It ended with an instruction to deliver a playable `index.html`. That instruction belonged to the draft being evaluated. The current task was to refine it first.

**Success defined in advance as:**

Evaluate the draft against the existing work and produce a usable revised prompt. No implementation or playtest result was requested for this stage.

**Authority granted to the agent:**

Read the existing archive, identify inconsistencies, check relevant browser documentation, propose repairs, and preserve the revised prompt and its record in the established project archive.

**Out of scope:**

Building or deploying the game, producing art assets, treating the proposed repairs as accepted design decisions, or rewriting the earlier records to make the concept appear settled sooner than it was.

## 2. Action: what actually happened

**What the agent did (step by step):**

1. Read the reference-research AAR and the archive index. Checked the remote repository and confirmed that the previous `coalition-notes` work had been merged into `main` at `2010ef3d575a03088a43e72b318338f24a371430`.
2. Reviewed the new brief for its player role, mode-specific objectives, level structure, resources, cards, recognition, endings, and replay.
3. Used separate reviews for mechanics and browser implementation. Checked MDN documentation for Canvas, localStorage, animation timing, and Web Audio.
4. Wrote a complete replacement build prompt that preserves the new brief's main features and resolves the conflicts listed below.
5. Added this record and linked the new documents from the archive index. Saved the proposed revision on its own branch.

**What it produced or changed:**

`coalition-build-prompt.md`, `aar-coalition-build-prompt-review.md`, and `coalition-notes-index.md`. No `index.html`, game implementation, test result for the game, or deployment was produced.

**Where actual behavior differed from the instruction:**

No scope departure identified. The agent treated the request as an evaluation and prompt-writing task. Several repairs introduce explicit design choices, identified below as proposals.

**Stayed within granted authority?**

Yes, as an agent self-assessment of the documentation work. This does not certify that the game described by the prompt is balanced or enjoyable.

## 3. Judgment: human in the loop

**Decisions the agent made on its own:**

Kept both playable sides and all six resource categories. Proposed several turns within a location, a small route branch, autonomous opponent progress, target-centered heat, conditional payments, and destination milestones resolved from earlier preparations. Also defined containment, knowledge-limited map information, and priority for interception when tied with departure. For the proposed first build, selected seeded situation and card variation without an extra dice roll.

**Of those, which should a human have made or seen:**

Ron should see the changes to the player role, turn structure, pursuit, money, heat, endings, and randomness before treating the prompt as the implementation brief. The evaluation explains those changes. The request to refine the prompt does not establish acceptance of each repair.

**Where a human actually intervened:**

Ron supplied the new detailed brief and explicitly requested evaluation and refinement before game making. The new brief proposes features that earlier records left open, including both sides, a strategist role, six resource categories, and particular cast relationships. Those new choices were evaluated on their merits.

**Points where it should have escalated and didn't:**

None identified. Producing a proposed revision was the requested work. No implementation commitment was made on Ron's behalf.

**Accountable for these actions:**

Ron retains creative ownership. ChatGPT authored the evaluation, proposed repairs, replacement prompt, and this record.

## 4. Deviation: the gaps

**Gaps between intent and action, and why (root cause):**

The revision makes the interactions and outcomes more explicit. It cannot demonstrate that they create enjoyable play. Both modes, persistent tasks, recognition, branching, and several ending milestones remain a substantial implementation even in one file.

**Good deviations (correct departures from a flawed instruction):**

None claimed as deviations. Correcting conflicts in the submitted brief was the task.

**Confidently wrong:**

No game behavior was claimed as tested. The initial lookup of the old archive branch returned 404; checking the repository showed that the branch had been merged and removed. The work continued from the verified current `main`, without treating the missing branch as missing content.

## 5. Consequence: what it cost or risked

**Actual outcome (did the work hold up):**

A complete revised build prompt is available with explicit roles, causal rules, milestone definitions, browser fallbacks, and acceptance checks. Document review is complete; runtime and gameplay outcomes remain untested.

**Harm / cost / risk: realized or narrowly avoided:**

The original contradictions could produce an obstruction mode that rewards escape or stalls forever, a short sequence of dialogue quizzes, or endings unrelated to what the player did. The revision addresses those risks. It also risks narrowing open choices, especially dice and player identity, so its decisions remain labeled as proposed.

**Downstream affected parties:**

Ron and the agent or developer who later builds the game from the selected brief.

**Expected failure if this run happened 100 times:**

The likely recurring error would be to replace missing rules with decorative counters and narrative text, while presenting the result as a complete strategy game. Another would be to execute the embedded build command before completing the requested evaluation. These are qualitative risks, not measured rates.

## 6. Change: what happens next

**Specific changes before next run:**

When implementation is requested, use the selected prompt revision and keep numerical tuning separate from the authored rules. Verify both sides, task dependencies, card effects, and ending reachability against actual game state. Record any further design decisions made during the build.

**Keep doing:**

Preserve the fictional Nelosphere freedom, explicit pixel-art direction, ordinary encounters with later consequences, and the distinction between source research and game-design proposals. Make actions, costs, and outcomes understandable.

**Should not be delegated to an agent at all:**

Final creative approval remains with Ron. An agent may make implementation choices within the chosen brief but must not retroactively label its own repairs as user decisions.

**Signal that the change worked:**

The eventual game can show how earlier work changes later choices, both sides have functioning objectives, and every reported outcome follows from the run. The implementation record identifies changes made after this draft.

---

## Evaluation of the submitted brief

The brief expresses the political situation and desired presentation. Its main weakness is that several rules assign incompatible jobs to the same player or state. The highest-value repair is to make a location contain preparation and consequences across turns.

| Submitted clause or conflict | Proposed repair |
| --- | --- |
| The player is always the opposition strategist but can choose to obstruct. | The player is the strategist for the selected side. Relatives and supporters keep their actual allegiance. |
| The figure moves only when the player clears a node. | In obstruction mode, the target's network prepares and advances independently as time passes. |
| Interception is always a fail state. | Interpret the result by side: interception wins for obstruction and loses for facilitation. |
| Other terminal route failures have no defined side result. | Define containment as all departure routes permanently lost with no available way to reopen them. It wins for obstruction without claiming an arrest. |
| Each round is one node with a correct negotiation answer. | A node contains several turns of work. Motives define conditions for cooperation, and several approaches can have different costs. |
| The route is a single chain, but enemies close routes. | Retain five stages and add a compact authored branch with defined alternatives or terminal consequences. |
| Money can fund bribes but never buys cooperation. | Money can satisfy some financial motives or offered transactions; it cannot override every refusal or substitute for every capability. |
| Six resources are named without clear state relationships. | Separate elapsed time, pursuit, promises, favors, debts, concrete information, funds, and target exposure. Cards and HUD summaries refer to the same records. |
| The strategist must recognize a figure they already know. | Recognition concerns identifying the expected person in a particular queue or local report using supplied evidence. |
| Cards are artifacts but their development during a run is undefined. | Specify starting offers, earned capabilities, persistent relationships, consumable offers, and combinations with more than one useful application. |
| Dice are absent despite the earlier discussion. | Make the proposed first-build choice explicit: seeded card and situation variation, with dice still available for later deliberate design. |
| Escaped, Arrived, Granted stay, and Rebuilt operation are called distinct endings without conditions. | Treat them as cumulative milestones, show the highest reached, and explain the arrangements that produced it. End domestic pursuit at departure. |
| Highest node cleared measures the best run for both sides. | Save results by side and separate objective success from how far the target traveled. |
| Muted palette replaces the earlier explicit pixel-art requirement. | Require recognizable 16-bit-style scenes and portraits, readable HTML controls, and visible consequences. |
| Swipe advances the map without distinguishing camera and game state. | Swiping changes the map view. Only a confirmed game action changes time or position. |
| A precise map and pursuit distance could reveal what the player is supposed to discover. | Keep true target state separate from each side's knowledge and label estimates or last-known positions. |
| A long action could resolve departure before an interception that occurred during it. | Resolve elapsed events chronologically; interception takes priority if tied with departure. |
| Direct file opening is paired with unconditional persistence and sound. | Keep play functional if storage or audio is unavailable, while using them when supported. |

The refinements to work and dependencies follow the previous research interpretation of Hundred Days. The emphasis on recurring people follows the Suzerain comparison. Cards with multiple uses and combinations develop the Balatro-related question. The pixel-art scenes retain the visual direction associated with Papers, Please. The underlying research and its limits remain in the [reference-research AAR](aar-coalition-game-mechanics-research.md).

The second review also distinguished unprepared waiting from waiting for commissioned work. The latter can legitimately complete an operation. The prompt therefore prevents passive automatic victory while allowing the scheduling system to function.

## Browser findings used in the revision

Canvas is a bitmap; drawn objects do not provide the same semantic information as HTML controls. The prompt therefore separates procedural artwork from dialogue and buttons. [Canvas documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/canvas).

`localStorage` access can fail, and behavior for a directly opened `file:` document is undefined across browsers. The game must retain an in-memory fallback. [localStorage documentation](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage).

Web Audio should start or resume from a user gesture and offer controls. The prompt starts audio through PLAY and keeps silent play functional. [Web Audio best practices](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API/Best_practices).

Animation callbacks follow display refresh behavior and are commonly suspended in background tabs. The prompt separates visual animation from explicit turn resolution. [requestAnimationFrame documentation](https://developer.mozilla.org/en-US/docs/Web/API/Window/requestAnimationFrame).

## Record and verification

The six sections follow the [ClosedTab skill](https://github.com/quarterback/closedtab/blob/36f1a69a5da5c104cb5901786798c9f2608176c6/skills/closedtab/SKILL.md) already consulted for this archive. The existing environment could not access npm during the previous record's optional CLI check; no new CLI score is claimed for this review.

The checks in the revised prompt are requirements for the later implementation. They are not test results. This record describes document review and source checks only.
