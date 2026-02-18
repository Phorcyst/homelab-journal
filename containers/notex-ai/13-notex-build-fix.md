# Fixing Notex Build Command

**Date:** 2026-02-18
**Tags:** notex, go, build, troubleshooting
**Location:** notex-ai container

## The Problem

When trying to build Notex with:
```bash
go build -o notex cmd/notex/main.go

package cmd/notex/main.go is not in std 
(/root/go/pkg/mod/golang.org/toolchain@v0.0.1-go1.25.0.linux-amd64/src/cmd/notex/main.go)

cd /root/notex
ls -la

-rw-r--r--  1 root root  4003 Feb 18 15:58 go.mod
-rw-r--r--  1 root root 28844 Feb 18 15:58 go.sum
-rw-r--r--  1 root root  5429 Feb 18 15:58 main.go
drwxr-xr-x  3 root root  4096 Feb 18 15:58 backend

#Key discovery: main.go is in the root directory, not in cmd/notex/

#Fix
go build -o notex main.go
