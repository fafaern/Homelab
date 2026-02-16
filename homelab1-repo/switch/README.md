# USW-24-POE Port Plan (Template)

| Port | Connected To | Purpose | PoE |
|---:|---|---|:---:|
| 1 | UDM Pro | Uplink | Off |
| 2 | Storage/Hypervisor | Server | Off |
| 3 | Plex VM (if dedicated NIC) | Media | Off |
| 4 | Jellyfin VM (if dedicated NIC) | Media | Off |
| 5 | TrueNAS (IPMI / Mgmt if available) | Mgmt | Off |
| 6 | Docker Host VM (if dedicated NIC) | Containers | Off |
| 7 | Immich VM (if dedicated NIC) | Photos | Off |
| 8 | Stash VM (if dedicated NIC) | Indexer | Off |
| 9 | Paperless-ngx VM (if dedicated NIC) | Docs | Off |
| 10-24 | Access devices / APs | Client/Infra | As needed |

> Adjust based on your physical NIC layout. If using a hypervisor vSwitch, most VMs will share the hypervisor uplink.
