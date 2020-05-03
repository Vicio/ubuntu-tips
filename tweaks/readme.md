# Tweaks

All ubuntu based OSes are by far the most simple of them all for a common user, however, simplicity in the front means complexity in the back. So when there is a specific need for a user, or needs more than just the plain install and a set of common apps, then it takes a turn for the worse.

Said that, here are a couple of helpful tweaks to increase system stability and performance, explained in a simple way.

## TLP

From the [creator's  website](linrunner.de/tlp/):

> _"TLP is a feature-rich command line utility for Linux, saving laptop battery power without the need to delve deeper into technical details._
> _TLP’s default settings are already optimized for battery life and implement Powertop’s recommendations out of the box. So you may just install and forget it._
> _Nevertheless TLP is highly customizable to fulfil your specific requirements."_

There is a complete table of contents about the installation and process to configure it on all systems, but since we are just using ubuntu based OSes, and TLP works well with almost no tweaking at all, we'll just check here the installation process.

So, the first thing to do is open a terminal, then just execute a series of commands:

```bash
apt search tlp
```

You should receive a response like this:

```bash
tlp/focal,focal,now 1.3.1-2 all
  Save battery power on laptops

tlp-rdw/focal,focal,now 1.3.1-2 all
  Radio device wizard
```

In case you don't see the response, it means your OS doesn't have it added to their repositories, so you just need to add it:

```bash
sudo add-apt-repository ppa:linrunner/tlp
sudo apt update
```

The last thing to do is install it, with a simple command:

```bash
sudo apt install tlp tlp-rdw --no-install-recommends
```

TLP requires some dependencies which are already included in most OSes, and updating them with their recommended ones could cause a system crash, hence it is recommended to use first the `--no-install-recommends` argument first. If TLP seems to fail to start, then try without the argument.

## Preload

[preload](sourceforge.net/projects/preload/) is an adaptive readahead daemon. It monitors applications that users run, and by analyzing this data, predicts what applications users might run, and fetches those binaries and their dependencies into memory for faster startup times.

This tool basically works like windows superfetch, and makes a comparable speedy startup of applications, this is specialle helpful if you open lots of them and want its libraries loaded during system startup so that they open quicly when you want to use them.

To install this tool is simple, as it is included in all ubuntu packages:

```bash
sudo apt install preload
```

And there you have it, no more configuration needed.

## Tracker

Most ubuntu based OSes, specially those based on gnome, rely on a background process called tracker.

Although helpful in some ocassions, for most users, including power users, since it scraps every nook and cranny of your system, it makes it slow, annoying the user. 

Creates an index for easy access the next time you want to search something in Gnome's menu or in file managers.

Being a little sincere, unindexed file search is not that slow, and normally a user knows where their stuff is located, so this background process becomes nothing more than a nuisance due to its high CPU, HDD and memory usage.

### Disabling

So, what should we do in case we don't want this app?

Very simple, again in terminal, just execute the following command:

```bash
systemctl --user mask tracker-store.service tracker-miner-fs.service tracker-miner-rss.service tracker-extract.service tracker-miner-apps.service tracker-writeback.service
```

After executing it, reset the tracker:

```bash
tracker reset --hard
```

Restart your computer, and it's done :3.
