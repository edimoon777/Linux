# Install NEXT-531WBT dongle driver on ubuntu 18.04

# Clone repository
    mkdir -p ~/build
    cd ~/build
    git clone https://github.com/brektrou/rtl8821CU.git
    
# Build and install without DKMS
    cd ~/build/rtl8821CU
    make
    sudo make install

# Check installed driver
    ls /lib/modules/$(uname -r)/kernel/drivers/net/wireless/realtek/rtl8821cu


## Install usb-modeswitch manually.
    sudo apt-get install -y usb-modeswitch

## Install DKMS
    sudo apt-get install dkms
      
## Install driver
sudo ./dkms-install.sh

