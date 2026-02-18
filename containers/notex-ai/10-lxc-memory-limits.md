# LXC Memory Limits and Ollama

**Date:** 2026-02-18

## The Issue
Ollama reported insufficient memory (1.0GB) even though `free -h` showed 4GB total with 3.9GB cache.

## Root Cause
Linux uses free RAM for disk cache (buff/cache). This memory is available to applications when needed, but LXC cgroup limits may restrict how much Ollama can actually use.

## Solution Attempts
1. Restart container to clear cache
2. Verify cgroup memory limits
3. Try smaller model (phi3:mini) as fallback

## Current Status
Restarting work:D
