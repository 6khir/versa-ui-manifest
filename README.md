# versa-ui-manifest

The signed UI manifest for VERSA CLASS's browser automation: selector ladders, button names,
busy/done/limit phrases, Canva anchors and flow recipes for Gemini, ChatGPT, Meta AI, Canva and TPT.

- `versa-ui-manifest.json` — the manifest (public data, no secrets).
- `versa-ui-manifest.sig` — its Ed25519 signature. The app ignores a manifest whose signature does not
  verify against the public key baked into the build.

The app fetches this file on start and every hour, keeps the last verified copy, and falls back to the
copy bundled with the build. Publish only with `pnpm manifest:publish` from the VERSA repo, which signs
with the private key that stays on the owner's Mac.
