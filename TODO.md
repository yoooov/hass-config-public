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

See <https://www.home-assistant.io/integrations/template/#configuration-variables>

```yaml
- platform: template
  sensors:
    template_ping_cloudflare: # sensor_name => The slug of the sensor.
      friendly_name: "Ping Cloudflare" # Name to use in the frontend.
      # unique_id string (Optional) An ID that uniquely identifies this binary sensor. Set this to a unique value to allow customization through the UI.
      value_template: "{{ states('binary_sensor.ping_cloudflare') }}" # The sensor is on if the template evaluates as True and off otherwise. The actual appearance in the frontend (Open/Closed, Detected/Clear etc) depends on the sensor’s device_class value

      # attribute_templates => Defines templates for attributes of the sensor.
      #   attribute: template => The attribute and corresponding template.
      attribute_templates:
        round_trip_time_avg: "{{ states('sensor.ping_cloudflare_round_trip_time_average') }}"
```

Convert from old legacy to new yaml config <https://community.home-assistant.io/t/migrating-from-legacy-templates/428536/3>

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


**Glances** on Mac OS

```
$ python3 -m pip install "glances[all]"
# see https://github.com/nicolargo/glances/issues/3116
$ python3 -m pip uninstall netifaces2
$ python3 -m pip install netifaces-plus

$ which glances
/Library/Frameworks/Python.framework/Versions/3.12/bin/glances
```

# set a plist com.tatooine.glances-web.plist
```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
	<key>KeepAlive</key>
	<true/>
	<key>Label</key>
	<string>com.tatooine.glances-web</string>
	<key>ProcessType</key>
	<string>Interactive</string>
	<key>ProgramArguments</key>
	<array>
		<string>/Library/Frameworks/Python.framework/Versions/3.12/bin/glances</string>
		<string>-w</string>
	</array>
	<key>StandardErrorPath</key>
	<string>/Users/yoannvidil/Library/Logs/com.tatooine.glances-web.err.log</string>
	<key>StandardOutPath</key>
	<string>/Users/yoannvidil/Library/Logs/com.tatooine.glances-web.log</string>
</dict>
</plist>
```

Then `$ launchctl load ~/Library/LaunchAgents/com.tatooine.glances-web.plist`
