# RAID‑5 Capacity Math (10 × 8 TB)

- Disk count: **10**
- Per-disk raw capacity (decimal): **8 TB**
- RAID‑5 usable (decimal TB): `(N − 1) × disk = 9 × 8 TB = 72 TB`
- Per-disk binary capacity (approx): **7.28 TiB**
- RAID‑5 usable (binary TiB): `9 × 7.28 TiB ≈ 65.5 TiB`

> Real-world formatted capacity will be slightly lower due to filesystem and metadata overhead (ZFS pools, snapshots, parity layout, 4k alignment, etc.). For ZFS, leave 10–20% free space to maintain performance.
