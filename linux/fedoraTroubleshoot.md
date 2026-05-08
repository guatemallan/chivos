# instalaciones dnf

## chequear existencia de repo

        dnf repolist | grep mozilla

## firefox

        sudo dnf config-manager addrepo --id=mozilla --set=baseurl=https://packages.mozilla.org/rpm/firefox --set=gpgkey=https://packages.mozilla.org/rpm/firefox/signing-key.gpg --set=gpgcheck=1 --set=repo_gpgcheck=0 --set=priority=10

        sudo dnf makecache --refresh

        sudo dnf install firefox

## keepassxc

        sudo dnf install keepassxc

## ffmpeg

        sudo dnf config-manager setopt fedora-cisco-openh264.enabled=1

        sudo dnf config-manager --enable fedora-cisco-openh264

        sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm



# thumbnails

## No hay thumbnails JPG, PNG

Instalar Glycin Thumbnailer

    sudo dnf install glycin-thumbnailer

    sudo dnf reinstall gdk-pixbuf2

    sudo dnf update

    sudo rm ~/.cache/thumbnails/*
    sudo rm ~/.cache/thumbnails/large/*

    rm ~/.cache/thumbnails/fail/gnome-thumbnail-factory/*

## No hay thumbnails de RAWS (RAF, CR2, ...)

Usar exiv2raw. Archivos soportados: 

- .ORF
- .ARW
- .NEF
- .RAF
- .CR2
- .CR3
- .DNG
- .RW2

1. Clonar repo:

        git clone https://github.com/emuskardin/nautilus-raw-thumbnails.git
        cd nautilus-raw-thumbnails


2. Instalar exiv2ray y sus dependencias:

        sudo dnf install exiv2 ImageMagick perl-Image-ExifTool


3. Configurar el thumbnailer:

        sudo cp exiv2raw.thumbnailer /usr/share/thumbnailers/

4. Mover el script thumbnailer y hacer ejecutable:

        sudo cp exiv2-thumbnailer.sh /usr/local/bin/
        sudo chmod +x /usr/local/bin/exiv2-thumbnailer.sh

5. Opcional: limpiar cache de thumbnails:

        sudo rm ~/.cache/thumbnails/*
        sudo rm ~/.cache/thumbnails/large/*