# balena-pihole

If you're looking for a way to quickly and easily get up and running with a Pi-hole device for your home network, this is the project for you.

This project is a [balenaCloud](https://www.balena.io/cloud) stack with the following services:

* [Pi-hole](https://hub.docker.com/r/pihole/pihole/)
* [Unbound](https://hub.docker.com/r/klutchell/unbound/)

balenaCloud is a free service to remotely manage and update your Raspberry Pi through an online dashboard interface, as well as providing remote access to the Pi-hole web interface without any additional configuation.

## Getting Started

To get started you'll first need to sign up for a free balenaCloud account and flash your device.

<https://www.balena.io/docs/learn/getting-started>

## Deployment

Once your account is set up, deployment is carried out by downloading the project and pushing it to your device either via Git or the balena CLI.

### Application Environment Variables

Application envionment variables apply to all services within the application, and can be applied fleet-wide to apply to multiple devices.

|Name|Example|Purpose|
|---|---|---|
|`TZ`|`America/Toronto`|To inform services of the timezone in your location, in order to set times and dates within the applications correctly. Find a [list of all timezone values here](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).|
|`DNSMASQ_LISTENING`|`eth0`|We set this to `eth0` to indicate we want DNSMASQ to listen on the ethernet interface of the Raspberry Pi. If you're connecting to your network with WiFi replace this with `wlan0`|
|`INTERFACE`|`eth0`|As above.|
|`ServerIP`|`192.168.86.22`|set to your server's LAN IP, used by web block modes and lighttpd bind address.|
|`WEBPASSWORD`|`mysecretpassword`|(optional) password for accessing the web-based interface of Pi-hole - you won’t be able to access the admin panel without defining a password here.|
|`DNS1`|`127.0.0.1#5053`|(optional) primary upstream DNS provider, default is google DNS|
|`DNS2`|`127.0.0.1#5053`|(optional) secondary upstream DNS provider, default is google DNS, none if only one DNS should used|

## Usage

* <https://www.balena.io/blog/deploy-network-wide-ad-blocking-with-pi-hole-and-a-raspberry-pi/>

## Help

If you're having trouble getting the project running, submit an issue or post on the forums at <https://forums.balena.io>.

## Author

Kyle Harding <https://klutchell.dev>

## Acknowledgments

* <https://github.com/pi-hole/docker-pi-hole/>
* <https://firebog.net/>
* <https://github.com/anudeepND/whitelist>

## License

[MIT License](./LICENSE)
