# Changelog for aiosenseme library

## v0.4.5

* Fix error when cancelling the listener task of a device when stop() is called. Thanks to [briantho](https://github.com/briantho) for bringing this to my attention.

## v0.4.4

* Fix protocol error on Windows and Python 3.7.8 and above. This error prevented discovery of any SenseME devices. Thanks to [briantho](https://github.com/briantho) for bringing this to my attention.

## v0.4.3

* Fix missing occupancy sensor for standalone Haiku Light. Regression caused by v0.4.2.

## v0.4.2

* Detects occupancy sensor for Haiku L fans with attached Wireless Wall Controller.

## v0.4.1

* Fix error discovery logic that treated a rediscovered Haiku Light as a new device.
* Removed some unhelpful discovery debug messages.
* Cleanup the usage of the word fan when device should be used.

## v0.4.0

* Now supports standalone Haiku Light. Thanks to [PenitentTangent2401](https://github.com/PenitentTangent2401) for help in testing and debugging these changes.
* Add ```--listen``` option to command line. This will open a connection to specified device name or IP address and show status information as the fans sends it.

## v0.3.3

* Ignore Wireless Wall Controllers. It appears this library will connect to them and cause lockups requiring a reset.
* Add error logging for unhandled exceptions in SensemeDiscovery._updater() and SensemeFan._listener().

## v0.3.2

* Add H-Series Haiku fan to known model list. Fan reports a slightly different model string for the Haiku Fan.
* Add model list to command line arguments.
* Add exception handling when creating discovery sockets. This should help the issue of a socket error on one network interface preventing discovery from working other network interfaces.

## v0.3.1

* SensemeFan.room_type now reports the room correctly.
* Removed socket option reuse_port for discovery as is appears to not work on MacOS and really isn't needed.
* Discovery no longer listens on loopback interface.

## v0.3.0

* Lots of linting changes.
* API breaking changes.
  * aiosenseme.Discover() is now aiosenseme.discover().
  * aiosenseme.Discover_Any() is now aiosenseme.discover_any().
* aiosenseme.discover() will now match Fan Name, Room Name and IP address.

## v0.2.1

* Requiring Python 3.7 was too restrictive. Back to allowing and testing Python 3.6.

## v0.2.0

* API breaking changes.
  * SensemeFan.group_status() is now SensemeFan.room_status().
  * SensemeFan.group_name() is now SensemeFan.room_name().
  * SensemeFan.group_room_type() is now SensemeFan.room_type().
* Now requiring python 3.7 or above. Not testing on anything lower.
* Add Discover() function to aiosenseme.
* Improved error handling in SensemeDiscovery and some testing on MacOS.
* Handle fan models differently and hopefully better in SensemeFan.
* Added SensemeFan.models() class method which returns an list of known models.
* API Added command line script capability.
* Added Type Hints.

## v0.1.1

* Add L-Series Haiku fan to known model list.

## v0.1.0

* Initial release.
