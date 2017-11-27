# Build and Deploy

This repo contains scripts to create a standalone, single machine deployment for testing and evaluation purpopses.

The following items are configured and run

- Platform; the core HIOT platform, consisting of REST servers for the main UI project, running on http://localhost:3000
- UI: the core HIOT UI, running on http://localhost:4200
- Coordinator_link: MQTT pub/sub implementation to connect the platform-side with the deployment-side (MQTT port 1833)
- Coordinator: edge device for the deployment, connnects to Coordinator_link and is the only communication channel between the platform and the deployment. (MQTT port - for deployment - 2833)
- Device 1 : Broker & sensor device to send commands from the coordinator to specific controllers on particular devices. Rand_sensor installed (Broker MQtt on port 3833)
- Device 2 : Controller device, with demo_controller installed, commands are sent to the console 
- Device 3 : Controller & sensor device: 2x Rand_sensor installed and 1 x demo controller installed
- Device 4 : Aggregator and sensor: aggregator device for all sensors above, rand_sensor installed, but not aggregated anywhere (Aggregator MQTT on 4833)
- Commander Device : commander installed to control all controllers above and display output from all sensors - all vai coordinator


-- git clone device
-- make 4 copies of device folder (device, broker, aggregator, commander, coordinator)
-- copy config files from device_configs to each of the above folders
-- start all 5 devices
-- git clone coordinator_link
-- start coordinator link
-- git clone platform 
-- start platform
-- git clone ui
-- start ui