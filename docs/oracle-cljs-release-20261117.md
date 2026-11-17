# cljs release bundle built by an oracle (2026-11-17)

ORACLE evidence, not a native build. The committed `etzhayyim-wasm-roukisho-actor-r0uk15h0/cljs/public/js/app.js` is the output of a JVM shadow-cljs
release run. No CI, gate, packaging or runtime path depends on it; the Tauri host only copies the
committed bundle. The dev build (`cljs-runtime/`) that was committed before is removed.

- Command: `cd etzhayyim-wasm-roukisho-actor-r0uk15h0/cljs && CLJ_CONFIG=<work>/clj-config ./node_modules/.bin/shadow-cljs -A:oracle release app (sources are .cljs; the :oracle alias only overrides the vanished git dependency kotoba-lang/kotoba@8c5b1bda jpGoDigitalDesignSystem with the local worktree)`
- Tools: node v26.0.0, npm 11.12.1, openjdk 21.0.1, shadow-cljs 2.28.20, kotoba-lang/kotoba@426ddd2a635b6714ad60a8d7852f4f802e3e54b6 (sparse lib/)
- Input: this repository at d5b340ecb81c2e314068df50b0854ac870c3bcbd.
- Output: `Build completed`, exit 0; `app.js` 292861 bytes, sha256 a38d66e331559215fc4d6f39d9e504e230d7c134e387be7995584bdd39454613.
- Check: the Tauri host built from it renders the page in Chromium under a CSP with no `'unsafe-eval'`
  (no EvalError). No console errors.
- Not shown: behaviour with live data; that a native (Amu) build produces the same code.
