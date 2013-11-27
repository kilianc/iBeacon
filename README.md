# iBeacon Firmware
This is an iBeacon compatible firmware for Bluegiga BLE112. Supports `CLBeaconRegion` and `didRangeBeacons`. All configurable from the gatt.xml file.

## Example configuration
This configures an iBeacon discoverable with the AirLocate app from Apple downloadable from the dev center or [here](http://docs.xamarin.com/samples/AirLocate/)
```xml
<service uuid="06F5641F-4340-47D8-BB87-E5121946E7B7">
    <description>iBeacon conf</description>
    <characteristic uuid="D96B4F96-8857-4169-A6B1-87A9F6F4A264" id="xgatt_ibeacon_flags">
      <properties const="true" />
      <value type="hex">020106</value>
    </characteristic>
    <characteristic uuid="2AC3ADFC-370E-4985-A186-CAA385AE0E0B" id="xgatt_ibeacon_manu">
      <properties const="true" />
      <value type="hex">1aff</value>
    </characteristic>
    <characteristic uuid="C1259AD9-F7DB-4E21-8F3C-E65EF7F4E4C3" id="xgatt_ibeacon_preamble">
      <properties const="true" />
      <value type="hex">4c000215</value>
    </characteristic>
    <characteristic uuid="77138B0E-0EBA-4171-B3D7-0EE39E37BEFD" id="xgatt_ibeacon_uuid">
      <properties const="true" />
      <value type="hex">e2c56db5dffb48d2b060d0f5a71096e0</value>
    </characteristic>
    <characteristic uuid="BFC90CD7-195F-4478-90A9-1451F1976F9D" id="xgatt_ibeacon_major">
      <properties const="true" />
      <value type="hex">00</value>
    </characteristic>
    <characteristic uuid="8A34E41A-4462-45CF-8B60-D57BEBD28B20" id="xgatt_ibeacon_minor">
      <properties const="true" />
      <value type="hex">00</value>
    </characteristic>
    <characteristic uuid="4109997D-D141-4FF1-A254-30AEFC33D394" id="xgatt_ibeacon_tx_pwr">
      <properties const="true" />
      <value type="hex">c6</value>
    </characteristic>
  </service>
```

## Uploading the firmware (Windows only #sadface)
In order to compile and upload the firmware, you need the **Texas Instrument CC Debugger** SPI programmer and the `BLE SW Update Tool` included in the Bluegiga SDK. Just click on the ibeacon.bgproj and hit `update`. You can also compile the `hexfile` with `bgbuild.exe`, also included in the SDK, and then upload the firmware with DFU or over the air.