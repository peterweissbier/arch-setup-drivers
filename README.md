## enable multilib (32-bit support)

uncomment `[multilib]` in `/etc/pacman.conf` and add

<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">/etc/pacman.conf
--------------------------------------------------------------------------------------
[multilib]
Include = /etc/pacman.d/mirrorlist</pre>

Then upgrade the system via `sudo pacman -Syyu`
