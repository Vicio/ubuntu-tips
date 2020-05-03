# Tweaks

All ubuntu based OSes are by far the most simple of them all for a common user, however, simplicity in the front means complexity in the back. So when there is a specific need for a user, or needs more than just the plain install and a set of common apps, then it takes a turn for the worse.

Said that, here are a couple of helpful tweaks to increase system stability and performance.

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