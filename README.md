Solar Analytics integration for Home Assistant Energy Monitoring
================================================================

This is a Solar Analytics public API integration into Home Assistant including:

    1. Solar PV system status; 
    2. Daily cumulative 5-minute energy Watt-hours per available channel (up to 6);
    3. Generated expected energy to the hour within the day; 
    4. 1-minute power Watts related reporting of consumed, generated and import-exported with conversions to kilo-Watts.
    5. Where costs are configured in HA Energy Monitoring (fixed, peak/off-peak/shoulder, spot market - e.g. Amber) provides 
         > cumulative daily net cost ($)
         > average import rate ($/kWh)
         > average export rate ($/kWh)

The solution provides daily cummulative consumed, generated, exported and imported energy (Wh). These variables are configured to work with the Home Assistant Energy Monitoring capability. System status information includes daily PV performance (%) and general status as reported by Solar Analytics.

Set-up involves the installation of a stand alone file included as a package in the configuration.yaml file - see the solar_analytics.yaml file for instructions. To upgrade from a previous version, simply replace the old solar_analytics.yaml file with the new (and repeat any required channel edits to match your SA channel set-up).

HA Energy Monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar production" via the HA Energy configuration page. The individual energy channels (e.g. load_ev_charger, load_air_conditioner, load_stove) can also be added to the HA Energy Manager as "Monitor Individual Devices". Go to HA settings and then search for “Energy Configuration” to make the changes. 

This integration draws on the API get calls defined in the Solar Analytics public open API definition. It also makes use of additional gets as learned from the Solar Analytics user portal.
https://api-docs.solaranalytics.com/OpenAPI-Specs/sapublic-openapi.yaml 

Developed by Peter Hormann and with thanks to Glen S and Roving-Ronin for their contributions.

If you find my work useful, please buy me a coffee ... thank you!
  https://www.buymeacoffee.com/peter24x7
