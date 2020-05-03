# Gaming

For the gaming tips, only one is present for now, and it is, enabling a specific wine version to allow pinging.

If you've reached here, it means that you have found that some multiplayer network games running under wine might be kicking you from their servers.

Games like all EA based games, and some FPS games.

This is due to a security implementation in linux systemd which forbids applications to have direct access to some system functionalities.

One of them is the handle of incoming network raw information.

Systemd immediately rejects wine applications to connect with this method as it is considered a network vulnerability.

So, how do we pass this issue?

I'd like to say it's easy, but it took me almost a week to figure out by searching everywhere and figuring out the whole issue, until I found a solution provided by [this guy](https://www.reddit.com/r/linux_gaming/comments/gc5qss/wine_and_ping_support_on_ubuntu_a_guide/).

So, how do we start?

First we need to use the set_cap command to provide specific root capabilities to wine:

```bash
setcap cap_net_raw+epi path/to/wine-preloader
setcap cap_net_raw+epi path/to/wine64-preloader
setcap cap_net_raw+epi path/to/wineserver
```

You need to replace the "path/to/" part with the path of your wine executable.

If you use the standard wine installation, then you can find your path with this command:

```bash
which wine
```

This will make your current wine executable unused, since it will not find any libraries as it looks for them not via environment variables but, in a special system configuration, to fix this we need to do the following:

```bash
sudo cp /path/to/lib/libwine.so.1 $HOME/.local/lib/libwine.so.1
sudo cp /path/to/lib/libwine.so.0 $HOME/.local/lib/libwine.so.1.0
sudo cp /path/to/lib64/libwine.so.1 $HOME/.local/lib64/libwine.so.1
sudo cp /path/to/lib64/libwine.so.1 $HOME/.local/lib64/libwine.so.1.0
```

Take into account that if you're using lutris, then your path might be different, lutris app stores its wine executables in:

```bash
$HOME/.local/share/lutris/runners/wine
```

Finally, we need to add these paths into the special location where wine now searches instead of the environment variables:

```bash
echo "/home/place-your-username-here/.local/lib" | sudo tee /etc/ld.so.conf.d/wine32.conf
echo "/home/place-your-username-here/.local/lib64" | sudo tee /etc/ld.so.conf.d/wine64.conf
sudo ldconfig
```
