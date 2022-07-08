# Cribl Pack for Synology NAS Events
----

The Cribl Pack for Synology NAS processes events with the following goals in mind:

1. Events are received via syslog directly from Synology NAS
1. Add Splunk metadata to events (e.g. index, source, sourcetype, host) and extract fields with Splunk CIM in mind
1. Reduction of events by trimming the Syslog header, removing unnecessary fields and droping logs about suppression.

You should expect to see 10-30% reduction in the size of your Synology NAS log data.


## Configuration

Before you begin, ensure that you have met the following requirements:

* Synology - See instructions below (or visit https://kb.synology.com/en-global/DSM/help/LogCenter/logcenter_client)
* Cribl Stream - Syslog input

### Synology DSM 

* Install the Log Center package from the Package Center.
* Configure the Log Sending settings.
  * Server: IP or hostname of Cribl Stream.
  * Port: Listening port (514)
  * Transfer Protocol: UDP or TCP
  * Log format: BSD (RFC 3164)
* Configure the Log Filters settings.
* Configure the File Transfer logs.
  * Go to Control Panel > File Services
  * For SMB, click Enable Tranfer Log and then configure the Log Settings. 



## Release Notes

### Version 0.1.0 - 2022-07-08
Initial release.


## Contributing to the Pack
To contribute to the Pack, please open a pull request.


## Contact
To contact us please email <faloker@tuta.io>.


## License
This Pack uses the following license: [`Apache 2.0`](https://github.com/faloker/cc-synology-events/blob/main/LICENSE).
