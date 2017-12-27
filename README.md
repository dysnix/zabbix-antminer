# zabbix-antiminer

An external script and template for getting Antiminer metrics into Zabbix

![Zabbix screen](screenshots/zabbix.png?raw=true "Zabbix screen")

# How it works

* Get Antiminer metrics from `/cgi-bin/get_miner_status.cgi` output by HTTP
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
* Download antiminer-zbx-chk and zbx_template.xml
* Put antiminer-zbx-chk into ExternalScript location (You will find it in zabbix_server configuration)
* Make antiminer-zbx-chk executable (`chmod +x check_dnsbl.sh`)
* Import zabbix_template (zbx_template.xml) into zabbix
* Add Antiminer as Zabbix Host. Input Antiminer HTTP Host or IP as Zabbix Agent Host
* Add Zabbix Macros `{$HOST.PORT}` with Antiminer HTTP port value
* Add Zabbix Macros `{$HTTP.USERNAME}` with Antiminer HTTP Username
* Add Zabbix Macros `{$HTTP.PASSWORD}` with Antiminer HTTP Password
* Link template to You servers
