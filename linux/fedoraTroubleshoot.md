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