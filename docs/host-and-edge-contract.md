# VPS and Edge Worker Boundary

## Purpose
Define the boundary for persistent VPS and edge workloads. This repository does not provision production hosts.

## Host baseline
Ubuntu Server 24.04 LTS or Debian stable; supported x86-64/ARM64; unattended security updates; SSH key authentication; non-root service accounts; host firewall; time synchronization; disk/memory monitoring; documented backup and recovery.

## Workload lifecycle
Provision -> harden -> register -> heartbeat -> schedule -> drain -> patch/restart -> re-register. Host identity must be independent from a mutable IP address. Secrets belong in a managed secret store and must never be committed.

## Isolation
- Public pull-request workflows use ephemeral GitHub-hosted runners only.
- Persistent hosts do not execute untrusted PR code.
- Edge services expose only explicitly approved ports and authenticated health endpoints.
- Worker dispatch must enforce per-tenant quotas, job limits and audit records.

## Current status
The bootstrap CI workflow validates this repository only. No VPS, gateway, CDN, storage, messaging service or persistent worker is claimed as deployed.
