---
name: frontend-changes
description: Use when changing user-visible frontend UI, including layout, styling, typography, copy, components, responsive behaviour, or animations. Verify the actual result and attach desktop and mobile screenshots by default.
---

# Frontend changes

Screenshots are part of the handoff for user-visible frontend changes, not an
optional follow-up. Do not wait for someone to ask to see the result. Skip them
only when the user explicitly opts out or rendering is blocked; explain a blocker.
This skill does not expand the scope of work that belongs in this chat.

## Verify the actual change

1. Run the relevant available checks (at least `git diff --check`) and open or
   update the pull request.
2. Look for a deployment preview in PR comments, checks, or deployment metadata.
   Verify that it was built from the latest pushed commit. If deployment is still
   running, wait within the turn when practical. Never screenshot the unchanged
   production site and present it as the PR result.
3. Read and follow the `browser-run` skill. Use Cloudflare Browser Run to capture
   the affected page at desktop and mobile sizes (defaults: 1280×800 and 390×844).
   Capture the actual app, not a reconstructed HTML mock-up. A cloud browser cannot
   reach the sandbox through localhost; do not assume a local dev server is
   accessible or expose one through an unapproved tunnel.
4. Prefer viewport screenshots that show the changed UI with enough surrounding
   context. Pick the affected route, not automatically the homepage. For shared
   components, also check another representative route where useful. Avoid huge
   full-page captures or an exhaustive screenshot matrix.
5. Open the saved images with `readFile` and inspect them before sharing. Check
   requested copy, typography, colours, alignment, spacing, clipping, overflow,
   and responsive visibility. Fix discrepancies, push the changes, and capture
   the updated deployment rather than sharing stale screenshots. Source checks
   complement visual inspection; neither proves the other.

## States and limitations

- A still screenshot proves only the captured state, not an animation, hover,
  focus, keyboard behaviour, or reduced-motion handling. State which of those
  were actually checked; do not claim verification from source alone.
- Follow Browser Run limits: no browser sessions, DevTools connections, or
  workarounds for refused actions. If interaction is needed but unavailable,
  describe the remaining manual check.
- If the preview fails, requires unavailable access, is stale, or Browser Run is
  disabled, say exactly what blocked screenshots. Still share the PR and checks
  that did run; do not imply visual verification or ask for more tools before
  checking the existing preview and browser capability.

## Show the result

- Save screenshots under `/workspace` with clear desktop/mobile filenames.
- Call `attachFile` for the screenshots so they are posted with the thread reply.
  Merely saving or opening an image does not share it. Respect attachment limits.
- Keep the reply short: link the PR or preview, identify the screenshots, and
  mention any unverified states or blockers. Distinguish a preview from a merged
  or live change. Record checks and visual verification in the PR description.
