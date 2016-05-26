OpenEmbedded/Yocto BSP layer for the UDOO i.mx6 based boards
===========================================================

This layer provides support for UDOO i.mx6 family based platforms for
use with OpenEmbedded and/or Yocto Freescale's BSP layers.

This layer depends on:

URI: git://git.openembedded.org/openembedded-core
branch: master
revision: HEAD

URI: git://git.yoctoproject.org/meta-fsl-arm
branch: master
revision: HEAD

Images
======

- udoo-image-full-cmdline
  A command line image with SSH server support and most of the packages in this layer
- udoo-image-qt5
  Providing a qt5 enabled image with a lot of Qt5 goodies. This image requires the meta-qt5 layer

Optional build configuration
============================

Enable SPI bus on the UDOO Neo
==============================
By default the ECSPI_2 bus is disabled in the device tree to enable the SPI bus a device tree modification is needed.
To activate this patch set this variable to enable SPI bus
```
ENABLE_SPI_BUS = "1"
```

Enable CAN bus on the UDOO Neo
===============================
By default both  CAN bus interfaces are disabled in the device tree to enable the CAN bus a device tree modification is needed. To activate this patch set this variable to enable CAN bus
```
ENABLE_CAN_BUS = "1"
```

Select the video outputmode on the UDOO Neo
===========================================
By default the UDOO Neo activates HDMI output. To enable the ``lvds7`` or ``lvds15`` this variable has to be set
```
VIDEO_OUTPUT = "lvds7"
```

Valid options are:
- hdmi
   The default value which activates HDMI only output
- lvds7
   Support for the official LVDS7 display Kit
- lvds15
   Support for the official LVDS15 display Kit


Contributing
============

To contribute to this layer you should the patches for review to the
mailing list.


Source code:

    https://github.com/graugans/meta-udoo

When creating a patch of the last commit, use

    git format-patch -s --subject-prefix='meta-udoo][PATCH' -1

To send it to the community, use

    git send-email --to ch@ege.io <generated patch>

Patches are normally intended for the master branch.

Patches for other branches should be sent separately so they can be tracked
individually in Patchwork and should have the branch name in brackets.

For example, use this to generate a patch for branch 'dizzy':

    git format-patch -s \
	--subject-prefix='meta-udoo][dizzy][PATCH' -1
