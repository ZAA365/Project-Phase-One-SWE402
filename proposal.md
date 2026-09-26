# Buried Outside

## Phase 1 Proposal and Pre-Production Plan

**Course:** SWE402 Team Project  
**Team members:** ZAHRAA ADEL ALAHMED 202343670 KAWTHAR ALI ALKHAWAJAH 202168810, FORKAN HUSSAIN ALSALMAN 202278520

## Project Description

Buried Outside is a single-player, first-person psychological horror vertical slice set inside an abandoned house beside a foggy graveyard. The player wakes up trapped inside the house, explores rooms, finds clues, solves a small set of environmental puzzles, survives supernatural events, and escapes through the main exit.

The scene begins when the player gains control inside a locked room and ends when the player escapes the house or is captured by the shadow entity. The project is deliberately limited to one complete playable scene so the team can demonstrate integrated gameplay, physics, AI, graphics, technical art, audio, UI, performance work, and professional collaboration within one semester.

## Purpose and Motivation

We chose this idea because a contained horror scene allows us to practice the full game-development pipeline while maintaining realistic scope. The project combines exploration, interaction, environmental puzzles, lighting changes, event-driven audio, supernatural AI, UI feedback, profiling, and playtesting in one connected space.

The project will help the team improve Unity scene construction, finite-state AI, collision and trigger design, event-driven feedback, real-time lighting, technical art, audio integration, performance debugging, and GitHub-based teamwork.

## Scene Summary

### Goal and player experience

The player must escape an unfamiliar house before a shadow entity finds them. The experience begins with uncertainty and exploration, then develops into fear as the lights fail, supernatural events appear, and the player must continue solving problems under pressure.

### Start and end boundaries

- **Start:** The player wakes inside a locked room and gains control.
- **Playable space:** One compact house interior with a visible or partially visible graveyard outside a window.
- **End:** The player collects the required clues or items, unlocks the main door, and crosses the escape trigger.
- **Failure:** The shadow entity captures the player or the player reaches zero health/sanity, leading to a failure screen and restart.
- **Scene end:** A short escape sequence confirms victory.

### Core gameplay loop

1. Explore rooms and inspect environmental details.
2. Find clues, keys, or objects that reveal the next step.
3. Interact with objects and solve compact environmental puzzles.
4. Respond to supernatural events while managing the threat and available light.
5. Unlock the exit, escape, and receive victory feedback.

### Game-state flow

`Intro and wake-up -> Exploration -> First clue -> Puzzle interaction -> Supernatural escalation -> Shadow encounter -> Final unlock -> Escape/Victory`

At any active stage, a capture or defeat event moves the player to `Failure -> Restart checkpoint`.

## Benchmark Reference

**Target game:** The Mortuary Assistant  
**Reference video:** [The Mortuary Assistant No Commentary Walkthrough Part 1 The First Shift](https://www.youtube.com/watch?v=x9Q_FEYF10k)

We will study the opening playable section for first-person interaction, environmental storytelling, pacing, lighting, audio cues, and supernatural interruptions. We will reproduce the design principles but simplify the content for a one-scene student project.

| System | Benchmark principle | Buried Outside adaptation |
|---|---|---|
| Controls and interaction | First-person movement and direct interaction with nearby objects. | Simple movement, camera look, one interaction input, and clear prompts. |
| Pacing | Routine tasks are interrupted by increasingly disturbing events. | Begin with exploration, then trigger blackout, apparition, and chase beats. |
| Environment | A compact interior creates familiarity and tension. | One small house with a strong sightline to the graveyard. |
| Audio | Ambience, object sounds, and unexpected cues build anticipation. | Footsteps, doors, whispers, light sounds, warning cues, and spatial ghost audio. |
| Simplification | The full game contains more tasks, entities, and outcomes. | One threat, two or three puzzles, one escape ending, and no procedural variation. |

## Project Features and Progression

Prototype features validate the idea early with graybox assets. Core features define the complete vertical slice. Stretch features are optional and will only be attempted after the core loop is stable.

| Feature category | Prototype features | Core features | Stretch features |
|---|---|---|---|
| Player and interaction | First-person movement, camera, and one test door. | Reliable movement, collision, prompts, inspection, and puzzle interactions. | More environmental interactions and accessibility options. |
| Escape objective | Hard-coded key opens a test exit. | Two or three linked clues/items unlock the final exit. | Alternative clue route or second ending. |
| Shadow threat | Scripted apparition at one trigger. | FSM with detection, stalking, chasing, attacking, and reset/capture. | Additional appearances or randomized scare timing. |
| Atmosphere | Placeholder lights and sound cues. | Flicker/blackout, readable lighting, ambience, SFX, music, and spatial audio. | Dynamic music layers, advanced VFX, and cinematic camera events. |
| Feedback and release | Debug text and restart key. | HUD/objective prompts, victory/failure screens, stable build, and profiling evidence. | Extra polish pass, second ending, and expanded post-processing. |

## Scope and Boundaries

### Must-have

- One complete playable house scene from wake-up to escape.
- First-person movement, camera, collision, and interaction prompts.
- Two or three small environmental puzzles or item-based interactions.
- One shadow entity controlled by a finite-state machine.
- Reliable capture, restart, victory, and failure states.
- Flickering or blackout lighting event.
- Basic HUD/objective feedback and pause/restart flow.
- Essential sound effects, ambience, music layer, and spatial ghost audio.
- Stable start-to-finish build with profiling evidence.

### Nice-to-have

- Additional ghost appearances or randomized scare timing.
- More advanced ghost animation and material effects.
- Cinematic camera moments.
- Optional environmental interactions and a second ending.
- Dynamic music layers reacting to threat intensity.

### Explicitly not doing

- Multiple levels or an open-world environment.
- Multiplayer or networked gameplay.
- Complex combat, firearms, or several enemy types.
- Procedural house generation or large-scale destruction.
- Full dialogue, voice acting, or branching narrative.
- Large inventory, crafting, or character progression.
- Additional content before the must-have scene is stable.

## Technical Competency Plan

| Competency | Planned implementation and evidence |
|---|---|
| Core gameplay systems engineering | Player movement, camera, interactable objects, objective manager, scene state flow, checkpoint restart, victory, and failure. |
| Physics and collision systems | Separate layers for player, environment, interactables, ghost, and trigger volumes. Controlled hit/detection volumes and cooldowns prevent repeated unintended hits. |
| AI behavior design | FSM: Hidden/Idle -> Appearing -> Stalking -> Chasing -> Attacking -> Recovering. Transitions use triggers, distance, line of sight, cooldowns, and capture conditions. |
| Real-time graphics pipeline | Dark but readable interior lighting, materials, limited dynamic lights, static lighting where possible, fog, shadows, and post-processing. |
| Technical art and polish | Animated doors and lights, ghost apparition/fade, blackout VFX, camera shake, particles, color grading, and vignette. |
| Audio systems design | Event-driven SFX, ambience, tension music, spatial ghost audio, and basic priority/volume mixing. |
| UI and UX feedback | Interaction prompts, objective, item/puzzle feedback, threat warning, pause/restart, failure, and victory screens. |
| Performance and debugging | Target stable 60 FPS on the team test machine; profile CPU, GPU, lighting, VFX, physics, and AI; track bugs in GitHub Issues. |
| Production and collaboration | Feature branches, pull requests, teammate review, issue-linked commits, GitHub Project board, builds, documentation, and milestone tags. |

## Learning Targets and Challenge Goals

- Implement and document a finite-state machine for a ghost.
- Build reliable interaction, trigger volumes, collision layers, hit detection, and restartable game-state flow.
- Use Unity lighting, materials, post-processing, VFX, animation, and camera effects while preserving readability.
- Design event-driven audio for ambience, spatial cues, supernatural events, and mixing priorities.
- Practice GitHub branches, pull requests, issue-linked commits, milestones, and code review.
- Profile CPU, GPU, lighting, physics, VFX, and AI costs and optimize based on measurements.
- Run structured playtests and convert observations into reproducible issues and prioritized fixes.

## Production Plan

### GitHub workflow

The project board will use `Backlog`, `Ready`, `In Progress`, `Review`, `Playtest`, and `Done`. Each issue will contain one actionable task, an owner, a milestone, dependencies, and acceptance criteria. Feature branches will be used for changes, and pull requests must receive at least one teammate review before merging into `main`.

### Roles and ownership

| Role | Primary ownership |
|---|---|
| Gameplay programmer | Player controls, interaction, objective flow, win/failure, checkpoints. |
| AI and systems programmer | Ghost FSM, detection, chase/attack logic, collision, and damage. |
| Technical artist/environment lead | House blockout, materials, lighting, camera, VFX, and readability. |
| Audio and UI lead | HUD, prompts, SFX, ambience, music, spatial audio, and mixing. |
| Producer and QA lead | Board, milestones, issue triage, testing, builds, and documentation. |

Specific team names will be added after assignments are confirmed.

## High Level Weekly Timeline

The schedule assumes approximately three hours per person per week of planned class-time work. Actual time will be recorded after tasks are completed.

| Task | Owner | Type | Status | Initial Estimate | Expected Time | Week # | Actual Time | Notes / Details / Description |
|---|---|---|---|---:|---:|---:|---:|---|
| Proposal and repository setup | Producer/QA | Milestone | In progress | 3 h | 3 h pp | 1 | — | Finalize proposal, repository, board, roles, and risk register. |
| Benchmark and feature matrix | Producer/design | Task | Not started | 2 h | 2 h pp | 1 | — | Document reference and prototype/core/stretch features. |
| House flow and graybox layout | Environment lead | Task | Not started | 3 h | 3 h pp | 2 | — | Create rooms, start point, puzzle route, threat route, and exit. |
| Player movement and interaction | Gameplay programmer | Task | Not started | 3 h | 3 h pp | 2 | — | Player can move, collide, inspect, and interact. |
| Puzzle and objective flow | Gameplay programmer | Task | Not started | 3 h | 3 h pp | 3 | — | Clue chain updates and unlocks the exit. |
| Ghost FSM and detection | AI programmer | Task | Not started | 3 h | 3 h pp | 3 | — | States transition through a test scenario. |
| Win, failure, and restart | Gameplay programmer | Task | Not started | 2 h | 2 h pp | 4 | — | Capture/failure and escape/victory work repeatedly. |
| First-pass UI and audio | Audio/UI lead | Task | Not started | 3 h | 3 h pp | 4 | — | Objective, prompt, danger, and result feedback are clear. |
| Phase 2 playtest report | Producer/QA | Milestone | Not started | 2 h | 2 h pp | 5 | — | Record findings, evidence, bugs, and next fixes. |
| Lighting, materials, VFX, and polish | Environment lead | Task | Not started | 3 h | 3 h pp | 6 | — | Start only after the complete core loop is playable. |
| Profiling and stability pass | AI/QA | Task | Not started | 3 h | 3 h pp | 7 | — | Capture performance evidence and fix blocking issues. |

## Risks and Mitigations

| Risk | Impact | Mitigation |
|---|---|---|
| Scope expansion | Content grows faster than the team can test. | Lock the must-have list and delay stretch features. |
| AI complexity | Ghost behavior becomes unreliable. | Start with a small FSM and test each transition. |
| Dark scene unreadability | Players miss clues, doors, or the threat. | Use lighting tests, contrast, readable interactables, and playtesting. |
| Performance problems | Frame rate drops from lighting, VFX, physics, or AI. | Profile regularly and simplify expensive systems. |
| Asset availability | Missing models or animations delay integration. | Use graybox and placeholders early; prioritize visible assets. |
| Puzzle confusion | Players cannot understand progression. | Test with classmates and add contextual clues. |
| Integration conflicts | Changes break other systems or delay builds. | Use small branches, pull requests, reviews, and weekly integration builds. |

## Phase 2 Checkpoint

By the Phase 2 checkpoint, the team will demonstrate:

- A player can start inside the house and understand the first objective.
- The player can move, collide, interact, and complete the basic puzzle route.
- The ghost can appear and transition through its planned AI states.
- Capture, restart, victory, and failure behavior work reliably.
- The exit can be unlocked and reached in the same build.
- Basic UI prompts and first-pass audio communicate important actions and danger.
- A playtest report lists observed problems, evidence, and planned fixes.

## Approval Request

The team requests instructor approval to continue to Phase 2. Phase 2 will begin with the graybox loop and must-have systems. Stretch features will remain optional until the core scene is stable, playable, and testable.
