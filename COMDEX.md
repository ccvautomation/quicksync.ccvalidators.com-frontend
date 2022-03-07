# COMDEX
 
| DOWNLOAD  | date | chain id | db backend | pruning | size | file name | hash |
| --------- | ---- | -------- | ---------- | ------- | ---- | --------- | ---- |
| [DOWNLOAD](https://quicksync.ccvalidators.com/SNAPSHOTS/comdex-1_pruned.tar.lz4) | 2022/03/07 | comdex-1 | goleveldb | pruned | 51G | comdex-1_20220307_pruned.tar.lz4 | 8c182b953ccf555d311b563fe5b2ed35 |
 
---
## download instructions
 
```sh
sudo apt install aria2 lz4
$URL=<paste URL>
cd $HOME/.comdex
rm -r data
aria2c -x5 $URL
md5sum `basename $URL`
lz4 -d `basename $URL` | tar xf -
comdex start
```
*or (single-stream, no double disk-space needed, but no possibility to check hash)*
```sh
$URL=<paste URL>
cd $HOME/.comdex
rm -r data
wget -O - $URL | lz4 -d | tar -xvf -
mv data-backup-2022-3-7 data
comdex start
```
