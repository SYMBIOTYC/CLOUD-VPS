# CLOUD-VPS

## Purpose

Repository boundary for persistent VPS and edge-service workloads in the Symbiotyc Compute Federation. This repository is a bootstrap surface; it does not provision or operate production servers yet.

## Host baseline

Target persistent hosts: Ubuntu Server 24.04 LTS or Debian stable, x86-64 or ARM64 as workload-compatible. Require unattended security updates, SSH key authentication, least-privilege service accounts, a host firewall, time synchronization, disk and memory monitoring, and a documented recovery path.

## Separation from Linux CI

- Repository validation runs on temporary GitHub-hosted `ubuntu-24.04` runners.
- Persistent VPS hosts are provisioned and monitored independently.
- Public pull-request workflows must never execute on persistent/self-hosted hosts.
- Do not store permanent cloud keys, SSH private keys, or production tokens in this public repository.

## Baseline

The initial CI workflow validates repository metadata and emits a run receipt. It is not evidence that a VPS exists or that a persistent worker is online.
