# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-file HTML portfolio (`portfolio.html`) — all HTML, CSS, and JavaScript in one file. No build step, no dependencies, no package manager.

## Architecture

Three full-viewport scroll-snap sections: `#about`, `#experience`, `#portfolio`. Content language is Traditional Chinese (zh-TW).

**CSS custom properties** (`:root`):
- `--bg` / `--bg2` — warm off-white backgrounds
- `--surface` — card/box white
- `--accent` — green; `--accent2` — gold/brown
- `--text` / `--muted` / `--subtle` — text hierarchy

**JavaScript** (inline `<script>`):
- `--vh` CSS var patched on load/resize to fix mobile viewport height
- `IntersectionObserver` (threshold 0.5) keeps top nav + side dots in sync with visible section
- Second `IntersectionObserver` (threshold 0.12) triggers `.fade-in → .visible` animations; About section elements are made visible immediately on load
- Scroll-snap is disabled via CSS on mobile (`max-width: 767px`) and landscape small screens (`orientation:landscape` and `max-height:500px`)

Fonts loaded from Google Fonts: `DM Serif Display`, `DM Sans`, `Noto Sans TC`.
