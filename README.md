# Telegraf Execution Script for Teamspeak 3
Telegraf-executable script to collect metrics of all virtual server instances of a Teamspeak 3 server

# Usage instruction
Clone, build and store somewhere on your server. Add the executable to the `exec` input plugin of Influx Telegraf. Don't set the execution timeout too low when you have multiple server instances running.

# Output
The script outputs collected metrics about all found Teamspeak 3 instances in Influx Line format.

- Metric Name: `teamspeak_server`
- Tags: `port` and `id` of the virtual server instance
- Value `online`: Whether the server instance is running or not
- Value `v_clients`: Currently online voice client count (Server Query clients not included)
- Value `q_clients`: Currently online Server Query client count
- Value `m_clients`: Maximum clients allowed for the virtual server instance
- Value `autostart`: Whether the virtual server instance will auto-start or not
- Value `bytes_out`: Overall egress traffic in bytes since restart
- Value `bytes_in`: Overall ingress traffic in bytes since restart
- Value `channels`: Channel count of the virtual server instance
- Value `reserved_slots`: Reserved slot count of the virtual server instance
- Value `uptime`: Uptime in seconds since restart
- Value `packets_out`: Overall egress packets since restart
- Value `packets_in`: Overall ingress packets since restart
- Value `ft_bytes_in_total`: Overall file transfer ingress bytes (not since restart but since ever)
- Value `ft_bytes_out_total`: Overall file transfer egress bytes (not since restart but since ever)
- Value `pl_control`: Average packetloss of the control packets
- Value `pl_speech`: Average packetloss of the speech packets
- Value `pl_keepalive`: Average packetloss of the keepalive packets
- Value `pl_total`: Average packetloss of control, speech and keepalive packets together
- Value `bytes_in_speech`: Overall ingress speech traffic since restart in bytes
- Value `bytes_out_speech`: Overall egress speech traffic since restart in bytes
- Value `bytes_in_control`: Overall ingress control traffic since restart in bytes
- Value `bytes_out_control`: Overall egress control traffic since restart in bytes
- Value `bytes_in_keepalive`: Overall ingress keepalive traffic since restart in bytes
- Value `bytes_out_keepalive`: Overall egress keepalive traffic since restart in bytes
- Value `packets_in_speech`: Overall ingress speech packets since restart
- Value `packets_out_speech`: Overall egress speech packets since restart
- Value `packets_in_control`: Overall ingress control packets since restart
- Value `packets_out_control`: Overall egress control packets since restart
- Value `packets_in_keepalive`: Overall ingress keepalive packets since restart
- Value `packets_out_keepalive`: Overall egress keepalive traffic since restart
- Value `avg_ping`: Average ping of all connected voice clients

# Usage example: Visualize Metrics with Grafana
![Grfana Example](https://i.gyazo.com/f6f5e28fbb8ea56c8cacedacc64bd6b8.png)

# Acknowledgments
go-ts3: https://github.com/multiplay/go-ts3  
This library provides all necessary methods to connect to a Teamspeak 3 ServerQuery. During my work on this repository I added a few methods for bandwidth and packetloss metering at it.
