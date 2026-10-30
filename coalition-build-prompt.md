# COALITION: single-file game build prompt

**Technology status, October 29, 2026:** This proposed brief retains its original no-library requirement. The later p5/D3 discussion recommends p5 for interactive pixel-art scenes and considers D3 for relationships and dependencies. Those options, including alternative runtime language, are recorded in the [p5/D3 exploration AAR](aar-coalition-p5-d3-exploration.md). No library choice has been adopted or implemented. Reconcile Section 1 with the selected renderer before using this as an implementation brief.

Build a complete, playable HTML5 game called COALITION. Deliver exactly one file, `index.html`, containing all HTML, CSS, JavaScript, story data, procedural graphics, and synthesized audio.

COALITION is a mobile-first, turn-based political thriller. An opposition figure has lost an election and is trying to leave the country. The player is the strategist for the side they select: facilitate the escape or organize the effort to stop it. Money, reputation, and authority have different value with different people. Progress depends on securing cooperation and making arrangements that other people can actually carry out.

Create a compact, complete game with meaningful decisions and replay variation. Implement the rules and consequences described below. Choose modest tuning values and keep them in a clearly named configuration object. Do not add unrelated systems to enlarge the game.

## 1. Runtime and delivery

- All runtime code and content must live in `index.html`. Use inline CSS and plain JavaScript. No libraries, external assets, image files, web fonts, imports, remote APIs, analytics, or network requests.
- Browser APIs such as Canvas, Web Audio, and localStorage are allowed.
- Generate artwork with Canvas drawing code and inline pixel-pattern arrays. Use semantic HTML and CSS for readable dialogue, cards, labels, and controls.
- The game must run when the file is opened directly in a browser and remain playable without a network connection. It must also work on a static host.
- Storage and audio failures must not prevent play.
- Deliver the finished file, with complete content and functioning controls. Do not substitute an implementation plan or pseudocode.

## 2. Fiction and the player's role

Use an entirely fictional South American setting in the Nelosphere. Invent the countries, cities, institutions, characters, documents, and events needed for this game. Give them consistent names and a coherent relationship to one another. The real article that inspired COALITION does not constrain the invented route or procedures.

The election result is the opening situation. Begin with a brief account of the defeat and the closing opportunity to leave. Do not build an election simulation.

The player remains a strategist throughout the run. They act through contacts and local people, receive reports, assign or arrange work, make commitments, and choose approaches. They do not become a different unexplained clerk at each location.

The references guide distinct qualities:

- Papers, Please: recognizable pixel-art places, faces, objects, and consequential ordinary work.
- Hundred Days: work that takes time, depends on other work, and changes later options.
- Suzerain: recurring people with motives and relationships affected by earlier decisions.
- Balatro: capabilities acquired during a run that combine and change how later problems can be solved.

## 3. Both playable sides

Offer FACILITATE and OBSTRUCT before the run starts. Show the selected side's role and objective in plain language.

FACILITATE:

- Direct the target's support network.
- Prepare arrangements, choose routes, maintain cooperation, and move the target toward departure.
- An opposing operation acts after committed turns. It can pursue leads, alert a location, or close a route according to the current state.
- Interception or decisive containment before departure is defeat. Leaving the country achieves the main objective; destination arrangements determine the fuller outcome.

OBSTRUCT:

- Direct the effort to prevent departure through interception or decisive containment.
- Gather or verify reports, secure cooperation from relevant people, and commit resources to an actionable lead.
- The target's network has an independent plan. It completes preparations and moves toward departure as game time advances unless a particular player action causes a delay or interception.
- The player must not need to approve the target's next move for the target to advance. Waiting must allow the target to make progress.
- Interception or decisive containment is victory. Departure is defeat for this side. Describe the result accordingly and distinguish capture from preventing departure.

Use the same world and route presentation for both modes, with different actions, information, allies, and goals. A relative who supports the target remains part of the target's network in OBSTRUCT mode. Do not turn that person into the pursuer's controllable ally merely because the mode changed.

## 4. Route, levels, and pursuit

Present a horizontal journey with five stages:

Origin -> Checkpoint -> Transit Hub -> Airport -> Destination

The first four stages are within the origin country. The checkpoint is domestic. Departing after the airport stage crosses the border into the neighboring country. Destination resolves what happens there.

Use a small authored graph with at least one meaningful choice between alternative checkpoint or transit locations. The alternatives should differ in their people, requirements, time, or consequences, and then rejoin the onward journey. Keep every possible run finite.

A location is a level containing preparation and decisions over several turns. At a given decision, offer two to four concrete actions. A single correct line of dialogue should not automatically replace all the work required to complete a level.

Give each active level:

- A visible immediate objective.
- People whose cooperation or actions matter.
- Known requirements and clues to unresolved requirements.
- Work that can prepare a later action.
- More than one possible approach across the available circumstances.
- A defined result that changes the next situation.

Show the target's journey moving left to right and an effective pursuit position behind it. The pursuit track represents the search directed toward the target's route. A false report or diversion must affect that state before it affects pursuit.

Maintain the true target state separately from what the selected side knows. In FACILITATE, show the position reported by the player's network. In OBSTRUCT, show confirmed or last-known locations and clearly labeled estimates when information is incomplete. Do not reveal an unknown route through the map or an exact pursuit-gap display. Resolve interception against the true state.

Interception occurs when effective pursuit reaches the target before departure. In OBSTRUCT mode, confirmed leads and effective actions must make that possible. Repeated waiting from the initial, unprepared state must not guarantee victory. Waiting for work already commissioned through effective decisions may legitimately complete an interception. Blocking one route must not immobilize the autonomous target indefinitely if another route remains available.

Route closures must have a defined result: a delay, an available alternative, or a clear terminal outcome. Every active situation needs a valid action, fallback, or ending. Do not leave the player in a screen with nothing that can resolve it.

## 5. A turn and the work it changes

Resolve play through one action handler shared by touch and keyboard input:

1. Show the situation, pending work, known clues, and available actions.
2. Let the player select an action and any applicable card or contact.
3. Preview its known costs, requirements, and stated commitments.
4. On confirmation, pay the cost and commit the action exactly once.
5. Advance the fictional clock by that action's duration. Advance pending work and the opposing side for the same elapsed time.
6. Resolve completed work, changed relationships, pursuit, and route conditions in a consistent order.
7. Show a brief consequence that explains what changed and why. Then open the next decision or resolve the level.

Process timed events chronologically throughout the elapsed interval. An interception before departure ends the active run immediately. If interception and departure occur at the same simulated moment, interception takes priority in both modes. A long action must not skip an intervening interception.

Some preparation must take more than one turn or occupy a particular contact. Show who is working, what the work is waiting for, and when its result becomes available. Let completed work change later options. The player can do other available work while a delegated task is pending. Waiting is a deliberate action that consumes time.

Reading, inspecting already available information, opening cards, panning the map, resizing the window, and animations never consume game time. Obtaining new information through a contact can be a time-consuming action, and its cost must be shown.

Advance the simulation only through committed actions. Use animation frames only for presentation. Pausing or putting the tab in the background must not advance pursuit, tasks, or deadlines.

## 6. Negotiation and recognition

Give each approver a motive, something they can actually do, and conditions under which they will cooperate. Reveal useful evidence through dialogue, existing relationships, reports, and optional inquiries.

Write choices as concrete commitments or approaches. Several approaches may work with different costs or later consequences. A good argument can change willingness, but it cannot supply a missing person, document, authorization, or service by itself. An unavailable action should explain its known missing requirement.

Keep dialogue brief enough to read on a phone. Remember previous promises and treatment. At least one ordinary person helped earlier must change a later opportunity. NPCs can pursue their own interests even when they broadly support the same side.

Use recognition at selected locations where identifying someone changes the work available. The strategist receives a queue view or a report from a local contact. The player matches the person to consistent evidence in a briefing, portrait, description, or conversation.

In FACILITATE, identifying the target or expected contact can enable assistance. In OBSTRUCT, identification can make a lead actionable. Include a way to defer identification or investigate further. A false identification must have a defined consequence.

Make the relevant clues readable and distinguishable. Provide equivalent written observations alongside portraits. Do not rely on an unexplained tiny visual difference, or require a recognition puzzle at every location.

## 7. Resources and commitments

Keep these six categories in a compact HUD. They can contain counts, named records, or status summaries; they do not all need to be spendable numeric currencies.

TIME / PURSUIT

Time records the cost of committed actions. Pursuit distance follows the target and effective search positions. Heat and specific actions can alter pursuit behavior through explicit rules. Avoid unrelated hidden clocks that punish the same event several times.

CREDIBILITY

Track the selected side's record of keeping commitments. A promise stakes credibility with a named person and records an obligation and its resolution condition. Keeping or breaking it changes the relevant relationship and general standing. Repeating a resolved promise cannot generate more credibility. Credibility alone cannot override every local condition.

FAVORS / DEBT

Distinguish assistance owed to the player's side from commitments that side owes other people. Each has a named person and a concrete scope. Calling in a favor, fulfilling a debt, or exhausting an offer changes that same underlying record.

INFORMATION

Store actual clues, claims, known requirements, and route conditions. Information changes understanding or available actions. A HUD count may summarize the collection. A rumor can be false, but the game must provide evidence or a way to investigate; hidden facts remain consistent within the run.

MONEY

Start with substantial but finite funds. Money buys logistics, preparation, information, and explicitly offered transactions. A payment or bribe may persuade a person with a financial motive. It cannot universally replace relationships, access, authority, or another person's willingness. Funds kept for later can support rebuilding, alongside relationships and permission to stay.

HEAT

Heat measures how exposed the target's escape operation has become. Higher heat helps the search and can make cooperation or routes harder for the target. It is a danger in FACILITATE and can be an advantage in OBSTRUCT. Loud obstruction tactics may still damage the player's credibility or warn the target into changing route. Show these effects through the relevant people and conditions.

Keep the resource labels and descriptions consistent with their implemented effects. Display the player's active stage, known or estimated pursuit gap, pending work, and active cards without shrinking the text to fit everything onto one screen. Label uncertain information. Use vertical scrolling where needed.

## 8. Cast, cards, and replay

Include the following fictional roles, with names, portraits, and specific motives:

- The target's brother abroad, whose preparation affects receiving arrangements and what can be secured before departure.
- The target's father at home, who has useful influence and attracts attention or opposition when he uses it.
- Party supporters and ordinary people with different capacities, loyalties, and requests. Some can supply misleading information or act as informants, with discoverable clues.
- Local approvers whose authority and willingness have limits.
- Rival officials or faction members who act as the situation develops.

Cards represent work, documents, information, relationships, or specific offers. A card records where it came from, what it enables, where it applies, and whether it persists, expires, or is consumed.

Offer a small starting set and new opportunities from authored content appropriate to the run. Earn further assistance through encounters and completed commitments. Known contacts and facts remain recorded; they do not vanish because a new hand is shown.

Include persistent relationships and consumable offers. At least one acquired capability must have more than one useful application, creating a decision about when to use it. Cards must also be able to work together: a contact might enable an action, a document satisfy its requirement, and a favor reduce its delay. Apply combinations only where their stated meaning fits.

Show a brief, accurate "why this mattered" line when a card affects an outcome. A favor represented by a card and by the HUD must refer to one record, so it cannot be spent twice.

For this build, use seeded variation in situations, available offers, and starting conditions. Do not add a separate dice-based success roll. Dice remain a possible later design change with their own purpose and timing.

Display a run seed and offer a new run or replay of the same seed. Use a dedicated seeded generator for gameplay. Keep motives, loyalties, identities, and conditions stable once generated. Choices can change them only through defined consequences.

Rendering, animations, and reopening panels must not consume gameplay randomness or reroll offers. Use authored combinations that allow coherent play. Do not require a missing essential card as the only path through a randomly generated run.

## 9. Endings

Separate the selected side's result from milestones reached by the target.

- INTERCEPTED: pursuit reaches the target before departure. Victory for OBSTRUCT; defeat for FACILITATE. Describe what enabled it and the consequence for the people involved.
- CONTAINED: the target remains in the origin country and every departure route is permanently unavailable, with no pending or obtainable action able to reopen one. Victory for OBSTRUCT; defeat for FACILITATE. This records prevented departure without claiming an arrest. Unfinished preparation or a missing card in the current hand is not sufficient to trigger it.
- ESCAPED: the target leaves the origin country. This completes FACILITATE's main objective and defeats OBSTRUCT's active objective.
- ARRIVED: the receiving arrangements secure the target's entry at the destination.
- GRANTED STAY: a specific host-country commitment or completed arrangement permits the target to remain.
- REBUILT OPERATION: permission to stay, surviving organizational support, and sufficient remaining target-side funds enable a continuing operation.

The four escape milestones are cumulative. Show the highest reached and explain which arrangements produced it and what prevented the next. Do not choose an ending randomly or award rebuilding for money alone.

End the domestic pursuit when departure occurs. Resolve destination outcomes in a short closing scene based on preparations and commitments already made. The obstructing player does not gain unexplained authority abroad. Evaluate the target's outcome from the target's state, not from funds belonging to the player in OBSTRUCT mode.

Give other terminal failures a specific explanation. Every ending should show the selected side's result, important earlier decisions, commitments kept or broken, and the people who affected the outcome. Record an ending once.

## 10. Art, interface, and sound

Use a deliberate 16-bit pixel-art style with a tense, muted palette. Draw recognizable people, architecture, vehicles, office objects, and location details. Give the locations distinct silhouettes and the recurring cast distinguishable portraits. Their appearance should remain coherent through the run.

Use a consistent pixel scale for artwork and disable image smoothing where appropriate. Preserve readable HTML text. Animate visible consequences: someone leaves a desk, a departure changes, a vehicle moves, or a location becomes unavailable. Keep transitions brief and respect reduced-motion preferences.

Show the left-to-right route inside its own viewport. Swiping pans that view; it never advances the target or spends a turn. Provide visible alternatives to swipe controls and center the current location when useful. The page itself must not overflow horizontally.

Make portrait touch play the primary layout. Use safe-area insets, readable text, visible focus, and interactive targets of at least 44 CSS pixels. Keep controls reachable on small screens and allow normal vertical scrolling and browser zoom.

Title screen: COALITION, a short atmospheric subtitle, PLAY, side selection, concise controls, and records for the selected side.

Provide visible Pause, Resume, Mute, and Restart controls. Escape toggles pause. Arrow keys move focus or pan the map according to the active screen. Keys 1-4 select a visible choice. Space or Enter confirms it. Preserve normal button and keyboard behavior. Prevent held keys or double taps from committing an action twice.

Use Web Audio to synthesize restrained ambient tension and short action or ending cues. Start or resume audio through PLAY or another user gesture. Suspend it when paused or hidden. Mute must work, and every gameplay cue must also be understandable without sound.

## 11. Records and robustness

Save a versioned record under a COALITION-specific localStorage key. Track total completed runs, outcomes and milestones reached, best result by side, and furthest stage reached.

Rank results according to the selected objective: interception and containment are successful outcomes for OBSTRUCT; successful departure and destination milestones outrank either for FACILITATE. Keep furthest stage as descriptive progress rather than a universal success score. An early interception must not be treated as a worse obstruction result merely because fewer locations were visited.

Guard storage reads, writes, and JSON parsing. Recover from malformed or outdated records. If storage is unavailable, continue with in-memory records and a short notice. Restarting a run resets its state while retaining lifetime records. Clearing records must be a separate deliberate action affecting only COALITION's key.

Track resolved requests, promises, rewards, consumed cards, and terminal outcomes. Prevent free repeat actions from creating unlimited resources. Lock commitment input while a turn is resolving.

Keep story data, rule evaluation, state transitions, and rendering clearly separated within the single file so effects can be checked without relying on animation.

## 12. Definition of done

Verify the implementation before delivering it:

1. One file contains every runtime dependency and makes no external requests.
2. Both sides can reach a terminal result with the correct interpretation of success and failure.
3. The target advances independently in OBSTRUCT mode. Unprepared waiting cannot immobilize it or guarantee victory; waiting for effective delegated work can resolve that work normally.
4. Work carries across turns, and an earlier encounter changes a later option.
5. Alternative routes and card combinations produce different viable plans.
6. Every advertised ending or milestone has a reproducible path through the rules.
7. Identical side, seed, initial configuration, and committed action sequence give identical gameplay results regardless of animation timing or viewport size.
8. Reading, map panning, pausing, resizing, and backgrounding do not advance the simulation.
9. Touch and keyboard can reach and operate every control. Repeated input cannot duplicate a transaction or turn.
10. Check small-phone, typical-phone, tablet, and desktop layouts, including 320x568 and 390x844 CSS pixels. Dialogue and controls remain readable, reachable, and unclipped.
11. Restart and saved records behave correctly. Missing or malformed storage and unavailable audio do not block play.
12. Card descriptions, action previews, consequence text, and ending explanations match the state changes that actually occur.
13. No placeholder content, dead-end controls, unhandled errors, or console errors remain.
14. Hidden target information is not leaked by the map, and long actions respect the chronological interception and departure rules.

Prioritize meaningful decisions, readable dialogue, recognizable pixel art, coherent consequences, replay variation, and comfortable touch interaction. Deliver the complete playable `index.html`.
