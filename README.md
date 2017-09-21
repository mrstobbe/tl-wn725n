# tl-wn725n
The TP-LINK TL-WN725N WiFi Linux drivers ported to kernel 4.x

## Background

Long story short, TP-LINK doesn't appear to support their drivers. I happen
to have in my machine a TL-WN725N based WiFi dongle... specifically
[this one](http://www.tp-link.com/lk/products/details/TL-WN725N.html) but
the drivers provided haven't been supported for a while and haven't been
ported to Linux 4.x.

I tried a couple other chip-based stuff after googling the issue and they
came back with a few user-land kernel drivers on github (which, I will link
if I remember to), but they proved disasterous as they just kept dumping the
device randomly and doing weird stuff.

I really don't know kmod dev details, and certainly don't know how Linux
deals with WiFi (or even USB for that matter), but I just hacked away at the
driver supplied at TP-LINK's website until it compiled without warning and
**appears** to work. Since then (it's been a bit), I haven't had any issue
that I didn't have with said drivers when I was on the 3.x branch of Linux.


## For Users

Make sure you have the appropriate develment headers installed for your
distro. For example, Fedora you want the package `kernel-devel`.

Obviously you also need a complete C build toolkit. Out of the box that
would be things like gcc and make.

Run...
```
$ make
```

In the source directory. There should be no warnings or errors. If there
are, deal with them appropriately.

As root, run...
```
# make install
```

You should see `depmod` stuff finishing. At that point you can simply remove
the device and re-insert it and you should be good-to-go without reboot.
To uninstall, `# make uninstall`.

Everytime you upgrade your kernel you will have to repeat these steps, so I
recommond keeping a copy someplace like `/usr/local/src/`


## For Developers (and others with a curious mind)

I just threw kernel version CPP checks around everything. I started by using
my own kernel version at the time (4.11.x I believe). If you get a compiler
error on a 4.x version < 4.11.x, simply try grepping and replacing that with
your own version.  If it works, please do a pull request back.

Also, I screwed up on keeping the original source directory clean when I was
working on porting it. It's been built and since it's not a "out-of-source"
build, there's undoubtedly stupid built stuff in the source. If you find them,
please remove them and do a pull request.

Lastly, there's a ton of debug `dmesg` spam. I haven't looked into what compiler
directive turns that off but it should obviously be off by default. Again, if
you figure that out, please do a pull request.


## License

No idea. It's not my source code and TP-LINK definitely didn't bother to make
that clear. There's nothing in the original archive or easy-to-find on their
website. I presume they own the rights and if they told me to take down this
repository, I would in an instant.

