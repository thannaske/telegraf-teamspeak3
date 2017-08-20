# Telegraf Execution Script for Teamspeak 3
Telegraf-executable script to collect metrics of all virtual server instances of a Teamspeak 3 server

# Usage instruction
Clone, build and store somewhere on your server. Add the executable to the `exec` input plugin of Influx Telegraf. Don't set the execution timeout too low when you have multiple server instances running.

# Output
The script outputs collected metrics about all found Teamspeak 3 instances in Influx Line format.

# Usage example: Visualize Metrics with Grafana
![Grfana Example](https://i.gyazo.com/f6f5e28fbb8ea56c8cacedacc64bd6b8.png)
