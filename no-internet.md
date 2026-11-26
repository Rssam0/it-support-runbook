# No internet

Work from the device outwards, stop when you find the fault.

1. is it just this device? try another one on the same wifi. if that one works, the problem is the device
2. basics: cable in, airplane mode off, on the right wifi
3. got an IP? `ipconfig` on windows, `ip a` on linux. 169.254.x.x on windows means DHCP failed - `ipconfig /release` then `ipconfig /renew`
4. can you ping the router? (the default gateway from ipconfig)
5. can you reach the internet by IP? `ping 8.8.8.8`. if yes but websites don't load, it's DNS
6. `nslookup example.com` to check DNS. try 1.1.1.1 as the server, and `ipconfig /flushdns`
7. still nothing: restart the router, then escalate with notes of everything you tried

The order matters because each step crosses off one layer (device, link, IP, gateway, internet, DNS), so you're not guessing.
