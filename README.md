# Tandem

## Description

This repo hosts the Flathub Flatpak packaging for [Tandem](https://tandem.chat/),
available on [Flathub](https://flathub.org/apps/details/com.discordapp.Discord).

Note that this packaging is unofficial and thus unsupported by Tandem. If you
have issues, please verify that they occur when using an official packaging
method before reporting them to Tandem. If you only can reproduce the issue with
this Flathub Flatpak packaging, make an issue in this repository.

Tandem can be installed from Flathub like so, assuming you have Flathub set up:

    $ flatpak install flathub chat.tandem.Client
    $ flatpak run chat.tandem.Client

## Packaging notes

### Why is inetutils built with this?

Looking at the log Tandem spews out when running in Flatpak, it by default says
says this:

```
hostname: invalid option -- 'f'
Try 'hostname --help' for more information.
```

Using the `hostname` command (which is the only thing that gets built and
included) from inetutils solves this.

### Why the Snap and not the deb/rpm?

I couldn't figure out how to download a specific version of the deb/rpm, so I
went with the Snap since they have a nice API for this.
