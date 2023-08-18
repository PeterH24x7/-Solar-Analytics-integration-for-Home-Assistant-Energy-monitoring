Solar Analytics integration for Home Assistant Energy Monitoring
================================================================

This is a Solar Analytics public API integration into Home Assistant including sensors for the following:

    1. Solar PV system status; 
    2. Daily cumulative 5-minute energy Watt-hours per available channel (up to 6);
    3. Generated expected energy to the hour within the day; 
    4. 1-minute power Watts related reporting of consumed, generated and import-exported with conversions to 
       kilo-Watts.
    5. Where costs are configured in HA Energy Monitoring (fixed, peak/off-peak/shoulder, spot market 
       - e.g. Amber) provides 
         > cumulative daily net cost ($)
         > average import rate ($/kWh)
         > average export rate ($/kWh)
    6. Generated energy consumed kWh and % (of all generated), and Consumed energy generated kWh and % 
       (of all generated).
    7. Electric Vehicle total energy kWh broken down into grid sourced (imported) kWh and generated kWh 
       with % of total charged kWh.
    8. Energy history sensor for graphing each SA channel in Apex Charts (Lovelace sample code included 
       as <SA-apex-charts.yaml> - unfortunately technically limited by HA to 2h20m.     

The solution provides daily cummulative consumed, generated, exported and imported energy (Wh). These 
variables are configured to work with the Home Assistant Energy Monitoring capability. System status 
information includes daily PV performance (%) and general status as reported by Solar Analytics.

Set-up and updates from previous releases involves the installation of a stand alone file included as a package 
in the configuration.yaml file - see the <solar_analytics.yaml> file for instructions. To upgrade from a 
previous version please read the  instructions included in the code header text.

HA Energy Monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar 
production" via the HA Energy configuration page. The individual energy channels (e.g. load_ev_charger, 
load_air_conditioner, load_stove) can also be added to the HA Energy Manager as "Monitor Individual Devices". 
Go to HA settings and then search for “Energy Configuration” to make the changes. 

This integration draws on the API get calls defined in the Solar Analytics public open API definition. It 
also makes use of additional gets as learned from the Solar Analytics user portal.
https://api-docs.solaranalytics.com/OpenAPI-Specs/sapublic-openapi.yaml 

For those using Amber Electric as their electricity retailer and/or with an EV there are additional bonus
sensors defined in <amber_forecast.yaml> and <amber_ev_charge_cost.yaml> respectively. See the code header 
for the detailed description and usage.
 
If you find my work useful, please buy me a coffee ... thank you!
  https://www.buymeacoffee.com/peter24x7
