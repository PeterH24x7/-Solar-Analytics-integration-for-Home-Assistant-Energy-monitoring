# -Solar-Analytics-integration-for-Home-Assistant-Energy-monitoring
Solar Analytics public API integration into HA including solar PV system status and data.

This formative solution provides daily cummulative consumed, generated, exported and imported energy (Wh). These variables are configured to work with the Home Assistant Energy monitoring capability. System status information includes daily PV performance (%) and general status as reported by Solar Analytics.

Set-up involves sensor additions to the HA configuration.yaml file and the users Solar Analytics account username/password to be defined in the secrets.yaml file.
HA Energy monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar production" via the HA Energy configuration page.
