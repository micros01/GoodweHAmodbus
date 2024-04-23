# GoodweHAmodbus
Homeassistant modbus config for Goodwe ET 15

The content in GoodweET15.yaml should be in the configuration.yaml file (remember to restart homeassistant after added)
sensors.yaml contains a template for translating the status of the battery to a readable 

Create helpers for calculating total effect and for each string
# PV1 Effect (replace "pv1" for PV2..4)
{{states('sensor.goodwe_current_pv1_string')|float * states('sensor.goodwe_voltage_pv1_string')|float}}

# Total Effect
{{states('sensor.goodwe_pv1_effect')|float + states('sensor.goodwe_pv2_effect')|float + states('sensor.goodwe_pv3_effect')|float + states('sensor.goodwe_pv4_effect')|float}}

# Battery SOC %
{{states('sensor.goodwe_battery_soc')|float*10}}