# Trust-Aware, Emotion-Adaptive Agentic Assistant

This repository contains a lightweight agentic AI prototype that explores how an autonomous system should decide **when to act, when to ask for confirmation, and how much autonomy to take**, based on user trust and emotional context.

Rather than focusing on task optimization or feature completeness, this project is intentionally designed to study **human–AI collaboration and autonomy calibration** in a controlled setting.

---

## Motivation

As AI systems become more capable, the challenge is no longer *what* they can do, but *how* they should behave around humans. Static autonomy—where an assistant always acts or always asks often leads to over automation or user frustration.

This project addresses a central question in agentic AI and human computer interaction:

**How should an autonomous agent dynamically adjust its behavior based on human trust and emotional state, while remaining transparent and controllable?**

---

## Approach

The system implements a closed loop agent architecture in which autonomy is not fixed, but continuously adapted. Trust is modeled as a long term signal derived from user behavior, while emotion is treated as a short term contextual signal that can temporarily override autonomy.

The agent operates in a simple task planning domain, allowing the focus to remain on decision making behavior rather than task complexity. At every step, the agent provides an explanation for its actions, ensuring transparency and preserving human oversight.

---

## System Overview

The interaction loop follows this sequence:

User input is first analyzed to infer a coarse emotional state (calm or stressed). In parallel, the agent maintains a trust state that evolves over time based on whether the user accepts, edits, or rejects previous decisions. These two signals are passed to an autonomy controller, which determines whether the agent should ask for confirmation, suggest a plan, or act directly.

Once a decision is made, the agent selects up to three tasks, presents them according to the chosen autonomy level, and generates a concise explanation describing why that level of autonomy was selected. User feedback is then logged and used to update trust for future interactions.

---

## Autonomy Behavior

The agent supports three autonomy modes:

- **Ask**: The agent seeks explicit confirmation before proceeding, used when trust is low or the user appears stressed.
- **Suggest**: The agent proposes a plan and waits for user feedback, used during moderate trust.
- **Act**: The agent proceeds autonomously and informs the user, used when trust is high and the context is calm.

Crucially, emotional stress can temporarily reduce autonomy regardless of trust level, reflecting a human-centered design choice that prioritizes user comfort and control.

---

## Trust and Emotion Modeling

Trust is inferred from observable user behavior rather than explicit ratings. Acceptance increases trust, rejection decreases it, and edits are treated as neutral collaboration signals. Trust evolves gradually, preventing sudden or unstable shifts in behavior.

Emotion is modeled conservatively using simple linguistic cues. Stress is not treated as a diagnosis, but as a contextual indicator that the agent should slow down and re-engage the user. This separation between long term trust and short term emotion allows the agent to behave predictably and ethically.

---

## Why This Design Matters

This project demonstrates that meaningful agentic behavior does not require large models or complex interfaces. By isolating autonomy decisions and making internal state explicit, the system highlights core challenges in trustworthy AI: calibration, transparency, and human control.

The prototype is intentionally minimal, making it easy to evaluate, extend, and adapt to different research directions in agentic AI, HCI, and responsible autonomy.

---

## Running the System

The agent is implemented in a single Jupyter Notebook. After running all cells, users can provide tasks as a comma separated list and respond with simple feedback (`yes`, `no`, `accept`, `reject`, or `edit`) when prompted. The agent’s internal state is printed after each interaction to make its reasoning traceable.

---

## Scope and Limitations

This is not a production assistant, nor is it intended to optimize task completion. It is a research oriented prototype designed to explore autonomy behavior in isolation. The simplicity of the system is a deliberate design choice rather than a limitation.

---

## Conclusion

This project offers a concrete demonstration of human centered agentic AI, showing how autonomy can be earned, reduced, and explained in response to human behavior and context. It serves as a foundation for future exploration into adaptive, trustworthy autonomous systems.

---

**Author:**  
Developed as a winter project to demonstrate research fit for work in agentic AI and human–AI interaction.
