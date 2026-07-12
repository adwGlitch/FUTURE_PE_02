# Prompt Engineering Documentation: Reminderr UGC Campaign

This document details the prompt engineering methodology, strategies, and design decisions used to generate the Reminderr UGC Ad Content Pack.

---

## 1. Prompt Objective
The goal was to engineer a set of prompts that instruct a Large Language Model (LLM) to act as a seasoned performance marketer, producing high-converting, natural-sounding social media content. The target was to eliminate typical robotic AI jargon and output structure-ready files that require zero post-editing.

---

## 2. Prompt Design & Core Techniques

### Persona Prompting
We assigned multi-disciplinary expert personas to the LLM:
*   *Prompt Engineer:* To structure prompt logic, enforce syntax rules, and define formatting parameters.
*   *UGC Creative Director / Copywriter:* To write natural, conversational dialogue featuring authentic pauses and informal phrasing.
*   *Performance Marketing Strategist:* To ensure every creative asset contains conversion-focused hooks and explicit call-to-actions.

### Zero-Shot Prompting
We utilized zero-shot prompts by providing clear structural templates and detailed context without feeding the model previous scripts. This tested the model's ability to extrapolate and generate highly original, contextually relevant scripts based purely on detailed rules.

### Constraints (Negative Prompting)
To achieve a human tone, strict negative constraints were implemented:
*   **Forbidden Buzzwords:** *Revolutionary, game-changing, cutting-edge, next-gen, unlock your potential, transform your life.*
*   **Tone Restrictors:** Avoid exclamation-heavy enthusiasm, formal grammar, or direct corporate pitching. Use casual fillers (e.g., *"honestly," "literally," "so"*).

### Output Formatting
The model was instructed to format all output in clean Markdown syntax with designated headers and markdown tables for storyboards, ensuring easy copy-pasting to Git repositories.

---

## 3. Iterative Prompt Refinement
The development of the final prompt proceeded in three distinct stages:

### Prompt V1 (Initial Trial)
*   **Approach:** A basic instruction asking for UGC ad scripts for Reminderr.
*   **Result:** The generated copy felt robotic and relied heavily on corporate marketing clichés ("revolutionize your day"). Pacing was too fast, and the scripts read like TV commercials rather than real user videos.

### Prompt V2 (Structured Persona & Negative Constraints)
*   **Approach:** Introduced the performance marketer persona, added the Hook-Problem-Solution structure, and banned specific buzzwords.
*   **Result:** The tone improved significantly. The scripts started sounding like real people talking. However, they lacked detailed storyboards and specific platform adaptations.

### Final Prompt (Multi-Platform & Visual Storyboarding)
*   **Approach:** Added instructions to generate storyboards with camera angles, visual cues, and 40 short-form platform variants. Enforced strict markdown structure guidelines.
*   **Result:** Generated the complete portfolio-ready content pack with precise formatting, visual direction, and clear distinction between platforms.

---

## 4. Why the Final Prompt Performed Better
1.  **Frictionless Formatting:** By providing explicit Markdown layout templates within the prompt, the model returned files that fit directly into our folder structure.
2.  **Visual Directives:** Specifying camera angles and on-screen text constraints forced the model to think like a video director, not just a writer.
3.  **Platform Distinctions:** Forcing separate parameters for TikTok, Instagram Reels, Facebook Reels, and YouTube Shorts prevented homogeneous copy.

---

## 5. Lessons Learned
*   **Context is Key:** Providing the brand personality ("modern, friendly, minimal") and the target audience pain points directly within the prompt drastically reduces the need for revisions.
*   **Constraint Enforcement:** Large language models require clear, capitalized list constraints (negative prompt lists) to consistently avoid marketing clichés.
*   **Structure Prompts for Output:** If you want a table, provide the table headers in the prompt. If you want a specific length, define it in seconds rather than words.
