# Digest

## Hardware

Unison
- HASS instance RPi4b 4G RAM / 128GB SSD
- ConBee II zigbee dongle
- GW Insteon hub
- GW Philips Hue hub

Terpsichora
- Logitech Harmony Hub (Entertainment)

Genesis
- Prusa 3D printer

Misc
- Ikea Tradfri ZigBee signal repeaters

## Interesting issues

- button-card/button-card.js reference in configuration.yaml <https://github.com/Madelena/hass-config-public/issues/3>
- configuration.yaml <https://github.com/Madelena/hass-config-public/issues/12>
- bar-row <https://github.com/Madelena/hass-config-public/issues/27>
- ping sensor <https://github.com/Madelena/hass-config-public/issues/9>
- isometric svg floorplan created via Sketchup 
- network rail map <https://github.com/Madelena/hass-config-public/issues/36>
- network rail map <https://github.com/Madelena/hass-config-public/issues/34>


## Dashboards

**Axonometric Floor Plan:**
- isometric-floorplan: https://github.com/knicholson32/isometric-floorplan?tab=readme-ov-file

Speedtest.net: <https://www.home-assistant.io/integrations/speedtestdotnet/>
  - sensor.speedtest_download
  - sensor.speedtest_upload
  - sensor.speedtest_ping

Include_templates: <https://www.reddit.com/r/homeassistant/comments/wu0870/how_to_include_templates_when_in_ui_editing_mode/>

Ping Integration:
 - Network rail card with new ping sensor: <https://github.com/Madelena/hass-config-public/issues/34>
 - <https://www.home-assistant.io/integrations/ping/>
 - <https://community.home-assistant.io/t/ping-icmp-automation/745295/10>
 - <https://github.com/home-assistant/core/issues/121875>

Ping de services web:
 - <https://www.antoineguilbert.fr/monitoring-ping-services-web-sur-home-assistant/>


## NETWORK Sensors list:

- binary_sensor.ping_cloudflare
- binary_sensor.ping_google
- binary_sensor.ping_my_website
- sensor.asuswrt_devices_connected
- sensor.speedtest_download
- sensor.valhalla_router_connected_devices
- binary_sensor.ping_valhalla_outlet
- binary_sensor.ping_valhalla_modem
- binary_sensor.ping_valhalla_router
- binary_sensor.ping_blue_cave_mesh
- binary_sensor.ping_kitchen_mesh_repeater
- binary_sensor.ping_bedroom_mesh_repeater
- binary_sensor.ping_dorothy_illinoise
- sensor.valhalla_router_wan_download_speed
- sensor.network_throughput_out_eth0 
- sensor.valhalla_router_wan_download
- sensor.valhalla_router_wan_upload_speed
- sensor.network_throughput_in_eth0
- sensor.valhalla_router_wan_upload
- sensor.valhalla_router_wired_download_speed
- sensor.workspace_mesh_node_wired_download_speed
- sensor.bedroom_mesh_node_wired_download_speed
- sensor.valhalla_router_wired_download
- sensor.workspace_mesh_node_wired_download
- sensor.bedroom_mesh_node_wired_download
- sensor.valhalla_router_wlan0_download_speed
- sensor.workspace_mesh_node_wlan0_download_speed
- sensor.bedroom_mesh_node_wlan0_download_speed
- sensor.valhalla_router_wlan0_download
- sensor.workspace_mesh_node_wlan0_download
- sensor.bedroom_mesh_node_wlan0_download
- sensor.valhalla_router_wlan1_download_speed
- sensor.workspace_mesh_node_wlan1_download_speed
- sensor.bedroom_mesh_node_wlan1_download_speed
- sensor.valhalla_router_wlan1_download
- sensor.workspace_mesh_node_wlan1_download
- sensor.bedroom_mesh_node_wlan1_download
- sensor.valhalla_router_wired_upload_speed
- sensor.workspace_mesh_node_wired_upload_speed
- sensor.bedroom_mesh_node_wired_upload_speed
- sensor.valhalla_router_wired_upload
- sensor.workspace_mesh_node_wired_upload
- sensor.bedroom_mesh_node_wired_upload
- sensor.valhalla_router_wlan0_upload_speed
- sensor.workspace_mesh_node_wlan0_upload_speed
- sensor.bedroom_mesh_node_wlan0_upload_speed
- sensor.valhalla_router_wlan0_upload
- sensor.workspace_mesh_node_wlan0_upload
- sensor.bedroom_mesh_node_wlan0_upload
- sensor.valhalla_router_wlan1_upload_speed
- sensor.workspace_mesh_node_wlan1_upload_speed
- sensor.bedroom_mesh_node_wlan1_upload_speed
- sensor.valhalla_router_wlan1_upload
- sensor.workspace_mesh_node_wlan1_upload
- sensor.bedroom_mesh_node_wlan1_upload

VALHALLA ROUTER:

- sensor.valhalla_router_cpu
- sensor.valhalla_router_temperature_cpu
- sensor.valhalla_router_ram
- sensor.valhalla_router_connected_devices

UNISON:

- sensor.unison_processor_use
- sensor.unison_processor_temperature
- sensor.unison_glances_ram_used_percent

VALHALLA OUTLET:

- binary_sensor.valhalla_outlet_modem
- binary_sensor.valhalla_outlet_router
- sensor.valhalla_outlet_event

WIFI SIGNAL STRENGTH:

- sensor.weatherman_wifi_signal_sensor
- sensor.kaleidoscape_wifi_signal_strength
- sensor.zuneth_wifi_signal_strength

ADGUARD (a0d7b954_adguard):

- sensor.adguard_dns_queries
- sensor.adguard_dns_queries_blocked_ratio
- sensor.adguard_average_processing_speed

## ASTROMETRICS Sensors list:

- binary_sensor.ping_my_website (url_path: 'https://MadelenaMak.com')
- binary_sensor.ping_my_website (url_path: 'https://www.astrospheric.com/')

- sensor.noaa_space_weather_solar_wind_magnetic_fields_bt
- sensor.noaa_space_weather_solar_wind_magnetic_fields_bz
- sensor.noaa_space_weather_solar_wind_speed
- sensor.noaa_space_weather_noon_10_7cm_radio_flux
- sensor.aurora_visibility_aurora_visibility
- sensor.noaa_space_weather_alerts
- sensor.noaa_space_weather_alert_1
- sensor.noaa_space_weather_alert_2
- sensor.noaa_space_weather_alert_3
- sensor.noaa_space_weather_alert_4
- sensor.noaa_space_weather_alert_5

- Radio Blackout: sensor.noaa_space_weather_r_24hr
- Solar Radiation Storm: sensor.noaa_space_weather_s_24hr
- Geomagnetic Storm: sensor.noaa_space_weather_g_24hr

- sensor.noaa_space_weather_r_latest
- sensor.noaa_space_weather_s_latest
- sensor.noaa_space_weather_g_latest
- sensor.noaa_space_weather_r_majorprob_1day
- sensor.noaa_space_weather_r_minorprob_1day
- sensor.noaa_space_weather_s_1day
- sensor.noaa_space_weather_g_1day
- sensor.noaa_space_weather_r_majorprob_2day
- sensor.noaa_space_weather_r_minorprob_2day
- sensor.noaa_space_weather_s_2day
- sensor.noaa_space_weather_g_2day
- sensor.noaa_space_weather_r_majorprob_3day
- sensor.noaa_space_weather_r_minorprob_3day
- sensor.noaa_space_weather_s_3day
- sensor.noaa_space_weather_g_3day

**Luna Location, Planetary Positions, Man Made Object locations (ISS, etc.)**

- sensor.nasa_iss_station_report
- sensor.rocketlaunch_live_next_1
- sensor.rocketlaunch_live_next_2
- sensor.rocketlaunch_live_next_3
- sensor.rocketlaunch_live_next_4
- sensor.rocketlaunch_live_next_5
