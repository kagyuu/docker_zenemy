# docker_zenemy

## What is this?
* This is a mining rig container for crypt currency.

## How to use it?

```
$ docker-compose up --build

zenemy_1  | [INFO   ] 21/12/09 16:06:48 zealot/enemy-2.6.2 miner (64 bit)
zenemy_1  | [INFO   ] 21/12/09 16:06:48 NVIDIA CUDA 10.0
zenemy_1  | [INFO   ] 21/12/09 16:06:48 Dev fee is 1.0%
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 MAIN POOL----------------------------------------------
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 URL : stratum+tcp://kawpow.usa-west.nicehash.com:3385
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 USER: 35wXssceVET45koSKXA93g6YKdfiMEzyDY
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 PASS: 
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 -------------------------------------------------------
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 FAILOVER POOLs-----------------------------------------
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 NONE
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 -------------------------------------------------------
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 Starting on stratum+tcp://kawpow.usa-west.nicehash.com:3385
zenemy_1  | [INFO   ] 21/12/09 16:06:48 GPU monitoring is not available.
zenemy_1  | [INFO   ] 21/12/09 16:06:48 HTTP API server started: http://127.0.0.1:4067
zenemy_1  | [INFO   ] 21/12/09 16:06:48 Mining 'kawpow' with 1 thread.
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 New job 0000000050d2029e
zenemy_1  | [WARNING] 21/12/09 16:06:48 New difficulty: 0.0911385, 391.44MH to the target
zenemy_1  | [NOTICE ] 21/12/09 16:06:48 Block 2052887 (epoch 273), difficulty 111203.505
zenemy_1  | [INFO   ] 21/12/09 16:06:49 Legacy API server started: telnet://127.0.0.1:4068
zenemy_1  | [INFO   ] 21/12/09 16:06:49 GPU#0: Intensity set to 21
zenemy_1  | [KAWPOW ] 21/12/09 16:06:51 GPU#0: Generating DAG in GPU memory (3416.38Mb)
zenemy_1  | [WARNING] 21/12/09 16:06:54 Stratum connection interrupted
zenemy_1  | [NOTICE ] 21/12/09 16:06:55 New job 0000000072ba9af2
```

* You can stop ccminer with Ctrl+C twice. Or ```$ docker-compose down``` .

# Attach your bitcoin wallet.

* Change docker-compose.yml
```
command: /root/z-enemy -a kawpow -o stratum+tcp://kawpow.usa-west.nicehash.com:3385 -u 35wXssceVET45koSKXA93g6YKdfiMEzyDY
```
* You don't have to sign in to nicehash. This is an address of NOMP (Node Open Mining Potal).
* Set your wallet ID to argument "-u". (The 35w...yDY is my wallet :-P)

# More 

* You can use MPOS insted of NOMP:
  * The nicehash is a mining pool. This URL is a NOMP (Node Open Mining Portal). You can use it without creating account.
  * You can also use MPOS(Mining Portal Open Source). MPOS has some usefull dashboards. You can reconginze how many Bit coins your gpu earned easily rather than NOMP.
* If you want to start mining with the power on, enable the flag "restart: always" on the docker-compose.yml. 
