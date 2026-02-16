# Network & Topology

> Rendered view of the Mermaid diagram from `network-diagram.mmd`. If your viewer supports Mermaid, it will render below.

```mermaid
%%{init: {'theme': 'default'}}%%
flowchart LR
    subgraph Internet
      WAN[ISP / Internet]
    end

    UDM[UDM Pro
192.168.5.12]
    SWITCH[USW-24-POE
192.168.5.23]

    WAN --> UDM --> SWITCH

    HYP[Storage/Hypervisor
Ryzen 1700X, 32GB, 1TB SSD boot
10x8TB RAID5
192.168.5.3]

    PLEX[Plex VM
192.168.5.4]
    JELLY[Jellyfin VM
192.168.5.6]
    TRUENAS[TrueNAS VM
192.168.5.7]
    DOCKER[Docker Host VM
192.168.5.8]
    IMMICH[Immich VM
192.168.5.9]
    STASH[Stash VM
192.168.5.10]
    PAPERLESS[Paperless-ngx VM
192.168.5.11]

    SWITCH --- HYP
    HYP --- PLEX
    HYP --- JELLY
    HYP --- TRUENAS
    HYP --- DOCKER
    HYP --- IMMICH
    HYP --- STASH
    HYP --- PAPERLESS

    classDef device fill:#0ea5e9,stroke:#0369a1,color:#fff,stroke-width:1px;
    classDef vm fill:#10b981,stroke:#065f46,color:#fff,stroke-width:1px;

    class UDM,SWITCH,HYP device;
    class PLEX,JELLY,TRUENAS,DOCKER,IMMICH,STASH,PAPERLESS vm;
```

## IP Plan (192.168.5.0/24)
| Device | Role | IP | Notes |
|---|---|---:|---|
| UDM Pro | Firewall/Router | 192.168.5.12 | Original said `192.167.5.12` — assumed typo |
| USW-24-POE | Core Switch | 192.168.5.23 | UniFi managed |
| Storage/Hypervisor | Compute + Disks | 192.168.5.3 | 10×8TB RAID5 behind TrueNAS |
| Plex | Media Server | 192.168.5.4 | VM |
| Jellyfin | Media Server | 192.168.5.6 | VM |
| TrueNAS | Storage OS | 192.168.5.7 | VM / Bare-metal mgmt depends on your setup |
| Docker Host | Container Node | 192.168.5.8 | VM |
| Immich | Photos | 192.168.5.9 | VM |
| Stash | Media Indexer | 192.168.5.10 | VM |
| Paperless-ngx | Docs | 192.168.5.11 | VM |
