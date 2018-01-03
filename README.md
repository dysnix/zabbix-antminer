# zabbix-antminer

An external script and template for getting AntMiner metrics into Zabbix

![Zabbix screen](screenshots/zabbix.png?raw=true "Zabbix screen")

# How it works

* Get AntMiner metrics from `/cgi-bin/get_miner_status.cgi` output by HTTP
* Parse data from JSON output
* Store data into Zabbix

# Supported metrics
* Fan 3, 6
* GH/S (RT)
* Temp chip2 for chain 6-7

# Supported triggers
* Temp any chip chain > 80

# Requirements
* Python 2 or 3
* Python [Requests](https://pypi.python.org/pypi/requests)
* Zabbix 3.0

# Install
* Download antminer-zbx-chk and zbx_template.xml
* Put antminer-zbx-chk into ExternalScript location (You will find it in zabbix_server configuration)
* Make antminer-zbx-chk executable (`chmod +x check_dnsbl.sh`)
* Import zabbix_template (zbx_template.xml) into zabbix
* Add AntMiner as Zabbix Host. Input AntMiner HTTP Host or IP as Zabbix Agent Host
* Add Zabbix Macros `{$HOST.PORT}` with AntMiner HTTP port value
* Add Zabbix Macros `{$HTTP.USERNAME}` with AntMiner HTTP Username
* Add Zabbix Macros `{$HTTP.PASSWORD}` with AntMiner HTTP Password
* Link template to You servers
