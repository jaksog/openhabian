## October 28, 2020
## openHAB3 readiness (BETA)
openHABian now provides menu options 4X to upgrade your system to openHAB3 and to downgrade
back to current openHAB2 as well. See [documentation](docs/openhabian.md) for details.
Please be aware that openHAB3 as well as openHABian are not thoroughly tested so be prepared
to meet bugs and problems. Don't use this on your production system.


## October 6, 2020
## Tailscale VPN network (BETA)
Tailscale is a management toolset to establish a WireGuard based VPN between multiple systems
if you want to connect to openHAB(ian) instances outside your LAN over Internet.
It'll take care to detect and open ports when you and your peers are located behind firewalls.
This makes use of the tailscale service. Don't worry, for private use it's free of charge.


## October 1, 2020
## Offline installation (BETA)
We now allow for deploying openHABian to destination networks without Internet connectivity.
While the optional components still require access to download, the openHABian core is
fully contained in the download image and can be installed and run without Internet.
This will also provide a failsafe installation when any of the online sources for the tools
we need to download is unavailable for whatever reason.


## August 29, 2020
## Auto-backup
openHABian can automatically take daily syncs of your internal SD card to
another card in an external port. This allows for fast swapping of cards
to reduce impact of a failed SD card.
The remaining space on the external device can also be used to setup openHABian
's Amanda backup system.

## July 4, 2020
### Wireguard VPN (BETA)
Wireguard can be deployed to enable for VPN access to your openHABian box when
it's located in some remote location.
You need to install the Wireguard client from <http://www.wireguard.com/install>
to your local PC or mobile device that you want to use for access.
Copy the configuration file '/etc/wireguard/wg0-client.conf' from this box or
transmit QR code to load the tunnel.
Any feedback is highly appreciated on the forum.

### New Java providers now out of beta
Java 11 has been proven to work with openHAB 2.5.


## June 17, 2020
### Removed support for PINE A64(+) and older Linux distributions
`openhabian-config` will now issue a warning if you start on unsupported
hardware or OS releases. See [README](README.md) for supported HW and OS.

In short, PINE A64 is no longer supported and OS releases other than the current
`stable` and the previous one are deprecated. Running on any of those may still
work or not.

The current and previous Debian / Raspberry Pi OS (previously called Raspbian)
releases are 10 ("buster") and 9 ("stretch"). The most current Ubuntu LTS
releases are 20.04 ("focal") and 18.04 ("bionic").


## June 10, 2020
### New parameters in `openhabian.conf`
See `/etc/openhabian.conf` for a number of new parameters such as the useful
`debugmode`, a fake hardware mode, the option to disable ipv6 and the ability to
update from a custom repository other than the `master` and `stable` branches.

In case you are not aware, there is a Debug Guide in the `docs/` directory.

### New Java options
Preparing for openHAB 3, new options for the JDK that runs openHAB are now
available:

-   Java Zulu 8 32-Bit OpenJDK (default on ARM based platforms)
-   Java Zulu 8 64-Bit OpenJDK (default on x86 based platforms)
-   Java Zulu 11 32-Bit OpenJDK
-   Java Zulu 11 64-Bit OpenJDK
-   AdoptOpenJDK 11 OpenJDK (potential replacement for Zulu)

openHAB 3 will be Java 11 only.  2.5.X is supposed to work on both, Java 8 and
Java 11. Running the current openHAB 2.X on Java 11 however has not been tested
on a wide scale. Please be aware that there is a small number of known issues in
this: v1 bindings may or may not work.

Please participate in beta testing to help create a smooth transition user
experience for all of us.

See [announcement thread](https://community.openhab.org/t/Java-testdrive/99827)
on the community forum.


## May 31, 2020
### Stable branch
Introducing a new versioning scheme to openHABian. Please welcome the `stable`
branch.

Similar to openHAB where there's releases and snapshots, you will from now on be
using the stable branch. It's the equivalent of an openHAB release. We will keep
providing new changes to the master branch first as soon as we make them
available, just like we have been doing in the past. If you want to keep living
on the edge, want to make use of new features fast or volunteer to help a little
in advancing openHABian, you can choose to switch back to the master branch.
Anybody else will benefit from less frequent but well better tested updates to
happen to the stable branch in batches, whenever the poor daring people to use
`master` have reported their trust in these changes to work flawlessly.

You can switch branches at any time using the menu option 01.

### ZRAM per default
Swap, logs and persistence files are now put into ZRAM per default.
See [ZRAM status thread](https://community.openhab.org/t/zram-status/80996) for
more information.

### Supported hardware and Operating Systems
openHABian now fully supports all Raspberry Pi SBCs with our fast-start image.
As an add-on package, it is supposed to run on all Debian based OSs.

Check the [README](README.md) to see what "supported" actually means and what
you can do if you want to run on other HW or OS.
