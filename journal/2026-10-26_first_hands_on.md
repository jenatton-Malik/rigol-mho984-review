# 2026-10-26 — First hands-on

## 🎯 Goal
Get to know the instrument before any formal measurement. Nothing here is a measurement for the article: every comparison below will be redone under protocol. Only 2 screenshots taken, nothing documented on purpose.

## ⚙️ Setup
- Bundle: MHO900-BND (all options except 500 Mpts memory)
- Licences installed over Ethernet (LAN)
- Firmware: *(to note)*
- Self-calibration: done after ~1 h warm-up *(note room temperature if possible)*
- Probe compensation: done on the RP3500A probes

## 📝 What I tried
- 4 channels and 100 Mpts memory
- Near-field probes on a 50 Ω input
- Logic analyser (PLA2216) decoding UART
- AFG (2 channels)
- Bode plot
- FFT, including the AFG harmonics *(keep these screenshots: they are the reference for the EMI tests)*
- Very low amplitude signals
- Side by side with the Hantek DSO2D15: 100 MHz signals, low amplitude, FM
- A small audio amplifier
- An LC low-pass filter on breadboard

## 💭 First impressions
- **Fluidity**: the display and touchscreen are very responsive. The Hantek lags at 8 Mpts, so in practice I kept it at 4 kpts most of the time.
- **Memory**: 100 Mpts is a huge step coming from 8 Mpts that I could not really use.
- **Signal quality**: traces look clean and stable.
- **AFG**: 2 channels, 16 bits, 1 GSa/s. Far beyond the Hantek's built-in AWG.
- **Interface**: intuitive.
- **Form factor**: compact, ergonomic, well built. I like compact bench tools.
- **Side by side with the Hantek**: not in the same league. *(To be backed by measurements, and to keep in mind: about 5× the price.)*

## 👎 What annoyed me
- **Wi-Fi**: the scope comes with a Wi-Fi dongle, but my Wi-Fi password is too long to be entered, so I could not connect it. Ethernet is hard to reach in my lab, so no LAN control for now.
- **Wi-Fi IP not displayed** (2026-10-27): the WLAN page showed no IP, gateway or DNS at first, although the scope was reachable at the IP found in Freebox OS. After the online firmware update, the IP is displayed (192.168.1.20). Removed from the article. Note: Utility → IO is the Ethernet port, "DISCONNECTED" there is normal without a cable.
- **Fan noise**: constant, slightly unpleasant fan noise.
- **No protective earth**: the scope is powered over USB-C Power Delivery, so its chassis is not earthed. The supplied ground cable is male-to-male, and French sockets have a male earth pin: it cannot be plugged into a wall socket.
- **Logic analyser**: works, but hard to get into, not the most intuitive part of the UI.
- **Probe ratio resets to ×1 at power-on**: the RP3500A probes are ×10, so after each restart the vertical scale is wrong by a factor 10. Caught me more than once. **Solved on 2026-10-27**: Utility → Setup → power-on set to "Load Last" instead of "Default". Not a bug, but a default setting that is easy to miss.

## ➡️ Next
- Find a way to connect it: USB (USBTMC) from the PC, or a network with a shorter password
- Find a safe earth point for the ground cable (earthed bench instrument, checked with a multimeter)
- Noise floor table, automated over SCPI — log which USB-C charger is used, and floating vs earthed
