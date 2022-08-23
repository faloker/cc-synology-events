# Cribl Pack for Synology NAS Events
----

The Cribl Pack for Synology NAS processes events with the following goals in mind:

* Events are received via syslog directly from Synology NAS
* The pack is designed to send logs to the Splunk destination, so it embeds some additional information in the events:
  * splunk metadata (index, sourcetype, host)
  * fields are named according to the Splunk Common Information Model ([CIM](https://docs.splunk.com/Documentation/CIM/5.0.1/User/Overview)), so it will work with Splunk Enterprise Security out of the box
* Reduction of events by trimming the Syslog header, removing unnecessary fields and droping logs about suppression.

You should expect to see 10-30% reduction in the size of your Synology NAS log data.

## Configuration

Before you begin, ensure that you have met the following requirements:
* Synology - DSM
  * See instructions below (or visit the [official DSM docs](https://kb.synology.com/en-global/DSM/help/LogCenter/logcenter_client))
* Cribl Stream - Syslog input
  * Pack pipelines are designed to remove all unnecessary syslog fields, such as severity, facility, facilityName, appname, etc., and leave only the important ones.
  
**Note - This pack was _NOT_ tested in conjunction with the [cribl-syslog-input](https://github.com/criblpacks/cribl-syslog-input) pack.**

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

### Version 0.1.3 - 2022-08-18
Minor release with a fix that changes the order of routes to avoid parsing problems.

### Version 0.1.2 - 2022-08-16
A few changes to regexes to extract more fields when possible.

### Version 0.1.1 - 2022-07-17
Minor release to fix version mismatch, update README and samples.

### Version 0.1.0 - 2022-07-08
Initial release.


## Contributing to the Pack
To contribute to the pack, please open a [pull request on GitHub](https://github.com/faloker/cc-synology-events/pulls).


## Contact
Feel free to reach out to <faloker@tuta.io>.


## License
This Pack uses the following license: [`Apache 2.0`](https://github.com/faloker/cc-synology-events/blob/main/LICENSE).