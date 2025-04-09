## Checks

- custom:mini-graph-card
    - should be referenced
        - url: /hacsfiles/mini-graph-card/mini-graph-card-bundle.js?hacstag=1512800620110
          type: module
- ping sensors
    - my_website
    - ping_valhalla_modem => router
    - ping_valhalla_router => switch
    - binary_sensor.ping_kitchen_mesh_repeater  => airport 
    - binary_sensor.ping_blue_cave_mesh
    - binary_sensor.ping_valhalla_outlet => outlet
    - binary_sensor.ping_bedroom_mesh_repeater  => 
    - binary_sensor.ping_dorothy_illinoise
    - states => entity.attributes.round_trip_time_avg

- clock
  - PixelIt <https://github.com/pixelit-project/PixelIt>
  - Ulanzi TC001
 
- dab+

- count of devices in **live_tile_with_last_changed_label**:
 ```yaml
label: |
      [[[
        var diff = (new Date() - new Date(entity.last_changed)) / 1000 / 60
        if (isNaN(diff)) { return 'Unknown' }
        if (diff <= 0.05) { return 'Just now' }
        else if (diff <= 1) { return Math.round(diff * 60) + ' seconds ago' }
        else { return 'From ' + Math.round(diff) + ' min.' }
      ]]]
```


- External IP address

https://www.home-assistant.io/integrations/sensor.rest/

```yaml
Template variable error: 'value_json' is undefined when rendering '{{ value_json.ip }}'

sensor:
  - platform: rest
    name: "External IP"
    resource: "https://api.ipify.org/?format=json"
    value_template: "{{ value_json.ip }}"

  - platform: rest
    name: "External IPv6"
    resource: "https://api6.ipify.org/?format=json"
    value_template: "{{ value_json.ip }}"
```

- ping (new) <https://community.home-assistant.io/t/graph-ping-round-trip-average-attribute/111772/5>

Legacy template:
*This format is configured as a platform for the binary_sensor integration and not directly under the template integration.*
*This format still works but is no longer recommended.*

```yaml
- platform: template
  sensors:
    template_ping_cloudflare:
      friendly_name: "Ping Cloudflare"
      value_template: "{{ states('binary_sensor.ping_cloudflare') }}"
      attribute_templates:
        round_trip_time_avg: "{{ states('sensor.ping_cloudflare_round_trip_time_average') }}"
```

The ping sensor is set up from the UI now.
The template sensor that exposes the round trip attribute from that as a sensor is still created in yaml. Though it too now has a new format:
New (configuration.yaml):

```yaml
template:
  - sensor:
      - name: Ping Google Average
        state: "{{ state_attr('binary_sensor.ping_google_dns', 'round_trip_time_avg') }}"
        unit_of_measurement: ms
```


