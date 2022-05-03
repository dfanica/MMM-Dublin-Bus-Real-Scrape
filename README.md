# MMM-Dublin-Bus-Real-Scrape
Magic Mirror Module - Dublin Bus Real Scrape

This an extension for the [MagicMirror](https://github.com/MichMich/MagicMirror). It displays bus times for a configurable stop. This uses the [Dublin Bus RTPI](https://www.dublinbus.ie/RTPI/Sources-of-Real-Time-Information/) website and scraping the real time information data, therefor is only useful within Dublin, Ireland and surrounding areas.

## Installation

- Navigate into your MagicMirror's `modules` folder and execute `git clone https://github.com/dfanica/MMM-Dublin-Bus-Real-Scrape.git`.
- Install the dependancies with `npm install`
- Configure the module as mentioned below.
- Start/Restart magic mirror

## Using the module

This module can display times on MagicMirror's position view or through using MagicMirror's alert module. It can be started or stopped using Magic Mirror's internal notification system, enabling the ability for other modules to control when it will request from Dublin Bus RTPI website. The two notifications MMM-Dublin-Bus will listen to are `DUBLIN_BUS_START` and `DUBLIN_BUS_STOP`.

Once installed, to use it add it to the modules array in the `config/config.js` file:

```javascript
modules: [
    {
        "module": "MMM-Dublin-Bus-Real-Scrape",
        "position": "top_left",
        "config": {
            "stop": <LOCAL_STOP_NUMBER>
        }
    }
]
```

## Configuration Options

The following properties can be configured, as well as any of the default Magic Mirror configuration [settings](https://github.com/MichMich/MagicMirror#configuration).

| Option 			| Default 			| Description 																																																								|
|-------------------|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|`stop` 		| _REQUIRED_ 	|Stop numbers can be found on the [Dublin Bus Route Planner](https://www.dublinbus.ie/RTPI)																																		|
|`mode`				| `module`				|The options supported are either `module`, `alert` or `enhanced`. This sets how the bus times are to be displayed. In `alert` mode all times are displayed using Magic-Mirror's notification system. In `module` mode it is displayed on the main screen and in `enhanced` mode you get both the module view and the alert. 	|
|`interval` 	| `10000` 			|An `int` value to set the API polling interval in seconds																																													|
