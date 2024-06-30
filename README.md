Solar Analytics Integration for Home Assistant Energy Monitoring
================================================================
Last updated for Release 7.

This is a Solar Analytics public API integration into Home Assistant.

In summary, the solution provides daily cumulative consumed/generated, exported/imported energy (Wh) 
and various load energy (where applicable). These sensors can be configured to work with the Home Assistant 
Energy Monitoring capability. There are also 1-minute power sensors for consumed/generated and exported/
imported power. Lastly, general systems status information is provided.

There are 3 separate instances (files) for the code:
    1. <solar_analytics.yaml> - consumed/generated, imported/exported, and standard load sensors 
       including electric vehicle, heating-cooling, hot water and stove-oven (where available). Total
       daily kWh per load only.
    2. <solar_analytics_3phase.yaml> - consumed/generated and imported/exported total daily kWh only. 
       As a basic test, this would also work for single-phase but with no device load sensors.
    3. <solar_analytics_advanced.yaml> - load sensors as above, additionally broken down by total daily 
       kWh sourced from generated or imported sources, including % generated.

Included sensors as follows - see Solar_Analytics_sensors_notes_v7-30Jun24.xlsx/pdf for details:
    1. Solar Analytics portal, system and solar PV performance status. 
    2. Daily cumulative 5-minute energy Watt-hours per available channel, including:
        a. Consumed (energy_consumed) and generated (energy_generated) energy. 
           All instances.
        b. Imported and exported energy - derived from consumed and generated. 
           All instances.
        c. Electric Vehicle total energy kWh broken down into grid sourced (imported) kWh and generated 
           kWh with % of total generated kWh. 
           Not applicable to solar_analytics_3phase.yaml instance.
        d. Heating-cooling, Hot Water and Stove-Oven load energy kWh broken down into grid-sourced 
           (imported) kWh and generated kWh with % of total generated kWh. 
           Only for <solar_analytics_advanced.yaml> instance.
        e. All other energy - balance of total consumed energy that's not heating-cooling, EV charging, 
           hot water or stove-oven. 
           Only for <solar_analytics_advanced.yaml> instance.
    3. Generated expected energy to the hour within the day (as estimated by Solar Analytics). 
    4. 1-minute power Watts reporting of consumed/generated and import-exported power.
    5. Where costs are configured in the HA Energy Monitoring (fixed, peak/off-peak/shoulder, spot market 
       - e.g. Amber) there are sensors for: 
         > Cumulative daily net cost ($).
         > Average import rate ($/kWh).
         > Average export rate ($/kWh).
    6. Generated energy consumed kWh and % (of all generated), and Consumed energy generated kWh and % 
       (of all consumed).
    7. Power history sensor for graphing each SA available channel in Apex Charts (Lovelace sample code 
       included as <SA-apex-charts.yaml> - unfortunately technically limited by HA to 2h20m.     

HA Energy Monitoring requires the manual assignment of "Grid consumption", "Return to grid" and "Solar 
production" via the HA Energy configuration page. The individual energy channels (e.g. load_ev_charger, 
load_air_conditioner, load_stove) can also be added to the HA Energy Manager as "Monitor Individual Devices". 
Go to HA settings and search for “Energy Configuration” to make the changes. 

Set-up and updates from previous releases involve the installation of a stand-alone file included as a package 
in the configuration.yaml file - see the <solar_analytics.yaml> file for instructions. To upgrade from a 
previous version, please read the instructions in the code header text.

This integration draws on the API get calls defined in the Solar Analytics public open API definition. It 
also uses additional gets as learned from the Solar Analytics user portal.
https://api-docs.solaranalytics.com/OpenAPI-Specs/sapublic-openapi.yaml 

For those using Amber Electric as their electricity retailer and/or with an EV, additional bonus sensors are 
defined in <amber_forecast.yaml> and <amber_ev_charge_cost.yaml>, respectively. See the code header for the 
detailed description and usage.
 
If you find my work useful, please buy me a coffee ... thank you!
  https://www.buymeacoffee.com/peter24x7
