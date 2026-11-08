# XIAO ESP32-S3 race logger (designed, never built)

Two paper designs for moving the race logger onto a Seeed XIAO ESP32-S3. Neither was built (user,
2026-11-08). The device actually in use is v2 (see the top-level README).

| File | What | Date |
|---|---|---|
| `pin_layout.md` | Pin plan: M9N on I2C with the BNO085, CAN on D0/D1, SD on D8–D10 + D6, mode switch and staging button | 2026-05-31 |
| `esp32_robo_capture/` + `robo_capture_wiring.txt` | Firmware and wiring ("Robo Capture"): M9N on UART D6/D7, CAN on D2/D3, mode switch on D1, trip/race modes, MQTT + SD, WiFiManager portal | 2026-06-03 |

The two disagree on almost every pin, so they are separate attempts, not one design.

Known problem in `robo_capture_wiring.txt`: it powers the TJA1051 from 3V3. The TJA1051 needs a
4.5–5.5 V supply (NXP datasheet; robo-services `docs/hardware/tja1051_breakout.md`).

Not compiled since the move: WiFiManager is not installed in this machine's arduino-cli.

Moved from robo-services `capture_device_configs/robo-capture/` and
`capture_device_configs/final_layout.md` (robo-services e706852 and earlier).
