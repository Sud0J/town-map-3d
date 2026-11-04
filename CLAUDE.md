# Workflow for Claude

- Owner's standing rule: when asked to fix or change something, make the change, show the result
  (screenshots of desktop + phone width), and WAIT for the owner to confirm it's good enough.
- After the owner confirms: commit and push straight to `main` (no PR, no branch). `main` is what
  GitHub Pages serves, so the push is the deploy: https://sud0j.github.io/town-map-3d/
- Never push before that confirmation. Pull/rebase on `origin/main` before pushing.
- To undo a bad deploy: `git revert <sha>` and push (no force-push).

# Project

Single `index.html` + vendored three.js r160 in `vendor/`. No build step. Test with
`python3 -m http.server` and Playwright (chromium with `--use-angle=swiftshader`).
