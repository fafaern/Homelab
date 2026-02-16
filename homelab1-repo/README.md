# Homelab1

Infrastructure-as-Documentation (IaD) repo for Ernie's homelab. This repository tracks network topology, IP plan, device inventory, RAID capacity math, and service notes for quick onboarding and recovery.

> **Note:** You listed the firewall as `192.167.5.12`. That network is different from the rest of the `192.168.5.0/24` devices. If this is a typo, consider `192.168.5.12` to keep everything in the same /24. I proceeded with **192.168.5.12** in diagrams and docs, and called out this discrepancy where relevant.

## Topology (Quick View)
See the Mermaid diagram in [`docs/network-diagram.mmd`](docs/network-diagram.mmd) or the rendered version in [`docs/NETWORK.md`](docs/NETWORK.md).

## Devices & IP Plan
- **Firewall**: Ubiquiti Dream Machine Pro (UDM Pro) — `192.168.5.12` (original input said `192.167.5.12`)
- **Switch**: Ubiquiti USW-24-POE — `192.168.5.23`
- **Storage/Server (Hypervisor)**: Ryzen 7 1700X / 32 GB RAM / 1 TB SSD boot / **10 × 8 TB** RAID‑5 — host `192.168.5.3`
- **VMs / Services**
  - Plex — `192.168.5.4`
  - Jellyfin (you wrote *Jellyjin*; assuming **Jellyfin**) — `192.168.5.6`
  - TrueNAS — `192.168.5.7`
  - Docker host — `192.168.5.8`
  - Immich — `192.168.5.9`
  - Stash — `192.168.5.10`
  - Paperless-ngx — `192.168.5.11`

## RAID-5 Usable Capacity (10 × 8 TB)
- Usable (decimal TB): `(10 − 1) × 8 TB = 72 TB`
- Approx usable (TiB): `(10 − 1) × 7.28 TiB ≈ 65.5 TiB`
- Expect additional filesystem/metadata overhead when provisioned by TrueNAS/ZFS.

Details and math in [`storage/RAID5-capacity.md`](storage/RAID5-capacity.md).

## What This Repo Contains
- `docs/` — network diagram (Mermaid), rendered network doc, and IP plan
- `inventory/` — human-friendly inventory in YAML
- `storage/` — RAID math and storage layout notes
- `udm-pro/` — checklist for UDM Pro baseline settings
- `switch/` — USW-24-POE port plan template
- `vms/` — per-VM service notes (Plex, Jellyfin, TrueNAS, Docker host, Immich, Stash, Paperless-ngx)

## How to Use
1. Keep this repo updated whenever you change IPs, VLANs, ports, or add services.
2. Export/attach device backups (UDM Pro site backup, TrueNAS config, etc.) in a private location (do **not** commit secrets here). Reference their locations in the notes files.
3. Use the checklists for rebuilds and DR.

---
**Owner**: Ernie Florentino — Network Administrator
