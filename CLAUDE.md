# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A single-page static HTML intranet portal ("Portal Corporativo") for the company, listing internal links (HR, IT support, DevOps platforms, local network devices) as clickable cards grouped by category. There is no build step, no package manager, and no test suite — the entire site is `index.html`, styled with Tailwind CSS loaded from the CDN (`<script src="https://cdn.tailwindcss.com">`).

## Working with this codebase

- Edit `index.html` directly. Each link category is a `<section>` containing a grid of `<a>` cards; each card follows the same structure: an emoji icon div, an `<h3>` title, and a `<p>` description. Follow this exact pattern when adding/editing links.
- To preview changes, simply open `index.html` in a browser (or serve the directory with any static file server) — Tailwind's CDN build handles styling live, no compilation needed.
- There is no linter, formatter, or test command configured for this repo.

## Deployment

Deployment is handled by Gitea Actions (`.gitea/workflows/deploy.yml`), not GitHub Actions, despite the repo being mirrored to/from GitHub. On every push to `main`, the workflow runs on a self-hosted runner labeled `rasberrypi` and executes a deploy script that lives on that server (`/home/arestoy/scripts/deploy-intranet-site.sh`) — the deploy logic itself is not part of this repo. Pushing to `main` immediately deploys, so treat commits to `main` as production changes.

Note: `.gitea/workflows/deploy.yml` may show as locally deleted in `git status` — check with the user before assuming the deploy workflow should be removed, since this could be in-progress/uncommitted work rather than an intentional change.
