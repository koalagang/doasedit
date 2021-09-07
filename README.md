# doasedit
`doasedit` is the doas equivalent to [sudoedit](https://www.youtube.com/watch?v=Njsth_VeSxY).\
sudoedit is pretty nice but [sudo is insecure](https://www.youtube.com/watch?v=eamEZCj-CuQ) and [has had many vulnerabilities over the years](https://www.qualys.com/2021/01/26/cve-2021-3156/baron-samedit-heap-based-overflow-sudo.txt). Which is why, if you are on GNU/Linux, you should use [doas](https://github.com/nholstein/OpenDoas).

## Installation

Perhaps your last time using sudo 😏
```sh
sudo curl -sL "https://raw.githubusercontent.com/koalagang/doasedit/main/doasedit" -o /usr/bin/doasedit
```
