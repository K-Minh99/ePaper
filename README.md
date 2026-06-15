# E-Paper Tag Controller

Static Web Bluetooth controller for the DA14585 e-paper tag firmware.

## Pages

After GitHub Pages is enabled for the `main` branch, open:

https://k-minh99.github.io/ePaper/

## BLE UUIDs

- Service: `18424398-7cbc-11e9-8f9e-2a86e4085a59`
- Control point: `2d86686a-53dc-25b3-0c4a-f0e10c8dee20`

## Protocol v1

The page sends one 16-byte packet:

| Byte | Meaning |
| --- | --- |
| 0..3 | ASCII `EPD1` |
| 4 | Command `0x01`: set config and refresh |
| 5 | Layout: `0` status, `1` clock, `2` calendar |
| 6 | Flags, currently `0` |
| 7 | Weekday: Monday `1` through Sunday `7` |
| 8 | Year offset from 2000 |
| 9 | Month |
| 10 | Day |
| 11 | Hour |
| 12 | Minute |
| 13 | Second |
| 14 | Reserved |
| 15 | Checksum: sum of bytes 0..14 modulo 256 |

Web Bluetooth requires HTTPS or localhost. GitHub Pages is suitable for phone testing on Chrome Android.
