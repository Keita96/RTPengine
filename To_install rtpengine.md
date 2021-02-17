# On unbutu 18.04.
sources : https://nickvsnetworking.com/rtpengine-installation-configuration/

#to download on git

        git clone https://github.com/sipwise/rtpengine.git 
        cd rtpengine

## to install dependancies 

      apt-get install debhelper default-libmysqlclient-dev gperf iptables-dev libavcodec-dev libavfilter-dev libavformat-dev libavutil-dev libbencode-perl libcrypt-openssl-rsa-perl libcrypt-rijndael-perl libhiredis-dev libio-multiplex -socket-inet6-perl libjson-glib-dev libdigest-crc-perl libdigest-hmac-perl libnet-interface-perl libnet-interface-perl libssl-dev libsystemd-dev libxmlrpc-core-c3-dev libcurl4-openssl-dev libevent -dev libpcap0.8-dev markdown décompresser nfs-common dkms libspandsp-dev


## La dépendance sur laquelle vous serez bloqué sera la bibliothèque G.729, que nous devons compiler manuellement.

             ER=1.0.4

            curl https://codeload.github.com/BelledonneCommunications/bcg729/tar.gz/$VER >bcg729_$VER.orig.tar.gz

            tar zxf bcg729_$VER.orig.tar.gz 

            cd bcg729-$VER 

            git clone https://github.com/ossobv/bcg729-deb.git debian 

            dpkg-buildpackage -us -uc -sa

            cd ../

            dpkg -i libbcg729-*.deb
            
  ## To check
  
    dpkg-checkbuilddeps
    dpkg-buildpackage 
    
    ## Si cela s'est terminé avec succès dans le répertoire ci-dessus, vous devriez avoir un tas de fichiers .deb:
    
        cd ../ 

        dpkg -i ngcp-rtpengine-daemon _ *. deb ngcp-rtpengine-iptables _ *. deb ngcp-rtpengine-kernel-dkms _ *. deb
        
        
   ## Faire fonctionner rtpengine
      
          mv /etc/rtpengine/rtpengine.sample.conf /etc/rtpengine/rtpengine.conf 

          vi /et vi /etc/rtpengine/rtpengine.conf   
   
   
   Nous allons décommenter la ligne d'interface et définir l'IP sur l'IP sur laquelle nous écouterons:
   
                  ###a single interface:
                  interface = 192.168.50.125
                  ###separate multiple interfaces with semicolons:
                  # interface = internal/12.23.34.45;external/23.34.45.54
                  ### for different advertised address:
                  # interface = 12.23.34.45!23.34.45.56

   

