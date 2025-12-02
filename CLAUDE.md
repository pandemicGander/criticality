# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a self-contained HTML/JavaScript canvas simulation demonstrating fire spread dynamics on a 240x240 pixel grid. The simulation models:
- Tree growth (black pixels appearing over time)
- Fire ignition (random fires starting in forested areas)
- Fire spread (probabilistic spread to neighboring pixels)
- Burn-out (fire turns pixels back to empty/white)

## Running

Open `critical.html` directly in a browser - no build step or server required.

## Architecture

Single-file application with three state sets tracking pixel states:
- `offStates` - empty pixels (white)
- `onStates` - forested pixels (black)
- `fireStates` / `fireStatesToFinish` - burning pixels (red)

Key parameters at the top of the script:
- `fireSpreadProbability` (0.3) - chance fire spreads to each neighbor
- `newFireStartProbability` (0.02) - chance of spontaneous fire per frame
- `growthRate` (10) - pixels added to forest per frame
