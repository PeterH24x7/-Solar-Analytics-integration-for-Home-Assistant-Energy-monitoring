Solar Analytics integration for Home Assistant Energy monitoring
================================================================

This is a Solar Analytics public API integration into Home Assistant including:

    1. Solar PV system status; 
    2. Daily cumulative 5-minute energy Watt-hours per available channel (up to 6);
    3. Generated expected energy to the hour within the day; 
    4. 1-minute power Watts related reporting of consumed, generated and import-exported with conversions to kilo-Watts.
    5. Where costs are configured in HA Energy Manager (e.g. fixed, peak/off-peak/should, spot market) provides 
         > cumulative daily net cost ($)
         > average import rate ($/kWh)
         > average export rate ($/kWh)

The solution provides daily cummulative consumed, generated, exported and imported energy (Wh). These variables are configured to work with the Home Assistant Energy monitoring capability. System status information includes daily PV performance (%) and general status as reported by Solar Analytics.

Set-up involves the installation of a stand alone file included as a package in the configuration.yaml file - see the solar_analytics.yaml file for details.

HA Energy Monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar production" via the HA Energy configuration page. The individual energy channels (e.g. load_ev_charger, load_air_conditioner) can also be added to the HA Energy Manager as "Monitor Individual Devices". Go to HA settings and then search for “Energy Configuration” to make the changes.  

Developed by Peter Hormann and with thanks to Glen S and Roving-Ronin for their contributions.

If you find my work useful, please buy me a coffee ... thank you!
  https://www.buymeacoffee.com/peter24x7
