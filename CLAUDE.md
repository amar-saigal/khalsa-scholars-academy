# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is an educational program design repository for **Khalsa Scholars Academy — College Prep Program (CCP)**. It contains:
- A static HTML website (`website/`) for parents and students
- LLM prompts (`prompts/`) for generating program documentation
- A versioned program configuration (`configuration/program_config.md`) as the single source of truth

## Website Development

The website is plain static HTML — no build step, no framework, no package manager. Open files directly in a browser.

- All pages live in `website/` as standalone `.html` files with embedded CSS and JS
- Design system: Navy `#1B2D5B`, Gold `#C8921A`, Cream `#FFF8EE`, Steel `#2E5D9E`
- Fonts: Playfair Display (headings) + DM Sans (body) via Google Fonts
- Layout uses CSS custom properties, Flexbox, Grid, and `clamp()` for fluid sizing

## Program Configuration

`configuration/program_config.md` is the versioned source of truth for all program parameters (pilot scope, staffing, communication structure, attendance thresholds, content sources). The prompts in `prompts/` are designed to reference this config block to generate consistent documentation.

When the config changes, update `notes/decision_log.md` to record the rationale.

## Key Program Architecture

- **Delivery model**: Flipped classroom via Google Classroom, 75-min Sunday sessions
- **Roles**: Program Lead → Content Curator → Tutors (2-3) → Mentors (4-6) → Students
- **Communication**: 4 WhatsApp groups (Leadership, Mentors/Tutors, Parents, Students)
- **Accountability**: Daily mentor checks (10-15 min), escalation after 3 consecutive missed days, Program Lead review after 2 weeks no engagement
- **Pilot scope**: Math only, 10-15 students, grades 7-11
