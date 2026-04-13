# Cloud Coder

Autonomous overnight coding agent for Claude Code. Queue tasks in YAML, run them via Claude CLI while you sleep, and use self-healing audit-fix loops to hit any quality target.

## What It Does

Cloud Coder turns your local Claude CLI into an autonomous coding agent that works through a task queue while you're away. It was built during a production hardening sprint where it took a fintech platform from a 5.8/10 to 8.8/10 production readiness score overnight, executing 160+ tasks across security, reliability, testing, infrastructure, and compliance.

The killer feature is the **audit-fix loop**: Claude audits your codebase, scores it, generates fix tasks for every gap, executes them, and re-audits. It keeps cycling until it hits your target score.

## Skills

### run-queue
Create and execute overnight task queues. Define tasks in YAML with priorities, target repos, and detailed prompts. The runner handles sequencing, logging, idempotent reruns, and error recovery.

### audit-loop
Continuous improvement loop that scores your codebase and autonomously fixes gaps. Set a target score (e.g., 10/10) and walk away. It audits, generates tasks, executes them, re-audits, and repeats.

### check-progress
Monitor running tasks. See what's completed, what's running, failures, and score progression across audit rounds.

## Quick Start

1. Install the plugin: `claude plugin add VadneyK/cloud-coder`
2. 2. Say: "Queue up these 5 tasks to run overnight" or "Audit my codebase and fix everything until it's 10/10"
   3. 3. Cloud Coder creates the queue YAML and kicks off the runner
      4. 4. Check back with "What's the progress?"
        
         5. ## Requirements
        
         6. - Claude CLI installed and authenticated (Claude Max subscription - no API key needed)
            - - Python 3 with PyYAML (`pip install pyyaml`)
              - - A git repository
               
                - ## How It Was Built
               
                - This plugin was born from a real production hardening sprint at a fintech company. The overnight runner executed 20 tasks in the first run, then we built the audit-fix loop on top. Five rounds later, the codebase went from 5.8 to 8.8 production readiness with zero human intervention.
               
                - ## License
               
                - MIT
