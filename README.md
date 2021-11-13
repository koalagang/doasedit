# doasedit
`doasedit` is the doas equivalent to [sudoedit](https://www.youtube.com/watch?v=Njsth_VeSxY).\
sudoedit is pretty nice but [sudo is insecure](https://www.youtube.com/watch?v=eamEZCj-CuQ) and [has had many vulnerabilities over the years](https://duckduckgo.com/?q=sudo+vulnerability), which is why, if you are on GNU/Linux, you should switch to [doas](https://github.com/nholstein/OpenDoas). Most BSD users probably already use doas.

## Installation

```sh
doas curl -sL "https://raw.githubusercontent.com/koalagang/doasedit/main/doasedit" -o /usr/bin/doasedit && doas chmod +x /usr/bin/doasedit
```
>To uninstall, just run `doas rm /usr/bin/doasedit`

## Things you might want to do

* It is not 100% necessary but it is recommended that you enable persistence in your doas.conf for more convenient use. To enable persistence, add the following line to `/etc/doas.conf`:
```sh
permit persist :wheel
```
* You should also make sure that `/etc/doas.conf` is owned by root but you have read permissions. If the file is writeable for anyone then you have a ***major*** security vulnerability on your system (anyone can give themselves root privilidges).

* If the source file is not readable then `doasedit` will not work. If you have not already done so then use this command (using `/etc/doas.conf` as the example path):
```sh
doas chown -c root:root '/path/of/file' && doas chmod 0444 '/path/of/file'
```
