# doasedit
`doasedit` is the doas equivalent to [sudoedit](https://www.youtube.com/watch?v=Njsth_VeSxY).\
sudoedit is pretty nice but [sudo is insecure](https://www.youtube.com/watch?v=eamEZCj-CuQ) and [has had many vulnerabilities over the years](https://www.qualys.com/2021/01/26/cve-2021-3156/baron-samedit-heap-based-overflow-sudo.txt). Which is why, if you are on GNU/Linux, you should use [doas](https://github.com/nholstein/OpenDoas).

There are two other `doasedit` implementations on GitHub but somehow they are both much longer than they need to be. This implementation is very small so I recommend you use this one.

## Installation

```sh
doas curl -sL "https://raw.githubusercontent.com/koalagang/doasedit/main/doasedit" -o /usr/bin/doasedit
```
