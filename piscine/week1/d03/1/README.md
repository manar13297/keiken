# How ARP Works?
ARP stands for Address Resolution Protocol. It's a fundamental protocol used in IP networking to map an IP address to a physical machine address that is recognized in the local network.

When a device wants to communicate with another on the same local network, it uses ARP to find out the MAC address associated with the intended IP address. The device sends an ARP broadcast query packet to all devices on the network, asking "Who has this IP address?". The device with the matching IP address responds with its MAC address, enabling direct communication at the data link layer.

# ARP POISONING?

ARP poisoning involves sending unsolicited ARP replies to falsely associate the attacker's MAC address with the IP addresses of other devices in the network. This positions the attacker as a man-in-the-middle, intercepting communications.

# Let's getting hands dirty!
> **NOTE:**.
>The activities described here, including the use of Kali Linux for ARP poisoning and traffic analysis with Wireshark, were conducted solely for educational purposes as part of this internship program.
> 
> Such exercises are meant to enhance understanding of network security vulnerabilities in a controlled and ethical environment. Engaging in these practices outside of such a context can be illegal and unethical

## Environement
- Kali linux imported in Oracle Virtual box [Kali linux VM](https://www.kali.org/get-kali/#kali-virtual-machines)
- Your local machine or another VM (in this case, my windows local machine)
- Connected to internet
## Scenario of what we gonna do
#### Parts of this scenario
- Kali linux 192.168.43.232  :7e:f5
- Windows    192.168.43.129  :F9:20
- Gateway    192.168.43.1    :8c:7f

![text](screenshots/1.png)
![text](screenshots/2.png)
![text](screenshots/3.png)
![text](screenshots/4.png)
![text](screenshots/5.png)
![text](screenshots/6.png)
![text](screenshots/7.png)
![text](screenshots/8.png)
![text](screenshots/9.png)
![text](screenshots/10.png)

## Practice
- In your kali linux, execute the command: 
```bash 
sudo sysctl net.ipv4.ip_forward=1
```
> **NOTE:**.
>This step is crucial for the ARP poisoning attack to be successful.
>
> This command make IP forwarding enabled on Kali Linux to allow it to act as a router, forwarding packets between the Windows machine and the gateway. This step ensures that while Kali intercepts the traffic, it also maintains network connectivity by relaying packets, preventing the network from detecting the attack due to dropped connections.

....To be continued


