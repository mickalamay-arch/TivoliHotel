:root {
  color-scheme: light;
  --bg: #0f172a;
  --fg: #0f172a;
  --muted: #64748b;
  --card: #ffffff;
  --accent: #2563eb;
}

* {
  box-sizing: border-box;
}

html,
body {
  width: 100%;
  min-width: 320px;
  height: 100%;
  margin: 0;
  overflow: hidden;
  background: var(--bg);
  font-family:
    Inter,
    ui-sans-serif,
    system-ui,
    -apple-system,
    BlinkMacSystemFont,
    "Segoe UI",
    sans-serif;
}

.page-shell {
  position: fixed;
  inset: 0;
  width: 100vw;
  height: 100vh;
  height: 100dvh;
  overflow: hidden;
}

.reference-frame {
  position: absolute;
  inset: 0;
  z-index: 2;
  display: block;
  width: 100%;
  height: 100%;
  border: 0;
  background: #ffffff;
}

.fallback {
  position: absolute;
  inset: 0;
  z-index: 1;
  display: grid;
  place-items: center;
  padding: 24px;
  background:
    radial-gradient(circle at 20% 20%, rgba(37, 99, 235, 0.24), transparent 34%),
    radial-gradient(circle at 80% 0%, rgba(14, 165, 233, 0.22), transparent 32%),
    var(--bg);
  opacity: 0;
  visibility: hidden;
  transition:
    opacity 240ms ease,
    visibility 240ms ease;
}

body.frame-delayed .fallback,
body.frame-error .fallback {
  z-index: 3;
  opacity: 1;
  visibility: visible;
}

.fallback-card {
  width: min(620px, 100%);
  padding: 28px;
  border-radius: 24px;
  background: var(--card);
  color: var(--fg);
  box-shadow: 0 28px 80px rgba(2, 6, 23, 0.38);
}

.fallback-card h1 {
  margin: 8px 0 12px;
  font-size: clamp(1.7rem, 4vw, 2.7rem);
  line-height: 1.05;
  letter-spacing: -0.04em;
}

.fallback-card p {
  margin: 0 0 18px;
  color: var(--muted);
  line-height: 1.6;
}

.fallback-card code {
  padding: 0.15rem 0.35rem;
  border-radius: 0.4rem;
  background: #f1f5f9;
  color: #334155;
}

.eyebrow {
  margin: 0;
  color: var(--accent) !important;
  font-size: 0.78rem;
  font-weight: 800;
  letter-spacing: 0.18em;
  text-transform: uppercase;
}

.fallback-card a {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  min-height: 44px;
  padding: 0 18px;
  border-radius: 999px;
  background: var(--accent);
  color: #ffffff;
  font-weight: 800;
  text-decoration: none;
}

.fallback-card a:focus-visible {
  outline: 3px solid rgba(37, 99, 235, 0.3);
  outline-offset: 4px;
}
