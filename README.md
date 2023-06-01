![Logo](https://kno.wled.ge/assets/images/ui/headers/wled_logo_akemi.png)

# WLED 2D Matrx Converter
It is an application that converts any image into code in JSON WLED format to 2D Matrix standards, currently it has only been tested on the 2D Matrix panel, but soon I will post news for the serpentine version.

### Features
- Converts any type of image
- Option on tape address format
- Result output option
- Choice of brightness intensity
- Convert transparent pixels to chosen color
- Convert animated GIFs
- Select image direct from [WLED-IP]/edit or upload
- Can save, simulate, copy or download generated code

## INTERFACE VERSION
### Download
**Right-Click** [[Interface]](https://raw.githubusercontent.com/ajotanc/wled-matrix-converter/main/interface.htm) and select save to your local computer.

### Tutorial
Showing usability in the interface version in an easy, simple and intuitive way.
https://github.com/ajotanc/pixelart-converter/assets/47322034/76bec6c3-7143-4453-815e-cc73fdc3a137

## INLINE VERSION
### Download
**Right-Click** [[Inline]](https://raw.githubusercontent.com/ajotanc/wled-matrix-converter/main/inline.htm) and select save to your local computer.

### Example of what the URL looks like
```
  GET http://WLED-IP/commands.htm?id=0&output=json&brightness=256&pre_segment=range&device=pixel_art_controller_001&unique_id=pixel_art_controller_001a&friendly_name=PixelArt&hostname=WLED-IP&color=%23CCFFE5&image=33.png&download=true&simulate=false
```

#### Description of parameters
| Parameters | Type | Description | Default | Required |
| ---------- | ---- | ------- | ----------- | -------- | 
| `id` | `integer` | Segment id | **0** | ✅
| `output` | `string` | Output type, options [json, curl, ha] | **json** | ✅
| `brightness` | `integer` | Brightness of the LEDs | **128** | ✅
| `pre_segment` | `string` | Address type, options [individual ("FFFFFF"), index(0, "FFFFFF"), range(0, 5, "FFFFFF") | **individual** | ✅
| `hostname` | `string` | WLED IP | - | ✅
| `color` | `string` | If the image contains a transparent background, you can change it to a desired color by passing the color in the HEX pattern | - | ⬜️
| `image` | `string` | Image which will be converted to standard JSON WLED | - | ✅
| `device` | `string` | Device name, mandatory if the output is "ha" | - | ⬜️
| `unique_id` | `string` | Unique device id, required if output is "ha" | - | ⬜️
| `friendly_name` | `string` | Friendly name of the device, mandatory if the output is "ha" | - | ⬜️
| `file` | `boolean` | If true, it will download the file according to the output | **false** | ⬜️
| `simulate` | `boolean` | If true, it will simulate the JSON WLED | **false** | ⬜️

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
