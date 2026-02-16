# UDM Pro Baseline Checklist

- [ ] Set static LAN IP to **192.168.5.12** (if you indeed intended `192.168.`, not `192.167.`)
- [ ] Create/verify LAN `192.168.5.0/24`
- [ ] DHCP scope (example): `192.168.5.100–200`, reservations for all statics
- [ ] Adopt USW-24-POE and set device IP to **192.168.5.23**
- [ ] Firewall rules: allow intra-LAN, restrict management from guest/networks (add later if you add VLANs)
- [ ] Port forwards (if any) for Plex remote access (or prefer Tailscale/ZeroTier)
- [ ] Enable IDS/IPS as desired (watch CPU impact)
- [ ] Backups: export Network Application backup and keep off-box
