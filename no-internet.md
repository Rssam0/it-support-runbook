# No internet

Work from the device outward. Stop when you find the fault.

1. **Is it only this device?** Try another device on the same Wi-Fi. If others work, the problem is local.
2. **Physical/Wi-Fi:** cable plugged in? Airplane mode off? Wi-Fi connected to the right network?
3. **Do I have an IP address?**
   - Windows: `ipconfig`
   - Linux: `ip a`
   An address starting with `169.254.` (Windows) means DHCP failed. Renew: `ipconfig /release` then `ipconfig /renew`.
4. **Can I reach the router?** `ping <default gateway>` (the gateway is shown in `ipconfig` / `ip route`).
5. **Can I reach the internet by IP?** `ping 8.8.8.8`. If yes but names fail, it is DNS.
6. **Is DNS working?** `nslookup example.com`. Try another DNS server (for example 1.1.1.1). Flush cache: `ipconfig /flushdns`.
7. **Still failing?** Restart the router, then escalate with notes of every step above.

## Why this order
Each step rules out one layer (device, link, IP, gateway, internet, DNS) so I don't guess.
