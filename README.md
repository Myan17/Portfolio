# Myan Gupta — Portfolio

Personal portfolio site for **Myan Gupta** — backend, distributed systems, AI/ML infrastructure, and quant. CS @ University of Minnesota.

**Live:** https://myan17.github.io/Portfolio/

## About

A single-page, zero-build portfolio with interactive, in-browser demos — no video walkthroughs. Highlights include:

- **Quant Lab** — live Black-Scholes / Monte Carlo option pricer, SMA backtest with drawdown, and a 2-asset efficient frontier.
- **Consistent-hash ring** — interactive KV-store hash ring showing key remapping as nodes join and leave.
- **ICU latency demo** — visualizes the 360ms → 14ms P95 optimization.
- Featured works, full project catalogue, events, resume, and a Cal.com booking embed.

## Tech

Plain **HTML · CSS · Canvas · SVG · GSAP** — no framework, no build step. Deployed via **GitHub Pages**.

## Structure

```
index.html      # the entire site (markup, styles, and scripts)
resume.pdf      # downloadable / embedded resume
images/         # event photos (Origin House, QuackHacks, BETA Accelerator)
.github/        # GitHub Pages deploy workflow
```

## Local development

It's a static file — just open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deployment

Pushing to `main` triggers the GitHub Pages workflow in `.github/workflows/`, which publishes the repository root.

## Contact

- Email — gmyang03@gmail.com
- LinkedIn — https://www.linkedin.com/in/myangupta
- Book a call — https://cal.com/myan-gupta-7s6z87/15min
