# Recommended Apps

Most Ubuntu flavors come with a set of predefined applications for managing images, video, documents and the like, however, some flavor fall in favor of certain applications due to them being lightweight, or being a part of a set of applications developed by the Ubuntu based OS developers.

Some applications are well, but there are some which their popularity has made them stand out. So here are some of them.

## VLC

The first in our list is the famous player from [VideoLAN](https://www.videolan.org/).

VLC is known for its great support of almost any codec available on internet, and as new codecs arise, also the quick support for them in this incredible app.

This is why this application is so famous. That, and the fact it is very lightweight.

### Installation

To install this application in Ubuntu and based OSes, you just need to update the repositories and install it:

```bash
sudo apt update
sudo apt install vlc -y
```

And you will have the best video player ever made.

## Lollypop

And what about music? Well, that can pretty much be covered with this app, it's true that are some music player like Clementine, Amarok, or Rhytmbox, but some of them are resource hungry, have a pretty complicated user interface, or just behave abnormally if your library grows up in size.

Here's where lollypop makes its appearance, by presenting the user with a clean interface, easy configuration, and the best of all, a suggestions section which presents you the album of the day, and some songs from your library to listen to and have a fun time while doing your work, exercising or just passing time.

### Installation

By default Ubuntu does not include this application on its repositories, however some Ubuntu based OSes do, to verify this just run this command first.

```bash
apt search lollypop
```

If the resulting search is as follows:

```bash
lollypop/focal,focal 1.2.35-1 all
  modern music player
```

It means your application is available, if not, just add the lollypop repository:

```bash
sudo add-apt-repository ppa:gnumdk/lollypop
```

Then proceed to update the repositories and install:

```bash
sudo apt update
sudo apt install lollypop -y
```

## KDE Connect

Most people have smart TVs to watch their movies and series online, but what if you don't have one, or use your computer as source for playing movies on a simple LCD TV.

It is then that you can use this great app, which lets you sync your PC with your smartphone.

It allows you to take control of your PC using your smartphone as a mouse and keyboard, you can also receive push notifications in your PC, and even respond to messages sent via facebook messenger or whatsapp.

### Installation

Since it is optimized for KDE desktop environment, it does not come included in Ubuntu and some of ist flavors by default, as always, you can check it by searching it:

```bash
apt search kdeconnect
```

You should get this response:

```bash
kdeconnect/focal,now 1.4-0ubuntu5 amd64
  connect smartphones to your desktop devices.
```

Otherwise, youĺl need to add the repository:

```bash
sudo add-apt-repository ppa:webupd8team/indicator-kdeconnect
```

Now just update the repositories and install:

```bash
sudo apt update
sudo apt install kdeconnect indicator-kdeconnect -y
```

You also need to intall this application in your phone, and then pair it with your computer. It is important to mention that this is an only android app, so iPhone users will need to look for an alternative :/.