# Clash
Recently, I have install the Clash on my Linux server, so I will record the process here. The process maybe not elegant, but useful for using Github.

## Download and Install

``` bash
wget https://github.com/Kuingsmile/clash-core/releases/download/1.18/clash-linux-amd64-v1.18.0.gz
gzip -d clash-linux-amd64-v1.18.0.gz
mkdir clash
mv clash-linux-amd64-v1.18.0 clash
```
## Prepare Configuration File

I have used the Clash on my Windows before, so I just copy the conf file from the Windows version, and put it in the ~/clash.

## Use the Clash
1. run the Clash. 
   Here the ~/clash/1702031025979.yml is the directory of my conf file.
   ``` bash
   ~/clash/clash-linux-amd64-v1.18.0 -f ~/clash/1702031025979.yml
   ```
2. Open a new terminal, and go to your working directory. Run the following code
   ```bash
   export http_proxy=http://127.0.0.1:7890
   export https_proxy=http://127.0.0.1:7890
   export ALL_PROXY=socks5://127.0.0.1:7890
   ```
3. Test the connection.
   ```bash
   curl google.com
   ```
   If there isn't any errors, then succeed! Some HTML code may appear in the terminal, which is natural. 
