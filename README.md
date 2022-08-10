Solar Analytics integration for Home Assistant Energy monitoring
================================================================

This is a Solar Analytics public API integration into HA including solar PV system status and live energy and power related data.

The solution provides daily cummulative consumed, generated, exported and imported energy (Wh). These variables are configured to work with the Home Assistant Energy monitoring capability. System status information includes daily PV performance (%) and general status as reported by Solar Analytics.

Set-up involves sensor additions to the HA configuration.yaml file and the users Solar Analytics account username/password to be defined in the secrets.yaml file. There is also an option to have a stand alone file included as a package in the configuration.yaml file - see the solar_analytics.yaml file for details.

HA Energy monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar production" via the HA Energy configuration page. The individual energy sensors can also be added to the HA Energy Manager as "Monitor Individual Devices". Go to HA settings and then search for “Energy Configuration” to make the changes.

Thank you to @TheOtherGlen for contributing his YAML template coding expertise.
