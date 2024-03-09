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

I have used the Clash on my Windows before, so I just **copy** the conf file from the Windows version, and put it in the ~/clash.

## Use the Clash
1. Run the Clash. 
   Here the `~/clash/1702031025979.yml` is the directory of my conf file. It is recommended to create a Tmux session to run the code.
   ``` bash
   ~/clash/clash-linux-amd64-v1.18.0 -d . -f ~/clash/1702031025979.yml
   ```
2. Open a new terminal (or detaching from tmux's session), and go to your working directory. Run the following code. This only takes effect in the terminal. And if you want to use Clash in another terminal, you should run the following in that terminal again.
   ```bash
   export http_proxy=http://127.0.0.1:7890
   export https_proxy=http://127.0.0.1:7890
   export ALL_PROXY=socks5://127.0.0.1:7890
   ```
3. Test the connection.
   ```bash
   curl google.com
   ```
   If there appear some HTML codes in the terminal immediately (see the Output below), the Clash works. Otherwise, there may be some errors. You can check the log in the former terminal.
   ![curl_google{#curl}](/static/curl_google.png)

