# doasedit
`doasedit` is the doas equivalent to [sudoedit](https://www.youtube.com/watch?v=Njsth_VeSxY).\
sudoedit is pretty nice but [sudo is insecure](https://www.youtube.com/watch?v=eamEZCj-CuQ) and [has had many vulnerabilities over the years](https://duckduckgo.com/?q=sudo+vulnerability), which is why, if you are on GNU/Linux, you should switch to [doas](https://github.com/nholstein/OpenDoas). Most BSD users probably already use doas.

## Installation
Dependencies: doas, GNU coreutils, GNU diffutils and an editor of your choice (make sure to set the `$EDITOR`
environmental variable in your shell).

```sh
doas curl -sL "https://raw.githubusercontent.com/koalagang/doasedit/main/doasedit" -o /usr/bin/doasedit && doas chmod +x /usr/bin/doasedit
```
>To uninstall, just run `doas rm /usr/bin/doasedit`

## Things you might want to do

* It is not 100% necessary but it is recommended that you enable persistence in your doas.conf for more convenient use. To enable persistence, (provided that you are part of the `wheel` group) add the following line to `/etc/doas.conf`:
```sh
permit persist :wheel
```
* You should also make sure that `/etc/doas.conf` is owned by root but you have read permissions. If the file is writeable for anyone then you have a ***major*** security vulnerability on your system (anyone can give themselves root privilidges).\
You can do this by issuing the following command:
```sh
doas chown -c root:root '/etc/doas.conf' && doas chmod 0444 '/etc/doas.conf'
```

* If the source file is not readable then `doasedit` will not work. You can mark a file as readable with the following command:
```sh
doas chmod +r '/path/of/file'
```
>`doas` is only required if the file is owned by root.

* Some software hardcode the use of sudo if they need root privilidges. This issue can be overcome by uninstalling sudo and then symlinking doas to sudo with the following command:
> Make sure to remove the `sudo` package first.
```
doas ln -s /usr/bin/doas /usr/bin/sudo
```
