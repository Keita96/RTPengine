## prerepquis on debian

    apt-get remove rtpproxy
    sudo apt install debhelper iptables-dev libcurl4-openssl-dev libglib2.0-dev libxmlrpc-core-c3-dev libhiredis-dev markdown build-essential:native
  
  
  
  ## é ime lot de prerequis
  
  
    apt-get install debhelper default-libmysqlclient-dev gperf iptables-dev libavcodec-dev libavfilter-dev libavformat-dev libavutil-dev libbencode-perl libcrypt-openssl-rsa-perl libcrypt-rijndael-perl libhiredis-dev libio-multiplex-perl libio-socket-inet6-perl libjson-glib-dev libdigest-crc-perl libdigest-hmac-perl libnet-interface-perl libnet-interface-perl libssl-dev libsystemd-dev libxmlrpc-core-c3-dev libcurl4-openssl-dev libevent-dev libpcap0.8-dev markdown unzip nfs-common dkms libspandsp-dev
    
## suite

        VER=1.0.4

        curl https://codeload.github.com/BelledonneCommunications/bcg729/tar.gz/$VER >bcg729_$VER.orig.tar.gz

        tar zxf bcg729_$VER.orig.tar.gz 

        cd bcg729-$VER 

        git clone https://github.com/ossobv/bcg729-deb.git debian 

        dpkg-buildpackage -us -uc -sa

        cd ../

        dpkg -i libbcg729-*.deb
