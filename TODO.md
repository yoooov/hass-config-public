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

```
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

