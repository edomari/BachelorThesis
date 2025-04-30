# BachelorThesis
Material created during my bachelor's thesis creation, regarding the performance analysis and expressiveness of Intrusion Detection System rules generated in LUA language for industrial scenarios.

## How to use the project
1. Open `project` folder.
2. Enter `Infrastructure` folder and run `vagrant up`. Then start client and server with `vagrant ssh client` and  `vagrant ssh server`.
3. In `server` install Python and pyModbus.
4. In `client` install Python, Suricata and pyModbus.
   - Place `suricata.yaml` into `/etc/suricata/`
   - Place `modbus_detect.rules` into `/etc/suricata/rules/`
   - Place `prova1.lua` into `/etc/suricata/rules/`
   - Place `ceftest.lua` and `script1.lua` into `/etc/suricata/lua-outputs`
5. Put into `Infrastructure` folder:
   - `client_async.py`
   - `client_payloads.py`
   - `helper.py`
   - `server_async.py`
   - `server_payloads.py`
6. Run server with `python3 server_payloads.py -c tcp -p 502`
7. Run client with `python3 client_payloads.py -c tcp -p 502 --host 192.168.1.61`
8. Check the two new-created log files `ceftest.cef` and `luatest.log` for alerts.
