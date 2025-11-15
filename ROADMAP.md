# Project Roadmap

This document outlines the development priorities for Unduckified, based on the **Value vs. Effort** framework.

*   **Value:** How much impact will this have on the user experience? (High, Medium, Low)
*   **Effort:** How complex is this to build? (High, Medium, Low)

---

## P1: Quick Wins (High Value, Low Effort)

These features offer significant user value for a relatively low implementation cost, making them ideal candidates for early development.

*   **Advanced Keyboard Shortcuts:**
    *   **Value:** High
    *   **Effort:** Low
    *   **Notes:** Improves accessibility and workflow for power users. Can be implemented incrementally.

*   **Settings Sync (Export/Import):**
    *   **Value:** High
    *   **Effort:** Low
    *   **Notes:** Crucial for users with multiple devices/browsers. Manual export/import to JSON file is low effort.

*   **Offline Mode Enhancements:**
    *   **Value:** Medium
    *   **Effort:** Low
    *   **Notes:** Ensures robust offline access to all data. Leverages existing PWA capabilities.

*   **Ephemeral Mode:**
    *   **Value:** Medium
    *   **Effort:** Low
    *   **Notes:** Good privacy option, involves conditional logic for search history storage.

*   **Help Page / Cheatsheet:**
    *   **Value:** High
    *   **Effort:** Low
    *   **Notes:** Central documentation for bang discovery and usage.

---

## P2: Core Features (High Value, Medium/High Effort)

These features are central to the app's mission and offer substantial user value, but require more significant development effort. They form the backbone of the enhanced Unduckified experience.

*   **Bang Aliases & Categories:**
    *   **Value:** High
    *   **Effort:** Medium
    *   **Notes:** A significant quality-of-life improvement for organizing and personalizing bangs. Requires UI and logic changes.

*   **Fuzzy Bang Search:**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** Makes the app much more user-friendly. A great candidate for the first Rust/WASM module.

*   **Visual Bang Browser:**
    *   **Value:** High
    *   **Effort:** Medium
    *   **Notes:** Improves bang discoverability and onboarding. Requires a new UI page/modal.

*   **Contextual Bang Suggestions:**
    *   **Value:** High
    *   **Effort:** Medium
    *   **Notes:** Makes the app more intuitive and efficient by suggesting bangs in real-time.

*   **Bang Parameters/Arguments:**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** Significantly expands bang power and flexibility. Requires robust parsing and URL construction logic.

*   **Natural Language to Bang:**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** "Wow" feature, lowers barrier for complex bang usage. Requires robust NLP model integration (external API).

*   **Intelligent Bang Suggestions:**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** Makes the app feel smarter. Requires client-side ML (Rust/WASM) or external API for query intent analysis.

*   **Privacy Redirects:**
    *   **Value:** High
    *   **Effort:** Medium
    *   **Notes:** Aligns with privacy demands. Requires maintaining a list of privacy-respecting frontends and modifying redirect logic.

*   **Tracker Stripping:**
    *   **Value:** High
    *   **Effort:** Medium
    *   **Notes:** Significant privacy win. Requires robust regex/parsing for URL parameters.

*   **Proactive & Predictive Assistance:**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** Makes the app feel incredibly smart and personalized. Requires sophisticated client-side logic (Rust/WASM) to monitor context.

*   **Generative & Content-Aware (AI-Powered Bang Creation, In-App Summarization, Query Expansion):**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** "Wow" features for productivity. Requires integration with powerful AI models (external APIs/client-side ML).

*   **Multi-Modal Input (Image-based Bangs):**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** New input method, requires image processing APIs.

*   **Multi-Modal Input (Audio-based Bangs):**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** New input method, requires audio processing APIs.

*   **Personal Assistant Actions (Todo List / Calendar):**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** Integrates with productivity workflows, requires third-party API integrations and authentication.

*   **Interactive Tutorial:**
    *   **Value:** High
    *   **Effort:** Medium
    *   **Notes:** Crucial for new user adoption and understanding the app's power.

---

## P3: Nice-to-Haves (Low/Medium Value, Low Effort)

These features offer some value but are not critical for the core experience. They can be tackled if time and resources permit, or after higher-priority items are complete.

*   **Bang Usage Statistics:**
    *   **Value:** Low
    *   **Effort:** Low
    *   **Notes:** A fun statistic for users to see, but not a core feature. Involves expanding the existing search counting logic.

*   **Temporary Default Bang:**
    *   **Value:** Medium
    *   **Effort:** Medium
    *   **Notes:** Useful for session-specific workflows. Requires session state management and UI work.

*   **Drag-and-Drop Custom Bangs:**
    *   **Value:** Medium
    *   **Effort:** Medium
    *   **Notes:** Improves UX for managing custom bangs in settings.

*   **Personalization (Personalized Bang Ranking, AI-Curated "Bang of the Day"):**
    *   **Value:** Medium
    *   **Effort:** Medium
    *   **Notes:** Improves UX by tailoring the app to individual preferences. Requires client-side learning algorithms.

*   **Achievements:**
    *   **Value:** Low
    *   **Effort:** Medium
    *   **Notes:** Fun for some users, but not core utility. Requires tracking and UI.

*   **"Bang of the Day":**
    *   **Value:** Low
    *   **Effort:** Low
    *   **Notes:** Encourages discovery. Involves fetching/selecting a daily bang.

*   **Opt-In Affiliate Bangs:**
    *   **Value:** Low
    *   **Effort:** Medium
    *   **Notes:** Potential revenue, but dependent on user opt-in and affiliate terms.

*   **"Sponsor a Feature":**
    *   **Value:** Low
    *   **Effort:** Low
    *   **Notes:** Community engagement/funding model.

---

## P4: Long-Term Epics (Low Value, High Effort)

These features represent significant undertakings with potentially lower immediate impact relative to their cost, or are highly experimental. They should be revisited much later in the project's lifecycle.

*   **Bang Chains:**
    *   **Value:** Medium
    *   **Effort:** High
    *   **Notes:** A niche power-user feature that requires significant logic changes for parsing and redirection.

*   **Community Bangs (Shared Repository):**
    *   **Value:** Medium
    *   **Effort:** High
    *   **Notes:** Fosters community but requires significant backend development, moderation, and app integration.

*   **Browser Extension Companion:**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** Enhances UX with quick access and on-page functionality, but is essentially a separate application to build and maintain.

*   **Bang Packs:**
    *   **Value:** Medium
    *   **Effort:** High
    *   **Notes:** Allows sharing curated bang collections. Requires creation/export/import mechanisms and potentially discovery.

*   **Discover Page:**
    *   **Value:** Medium
    *   **Effort:** High
    *   **Notes:** Crucial for community engagement and bang pack discoverability. Requires backend and UI.

*   **Bangs as Commands (DSL):**
    *   **Value:** High
    *   **Effort:** High
    *   **Notes:** A transformative feature expanding bang utility. Requires robust DSL design, parser, and execution engine.
