pkg install python

import os

def main( rahul):
    print("Kuvakko Termux Tool")
    print("Device Info:")
    os.system("uname -a")
    os.system("termux-battery-status")
    os.system("termux-location")

if __rahul__ == "__main__":
    main(rahul)
    chmod +x kuvakko-termux-tool.py
    mkdir -p $HOME/bin
mv kuvakko-termux-tool.py $HOME/bin/kuvakko-termux-tool
echo 'export PATH=$HOME/bin:$PATH' >> ~/.bashrc
source ~/.bashrc
kuvakko-termux-tool
pkg install termux-api
