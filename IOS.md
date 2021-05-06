# IOS Users

You can also do the "hacks" by hand using the [nRF Connect](https://apps.apple.com/nl/app/nrf-connect-bluetooth-app/id1054362403 "nRF Connect") app or the [BLE Scanner](https://apps.apple.com/nl/app/ble-scanner-4-0/id1221763603 "BLE Scanner") app from the Apple Store.

## Usage

Disable speedlimit (tested on Cowboy V1+) but should work on V2 and V3 too.
It's completely at your own risk, your bike will be "illegal" in some countries. However the police cannot see it in the app.

##### Unlock your bike with the Cowboy app.
##### Kill the Cowboy app and make sure it's not running in the backround.

For more information on the nRF Connect app go to [here](https://devzone.nordicsemi.com/f/nordic-q-a/22523/writing-hex-values-to-characteristics-using-nrf-connect "here").

So use the nRF Connect app. It seems you have to connect to the Cowboy and then disable“Parse known characteristics". Now you can select "BYTE ARRAY" when sending. I assume this will solve the problem of the values not written correctly on some devices.
Connect to your Cowboy and make sure it's connected and bonded. Go to Nordic UART Service Send values to RX Characteristic.

- Disable speed limit: `0110000b000102000166eb`
<br>or<br>
Enable speed limit (default): `0110000b000102000226ea`

- Field weakening 20%: `0110008100010203f8a4`
<br>or<br>
Field weakening 15%: `011000810001020266390b`
<br>or<br>
Field weakening 0% (default): `011000810001020000b841`
- Store in flash: `011001ff0001027fffc2ef`
- Close flash: `011001ff0001020000a29f`

If you have followed the steps above the settings should be made and you can start using the regular Cowboy app again.