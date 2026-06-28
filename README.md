# E-Paper Tag Web

Web Bluetooth controller for the DA14585 e-paper tag firmware.

Open the GitHub Pages site:

https://k-minh99.github.io/ePaper/

## Update Flow

- The web app checks `firmware/manifest.json` on GitHub Pages.
- When a newer firmware image is available, the user can connect the BLE tag and press update.
- The browser downloads the `.img` file from GitHub, verifies size and SHA-256, then sends it to the device through BLE safe OTA.
- If BLE disconnects before the final commit command, the old firmware remains active.

## BLE UUIDs

- Service: `18424398-7cbc-11e9-8f9e-2a86e4085a59`
- Control point: `2d86686a-53dc-25b3-0c4a-f0e10c8dee20`

Web Bluetooth requires HTTPS or localhost. GitHub Pages is suitable for Chrome on Android and desktop Chrome.
