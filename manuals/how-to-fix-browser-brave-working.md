# How to fix browser Brave working?

Start from the middle of the spring of 2023 year browser Brave works little incorrect on Linux.
One of the problem is that Brave reset itself configuration.

Here's an example:

> I’m using Brave Browser in my Linux Mint OS and I haven’t had this problem before. I use dark mode in both my OS as well as the browser. When I used to reboot the system, it didn’t change. But I noticed that Brave got updated recently and it created this issue for me. Every time I reboot my computer and I open Brave, it is set in light mode. However, when I check settings the dark mode is still selected, so I have to select light mode, and then dark mode again in order to change to dark mode. As I said, I noticed this issue in recent days, after Brave Browser update, since I didn’t have this problem before.

Source: https://community.brave.com/t/brave-browser-dark-mode-changing-after-reboot/490297

Also the problem in Browser render working (I don't know why...)

So, unless Brave developers will fix the problem you should to stay on use the stable version of browser.

Open the terminal and downgrade your Brave browser (actual on Spring-Summer of 2023)

```bash
sudo apt update && sudo apt install brave-browser=1.51.118 --yes
```

And hold this version for the Update Manager

```bash
sudo apt-mark hold brave-browser=1.51.118
```

---

When Brave will release the new stable version you'll unhold the current one

```bash
sudo apt-mark unhold brave-browser=1.51.118
```

Evrything can be solved!
