date: 2021-03-06
---

Google, YouTube and Bing all provide means to enforce safe search that blocks most adult content. These settings are easy to implement on an office network, but what about the average home user?

Disney Circle enforces safe search for managed devices, but not all devices. To protect all devices on your network, you'll need your own DNS server. Here's how to do it easily and cheeply using Amazon EC2 and DNSMasq.

1. Create an Amazon t2.micro instance using the Amazon Linux AMI. Assign it an elastic IP (EIP). Allow only SSH and DNS access to your EC2 instance.
2. Install dnsmasq: sudo yum install dnsmasq
3. Edit /etc/dnsmasq.conf as directed in this [excellent guide][1].
4. Point dnsmasq at OpenDNS or CloudFlare's 1.1.1.1 for Families.
5. Point your home route at the EIP of your EC2 instance. 

[1](https://spotlightcybersecurity.com/openwrt-dnsmasq-google-youtube-bing-filtering.html)
