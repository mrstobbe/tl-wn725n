# tl-wn725n
The TP-LINK TL-WN725N WiFi Linux drivers ported to kernel 4.x

## Background

Long story short, TP-LINK doesn't appear to support their drivers. I happen
to have in my machine a TL-WN725N based WiFi dongle... specifically
(this one)[http://www.tp-link.com/lk/products/details/TL-WN725N.html] but
the drivers provided haven't been supported for a while and haven't been
ported to Linux 4.x.

I really don't know kmod dev details, and certainly don't know how Linux
deals with WiFi (or even USB for that matter), but I just hacked away at the
driver supplied at TP-LINK's website until it compiled without warning and
**appears** to work. Since then (it's been a bit), I haven't had any issue
that I didn't have with said drivers when I was on the 3.x branch of Linux.

## It's Yours Now

