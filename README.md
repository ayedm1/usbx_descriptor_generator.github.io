# USBX Descriptor Generator

A browser-based tool for generating USB descriptor C code compatible with **Eclipse ThreadX USBX** (formerly Azure RTOS USBX). No installation required — runs entirely in the browser.

🔗 **Live site:** [https://ayedm1.github.io/usbx_descriptor_generator.github.io](https://ayedm1.github.io/usbx_descriptor_generator.github.io)

---

## Features

### USB Device Descriptor Generator
Configure a complete USB device descriptor with:

- **USB Speed** — Full Speed (always enabled) and optional High Speed support
- **USB Classes** — Enable/disable and configure multiple classes per device:

  | Class | Code |
  |---|---|
  | HID — Human Interface Device | `0x03` |
  | CDC ACM — Abstract Control Model | `0x02` |
  | CDC RNDIS | `0x02` |
  | CDC ECM | `0x02` |
  | Mass Storage | `0x08` |
  | DFU — Device Firmware Upgrade | `0xFE` |
  | Printer | `0x07` |
  | Video | `0x0E` |
  | MTP — Media Transfer Protocol | `0x06` |
  | PTP — Picture Transfer Protocol | `0x06` |
  | Audio 1.0 / 2.0 | `0x01` |

- **String Descriptors** — Manufacturer, Product, Serial Number, and Configuration strings with multi-language support (English, French, German, Spanish, Italian, Japanese, Chinese Simplified)
- **JSON save/load** — Export the current configuration as JSON and reload it later
- **Template** — Load pre-filled example values instantly

### HID Report Descriptor Generator
Build USB HID report descriptors visually with:

- **Built-in device templates:**
  - Mouse (Boot Protocol)
  - Mouse (Absolute Positioning)
  - Keyboard (Boot Protocol)
  - Game Controller / Gamepad
  - Joystick
  - Consumer Control
  - Vendor-Specific
  - Custom (blank)
- **Item-level editor** — Add, remove, and configure individual HID descriptor items (Usage Page, Logical Min/Max, Report Size, Report Count, Input/Output/Feature, Collections, etc.)
- **JSON save/load** — Save and restore descriptor configurations
- **C code output** — Generate ready-to-use C arrays for USBX

---

## Usage

1. Open the live site (or clone and open `index.html` locally).
2. Configure your USB device on the **Device Descriptor** page.
3. If using HID, navigate to the **HID Report Descriptor Generator** to configure the report descriptor.
4. Click **Generate** to produce the C descriptor code.
5. Use **Load JSON** / **Save JSON** to persist and share configurations.

---

## Running Locally

No build step is required. Just clone the repository and open `index.html` in any modern browser:

```bash
git clone https://github.com/ayedm1/usbx_descriptor_generator.github.io.git
cd usbx_descriptor_generator.github.io
# Open index.html in your browser
```

---

## Project Structure

```
├── index.html                        # USB Device Descriptor Generator
├── hid_report_descriptor.html        # HID Report Descriptor Generator
├── script.js                         # Device descriptor logic
├── hid_report_script.js              # HID report descriptor logic
├── styles.css                        # Shared styles
└── hid_report_descriptor_template/  # Built-in HID JSON templates
    ├── mouse_boot.json
    ├── mouse_absolute.json
    ├── keyboard.json
    ├── game_pad.json
    ├── Joystick.json
    ├── Consumer.json
    ├── Vendor_specific.json
    └── Custom.json
```

---

## License

This project is licensed under the [MIT License](LICENSE).
