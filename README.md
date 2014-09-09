centminmodbench.sh
===============

Custom system benchmark script for Centmin Mod LEMP web stack users. 

Development is ongoing so please test only on test servers and not production live servers.

*Current Test Suite*

* disk dd, ioping, fio & bandwidth benchmarks
* OpenSSL system benchmark + Nginx static OpenSSL benchmarks
* mysqlslap http://dev.mysql.com/doc/refman/5.6/en/mysqlslap.html
* PHP (php-fpm) Zend/bench.php & Zend/micro_bench.php
* UnixBench 5.1.3 (currently disabled by default)
* ServerBear.com tests (currently disabled by default)

To run type in SSH window as root user:

    curl -sL https://github.com/centminmod/centminmodbench/raw/master/centminmodbench.sh | bash

If you want to download to server and run in SSH window as root user:

    mkdir -p /root/tools
    cd /root/tools
    wget -O centminmodbench.sh https://github.com/centminmod/centminmodbench/raw/master/centminmodbench.sh
    chmod +x centminmodbench.sh

To run script locally in SSH window as root user type:

    /root/tools/centminmodbench.sh

Default log directories include:

* BENCHDIR='/home/centminmodbench' (source downloads location)
* LOGDIR='/home/centminmodbench_logs' (benchmark results logs)
* MYSQLSLAP_DIR='/home/mysqlslap' (mysqlslap results logs)
* PHPBENCHLOGDIR='/home/phpbench_logs' (PHP-FPM benchmark logs)

Variables you can alter within centminmodbench.sh. Note the bandwidth tests can be set regionally as well, so if you have no need for Asia tests, you can turn the Asian specific bandwidth tests off etc. UnixBench is turned off by default during testing of this script as it adds up to 30 minutes to test runs as seen at https://community.centminmod.com/threads/centminmodbench-sh-benchmark-script-for-centmin-mod-lemp-servers.1298/#post-5880.

    SEVERBEAR='n'
    OPENSSLBENCH='y'
    OPENSSL_NONSYSTEM='y'
    OPENSSL_VERSION='1.0.1i'
    
    MYSQLSLAP_SAVECSV='n'
    
    RUN_DISKDD='y'
    RUN_DISKIOPING='y'
    RUN_DISKFIO='y'
    RUN_BANDWIDTHBENCH='y'
    EUROPE_BANDWIDTHTESTS='y'
    ASIA_BANDWIDTHTESTS='y'
    AUSTRALIA_BANDWIDTHTESTS='y'
    USA_BANDWIDTHTESTS='y'
    RUN_PINGTESTS='y'
    RUN_UNIXBENCH='n'
    UNIXBENCH_VER='5.1.3'
