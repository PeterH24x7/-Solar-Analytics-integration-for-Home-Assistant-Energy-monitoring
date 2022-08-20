Solar Analytics integration for Home Assistant Energy monitoring
================================================================

This is a Solar Analytics public API integration into Home Assistant including solar PV system status, 5-minute energy and 1-minute power related reporting.

The solution provides daily cummulative consumed, generated, exported and imported energy (Wh). These variables are configured to work with the Home Assistant Energy monitoring capability. System status information includes daily PV performance (%) and general status as reported by Solar Analytics.

Set-up involves the installation of a stand alone file included as a package in the configuration.yaml file - see the solar_analytics.yaml file for details.

HA Energy Monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar production" via the HA Energy configuration page. The individual energy channels (e.g. load_ev_charger, load_air_conditioner) can also be added to the HA Energy Manager as "Monitor Individual Devices". Go to HA settings and then search for “Energy Configuration” to make the changes.  

Thank you to @TheOtherGlen for contributing his YAML template coding expertise.
