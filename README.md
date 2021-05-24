# Bypass Hotspot Limit

### Requirements:
1. You have a mobile data plan with **unlimited mobile data** but limited hotspot pool.
2. This will just make your data usage on the computer counted as the mobile data usage limit, instead of using the hotspot usage limit (so you **need** unlimited mobile data).


### For Ubuntu/Linux

*To temporarily change the value until the next reboot, use the following command:*

`sudo sysctl -w net.ipv4.ip_default_ttl=65`

### For Ubuntu/Linux (alternative)

*To permanently change the value even if the host is rebooted you have a number of options:*

- Edit the `/etc/sysctl.conf` file
- Create a new file with a `.conf` extension in the `/etc/sysctl.d/` directory
- Edit an existing file in the `/etc/sysctl.d/` directory

Whichever route you choose, add this to the file, save and exit:

`net.ipv4.ip_default_ttl = 65`

Then reload the kernel parameters using the following command along with the name of the file you added the parameter to:

`sudo sysctl -p /etc/sysctl.conf`


---
### For Windows
CMD: `netsh int ipv4 set glob defaultcurhoplimit=65`

---
What is TTL and Hop Limit?

https://packetpushers.net/ip-time-to-live-and-hop-limit-basics/

How does changing the TTL / Hop Limit help in bypassing hotspot limit?

https://www.reddit.com/r/Android/comments/8p69ez/bypassing_verizons_unlimited_plans/

Note: No guarantee to work in all situations, I am using Windows/Ubuntu dual boot with Yoodo data plan.
