## Download Miner Binary
[Official Package](https://github.com/ethereum-mining/ethminer)

__Official is not support with latest version of cuda version. checkout personal package__

[Personal Package](https://github.com/no-fee-ethereum-mining/nsfminer)

## Setup miner script
```bash
touch mining.sh
```
__Add content below to mining.sh__

```sh
./nsfminer -U -P stratum1+ssl://<wallet_address>@asia1.ethermine.org:5555
```
__Allow script to executable__

```bash
chmod +x  mining.sh
```
## Setup Service Script
```bash
touch mining.service
```
__Add content below to mining.service__
```sh
[Unit]
After=network.service

[Service]
Type=simple
ExecStart=<path>/mining.sh
StandardOutput=append:<path>/logs/mining.log
StandardError=append:<path>/logs/mining.error.log
Restart=always
RestartSec=1

[Install]
WantedBy=default.target
```
__Available command__
```bash
sudo systemctl enable $PWD/mining.service
sudo systemctl disable mining.service
sudo systemctl status mining.service
sudo systemctl start mining.service
sudo systemctl stop mining.service
sudo systemctl restart mining.service
```
