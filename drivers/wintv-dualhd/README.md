# WinTV-dualHD extension

This system extension provides the kernel modules required for the Hauppauge WinTV-DualHD device.

## Installation

See [Installing Extensions](https://github.com/siderolabs/extensions#installing-extensions).

## Usage

Enable the `wintv-dualhd` module in Talos machine config to enable `/dev/video` devices from USB devices supporting the USB video device class.

```yaml
machine:
  kernel:
    modules:
      - name: wintv-dualhd
```

## Verifiying

You can verify the modules are enabled by reading the `/proc/modules` where it _should_ show the module is live.

For example:

```
❯ talosctl -n 192.168.42.15 read /proc/modules
i2c_mux 16384 1 lgdt3306a, Live 0xffffffffc5d67000
dvb_core 217088 1 em28xx_dvb, Live 0xffffffffc5d07000
em28xx 131072 2 em28xx_rc,em28xx_dvb, Live 0xffffffffc5cc7000
em28xx_dvb 49152 0 - Live 0xffffffffc5d51000
```
