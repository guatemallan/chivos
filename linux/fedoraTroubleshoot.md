# por qué fedora?

- Es un proyecto patrocinado por redhat.
- Gnome casi vanilla. Muy buena integración con Gnome.
- Incluye las novedades más actuales en cuanto a software y compatibilidad en hardware.
- Un sistema limpio, funcional desde la instalación, listo para empezar a experimentar y trabajar.

# por qué no debian?

- Debian es un proyecto de comunidad. 
- Gnome casi vanilla.
- La versión estable no prioriza las últimas versiones de software en favor de la estabilidad. Algunos paquetes de software pueden estar muy desactualizados en comparación con otras distribuciones. 
- En algunas ocasiones, hacer que algún hardware funcione se deben hacer ajustes intermedios y avanzados en el sistema (por ejemplo, haciendo que GPUS de NVidia funcionen).

# iniciar en resuce mode

1. Al iniciar el sistema, en la pantalla de GRUB/GRUB2 seleccionar con la flecha la opcion de boot en la que se desea iniciar
2. Presionar la tecla *e* para editar la entrada
3. Buscar la linea que empieza con *linux*/*linux16*/*linuxefi* y seleccionarla con las flechas arriba y abajo
4. Ir al final de la linea, agregar un espacion y anadir lo siguiente: `rw init=/bin/bash`
5. Presionar `ctrl+x` o `F10` para iniciar. 

# resetear el password de root

1. Hacer los pasos para [inicar en rescue mode](#iniciar-en-resuce-mode)
2. correr el commando `passwd`
3. reiniciar con el comando /sbin/reboot -f
4. seguir los pasos de 1 al 3 de [rescue mode](#iniciar-en-resuce-mode)
5. agregar al final del comando `autorelabel=1`

# GRUB mostrar comandos

1. hacer los pasos del 1 al 3 de [rescue mode](#iniciar-en-resuce-mode)
2. ir al final de la linea y hacer lo siguiente:
    1. quitar el comando `quiet`
    2. agregar `plymouth.enable=0`

# instalaciones dnf

## chequear existencia de repo

`dnf repolist | grep mozilla`

## firefox

`sudo dnf config-manager addrepo --id=mozilla --set=baseurl=https://packages.mozilla.org/rpm/firefox --set=gpgkey=https://packages.mozilla.org/rpm/firefox/signing-key.gpg --set=gpgcheck=1 --set=repo_gpgcheck=0 --set=priority=10 `

`sudo dnf makecache --refresh`

`sudo dnf install firefox`

## keepassxc

`sudo dnf install keepassxc`

## ffmpeg

`sudo dnf config-manager setopt fedora-cisco-openh264.enabled=1`

`sudo dnf config-manager --enable fedora-cisco-openh264`

`sudo dnf install https://mirrors.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm https://mirrors.rpmfusion.org/nonfree/fedora/rpmfusion-nonfree-release-$(rpm -E %fedora).noarch.rpm`



# thumbnails

## No hay thumbnails JPG, PNG

Instalar Glycin Thumbnailer

`sudo dnf install glycin-thumbnailer`
`sudo dnf reinstall gdk-pixbuf2`
`sudo dnf update`
`sudo rm ~/.cache/thumbnails/*`
`sudo rm ~/.cache/thumbnails/large/*`
`rm ~/.cache/thumbnails/fail/gnome-thumbnail-factory/*`

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

`git clone https://github.com/emuskardin/nautilus-raw-thumbnails.git`
`cd nautilus-raw-thumbnails`


2. Instalar exiv2ray y sus dependencias:

`sudo dnf install exiv2 ImageMagick perl-Image-ExifTool`


3. Configurar el thumbnailer:

`sudo cp exiv2raw.thumbnailer /usr/share/thumbnailers/`

4. Mover el script thumbnailer y hacer ejecutable:

`sudo cp exiv2-thumbnailer.sh /usr/local/bin/`
`sudo chmod +x /usr/local/bin/exiv2-thumbnailer.sh`

5. Opcional: limpiar cache de thumbnails:

`sudo rm ~/.cache/thumbnails/*`
`sudo rm ~/.cache/thumbnails/large/*`

## Filesystem Not Using All Available Space

### Possible Reasons for Disk Space Discrepancy

The issue may arise if the filesystem is not utilizing the entire space allocated to the partition. This can happen for several reasons, including:

    Filesystem Configuration: The filesystem might be configured to reserve a portion of the disk space for system use.
    Partition Size: The partition may not be correctly sized or formatted to use all available space.

Steps to Diagnose and Fix

    Check Partition Size: Use the command df -h to see how much space is being reported and how much is actually used.

    Resize Filesystem: If the partition is correctly sized but the filesystem is not using all the space, you may need to resize it. You can use the following commands:
        To check the filesystem: tune2fs -l /dev/sdX1 (replace /dev/sdX1 with your actual partition).
        To resize the filesystem: resize2fs /dev/sdX1.

    Check for Reserved Space: If the filesystem has reserved space, you can adjust it using:
        tune2fs -m 0 /dev/sdX1 to remove the reserved space.

Example of Checking Disk Space
Command	Description
df -h	Displays disk space usage for all mounted filesystems.
tune2fs -l /dev/sdX1	Lists filesystem information, including size and reserved space.
resize2fs /dev/sdX1	Resizes the filesystem to use all available space.

By following these steps, you should be able to identify and resolve the issue with your home partition's disk space detection.
Arch Linux forum.level1techs.com
