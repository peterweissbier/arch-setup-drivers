## enable multilib (32-bit support)

uncomment `[multilib]` in `/etc/pacman.conf` and add

<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">/etc/pacman.conf
--------------------------------------------------------------------------------------
[multilib]
Include = /etc/pacman.d/mirrorlist</pre>

Then upgrade the system via `sudo pacman -Syyu`

## AMD drivers

<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">sudo pacman -S --needed lib32-mesa vulkan-radeon lib32-vulkan-radeon vulkan-icd-loader lib32-vulkan-icd-loader</pre>

## Wine dependencies

<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">sudo pacman -S --needed wine-staging giflib lib32-giflib libpng lib32-libpng libldap lib32-libldap gnutls lib32-gnutls \
mpg123 lib32-mpg123 openal lib32-openal v4l-utils lib32-v4l-utils libpulse lib32-libpulse libgpg-error \
lib32-libgpg-error alsa-plugins lib32-alsa-plugins alsa-lib lib32-alsa-lib libjpeg-turbo lib32-libjpeg-turbo \
sqlite lib32-sqlite libxcomposite lib32-libxcomposite libxinerama lib32-libgcrypt libgcrypt lib32-libxinerama \
ncurses lib32-ncurses ocl-icd lib32-ocl-icd libxslt lib32-libxslt libva lib32-libva gtk3 \
lib32-gtk3 gst-plugins-base-libs lib32-gst-plugins-base-libs vulkan-icd-loader lib32-vulkan-icd-loader</pre>

## jc141 dependencies

add rumpowered repository

<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">echo '
[rumpowered]
Server = https://jc141x.github.io/rumpowered-packages/$arch ' | sudo tee -a /etc/pacman.conf</pre>

sign keys for rumpowered
<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">sudo pacman-key --recv-keys cc7a2968b28a04b3
sudo pacman-key --lsign-key cc7a2968b28a04b3</pre>

refresh all packages
<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;">sudo pacman -Syyu</pre>

install the required packages

<pre style="margin-bottom: 0; border-bottom:none; padding-bottom:0.8em;"sudo pacman -S --needed dwarfs fuse-overlayfs bubblewrap wine-staging
sudo pacman -S --needed {lib32-,}{alsa-lib,alsa-plugins,libpulse,pipewire,openal,libxcrypt-compat,gst-plugins-{good,base,base-libs},sdl2_ttf,sdl2_image} libgphoto2</pre>


